## How to Install Levridge Scale

#### Prerequisites
- Windows user account needs to have local admin rights and a password
- PC needs to have an internet connection
- Disable any security add-ons (Bitdefender, etc.)
- Whenever prompted to use a browser, use Chrome
- Install SqlExpress using the 'Basic' installation
  - SQL is located in the Master Scale App Install folder
  - It was downloaded from <https://go.microsoft.com/fwlink/?linkid=866658>
  - The SQLEXPRESS connection string will default to `Server=localhost\SQLEXPRESS;Database=master;Trusted_Connection=True;`
- If IIS is not enabled, enable IIS through Control panel>Programs and Features>Turn Windows feature on or off>Internet Information Services. Check the root box for Internet Information Services and let is select the defaults. Ensure everything under IIS>World Wide Web Services>Application Development Features is checked. 
- If you receive an error, when downloading IIS you may need to make a change in the registry: 
```
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU
```
- Set "UseWUServer" to 0

#### Install Levridge Scale
1. Run the Levridge Scale House Install.exe
2. Right click and *Run as Administrator*
3. Agree to terms and click Install
4. When the installer displays "Installation Successfully Completed", click Close

#### Configure Settings
reference the *2. Levridge Scale Appsettings* document
1. Open file explorer and go to C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Servers
2. In the **API** and **Client** folders, configure appsettings.json
3. Open file explorer and go to C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Services
4. In **AxToScaleIntegration** and **HardwareInterface** folders, configure appsettings.json

#### Log into Services
1. Oepn IIS
2. In Application Pools, right click DefaultAppPool and click Stop
3. On the left under Sites, rick click Default Web Site>Manager Website>Stop
4. On the left select Application Pools, on the right do the follow steps for BOTH **LevScaleAPI** and **LevPrint**
    - Right click>Advanced settings
    - In the Identity field select Custom account>Set and enter username and password. Use the username and password. 
5. Open (Windows) Services
6. There should be 4 new services installed:
   - LevAxToScaleService
   - LevHardwareService
   - LevPrinterService
   - LevScaleClient
7. Set the Startup Type to "Automatic (Delayed Start)"
8. On the **LevHardwareService** and **LevScaleClient** services, change the Log on for EACH service:
    - Right click on the service>Properties
    - Select the Log On tab
    - Select account and password
    - Click Apply and OK
9. Restart the machine. When it restarts, the services will start automatically and the database will be created. 

#### Access Levridge Scale
1. In a web browser, go to http://localhost to access Levridge Scale

![Access Leverage Scale.](.\assets\images\ScaleApp\Access-Levridge-Scale.png "Access Leverage Scale")

#### Sync data from F&O
1. In F&O, Create an Event Frameowrk endpoint definition for scale

Service Bus endpoint: 
```
Endpoint:=sb://example.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx=
```
- Enter the Topic name
- Endpoint type: Topic
- Session Required: Yes
- Enabled: Yes
2. Create an Event Framework event and sync all scale entities, referenced in [Scale Integration](scale-integration.md)
