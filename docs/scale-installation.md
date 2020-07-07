## ScaleHead Hardware Setup for Rice Lake 920i

#### Add the Equipment Information

1. In **LevridgeScale**, click Application Configuration > Equipment Management
2. Click Create New
3. Set is active = Yes
4. Set is scale = Yes
5. Enter Equipment Name
      - This is the name that will show in the list and on printed reports
6. Equipment Description (not used)
7. Location (not used)
8. Custom Character = L
9. Click Save, then Edit for the next two fields to be visible
10. Equipment Response Type ID = 4
11. Return Response Type ID = 5
12. Service URL (http://localhost:5000)
13. Click Save

#### Add the Equipment Field Details
1. From **Equipment Management**, click Edit on the Equipment record
2. Click Equipment Field Details
3. Click Create New
4. Enter a name (ex. "weight")
5. SequenceID = 1
6. Check the box by OutputStreamTypeId
7. FieldName = weight
8. StringLength = 30
9. ReturnTypeResult = String
10. Click Create
11. Click Back to Equipment

#### Add the Connection Details
1. Click **Connection Details**
2. Name = 1
3. Hostname = `<ipaddress of scalehead>`
4. Port = 10001
5. TypeId = TcpIDClientStream
6. Click Submit

#### Create a Workstation
1. In **LevridgeScale**, click Application Configuration > Workstation Management
2. Click Create New
3. Enter a Workstation name (ex. "Ws1")
4. Click Create
5. Click Edit
6. Under Equipment, mark the box next to the Scale
7. Click Save

#### Configure the Hardware Service with the Workstation  Name
1. Navigate to the folder: **LevridgeScaleHouse/Services/HardwareInterface**
2. Open appsettings.json
3. Enter the WorkstationName (ex: "WorkstationName" or "Ws1")
4. Open (Windows) Services
5. Restart LevScaleHardwareService

### Internal Database Information
#### Database Fields
1.	In Hardware > dbo.ExquipmentExportMaster
    - EquipmentResponseTypeId = 4 (custom character deliminated)
      - GO TO Library.cs in DataExchange project. Look at ReturnType
    - EquipmentExportId = unique identifier, use a GUID
    - CustomCharacter = L (lb from Scale)
    - EquipmentName
    - EquipmentDescription
    - ReturnResponseTypeId
    - EquipmentTypeId = GUID
    - ConnectionId = GUID
    - TemplateId
    - CertificationType
    - IsActive = True
2. ConnectionMaster
    - ConnectionId = from EquipmentExportMaster
    - ConnectionName = tcp
    - HostName = ip address
    - HostPort = 10001
    - ConnectionTypeId = type of connection (serial, tcp, etc.) 10 for ricelake 920i
    - Only if TCP
      - HostName (ip address) and HostPort (10001)
    - Only if serial:
      - SerialLine, Speed, DataBits, StopBits, Parity, FlowControl
3.	EquipmentExportDetail
    - EquipmentDetailId = GUID
    - EquipmentExportId = from ExportMaster
    - DetailName =
    - ReturnTypeResult = 2 (string)
    - ArrayIndex = 0
    - FieldName = weight
    - StartCharacter = 0
    - StringLength = 30

#### Additional Items
- While in the service, it calls it Exchance Objects and treats it as a controller
- We initialize it by getting all active items (equipment master)
- We set up monitor connection type based on ConnectionType

















- Windows user account needs to have local admin rights and a password
- PC needs to have an internet connection
- Disable any security add-ons (Bitdefender, etc.)
- Install SqlExpress using the "basic" installation: [SqlExpress Installation](https://go.microsoft.com/fwlink/?linkid=866658). The SQLEXPRESS connection string will default to: 
```    
 > Server=localhost/SQLEXPRESS;Database=master;Trusted_Connection=True;
```
- Enable IIS through Control panel > Programs and Features > Turn Windows features on or off > Internet Information Services. Check the root box for Internet Information Services and let it select the defaults.

#### Install Levridge Scale
1. Download the file Levridge Scale House Install.exe 
2. Right click and *Run as Administrator*
3. Agree to terms and click Install (The installer will run for a while and download items)
4. Click Next on the setup Wizard
5. Accept the terms and click Next
6. Select Typical for the setup type
7. Click Install
8. When the install is complete, click Finish
9. When the installer displays “Installation Successfully Completed”, click Close


#### Configure Settings
Reference [Scale Install Settings Instructions](scale-install-settings-instructions.md). 

- Open file explorer and go to: 
```
    C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Servers
```
- In the **API** and **Client** folders, configure `appsettings.json`
- Open file explorer and go to: 
```
    C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Services
```
- In the **LevEstimatedTicket** and **AXToScaleIntegration**, **ScaletoAXIntegration** folders configure `appsettings.json`

#### Log into Services

- Open IIS
- On the **LevScaleAPI** and **LevPrint** Application Pools, right click > Advanced settings
- In the Identify field select Custom account > Set and enter username and password
- Open (Windows) Services
- There should be five new services installed with startup Type of Automatic:
1.  LevHardwareInterfaceService
2.  LevridgeAxtoScale
3.  LevridgeScaletoAx
4.  LevScaleClient
5.  LevScalePrinterService
- On the **LevHardwareInterfaceService** and **LevScaleClient** services, right click > Properties
- Click the Log On tab
- Enter account and password and click OK. If the account is part of a directory, click Brose. Then enter the username and click Check Names. 

    ![LogOn Information](assets\images\ScaleApp\LogOnInformation.png)

- Restart the machine. When it restarts, the services will start automatically and the databases will be created. 

#### Access Levridge Scale
- In a web browser, go to http://localhost to access Levridge Scale

    ![Local Host Levridge Scale](\assets\images\ScaleApp\LocalHostLevridgeScale.png)


#### Sync Data from F&O
- In F&O, create an Event Framework endpoint definition for scale
```
Service Bus endpoint: 
Endpoint=sb://example.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx=
Enter the Topic name
Endpoint type: Topic
Session Required: Yes
Enabled: Yes
```
- Create an Event Framework event and sync all scale entities, referenced in [Scale Integration](scale-integration.md).

