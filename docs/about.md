# Print Configuration Notes
### Installing Print Service Application
To first install print service application open Visual Studio.
In Visual Studio, the print service is checked-in at "$/Levridge/CRM/Main/PrintService".

Double click this and map it to a path on your machine.

![print configuration 1.1](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.1.png)

In Visual Studio click Build > Build Solution.
Activate the service as detailed below in PowerShell:

- Right click on the windows icon and select "Windows PowerShell (Admin)"

- Enter the following command once Be sure to substitute the local path!
    
>     New-Service-Name"PrintService"-"{Your Local path to project}\PrintService\bin\Debug\PrintService.exe-k netsvcs"
 
### Locating Printer Network Name
If a printer is a network device, its name will be more difficult to locate.
Use these steps to find the name that
the Print Service application will use to print:

1. Go to control panel and locate the setting titled "Devices and Printers"
(Note: Not all setting are in this screenshot. This view is set to "Small icons")

     ![Print Configuration 1.2](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.2.png)

2. Navigate to the list of print options on your computer and select the device of your choice.

     ![Print Configuration 1.3](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.3.png)

3. The full network name that is required for the code is listed once you select the printer. (Highlighted in yellow below)

     ![Print Configuration 1.4](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.4.png)


### Using Print Service Application
After initial setup, use one of the following two options to start the Application.

**PowerShell**

Following the first setup, you can enter the following command into PowerShell instead.
    
>     Start-Service-Name"PrintService"

**Services App.**

Use Windows+R to select "services.msc" to open Services Management Console. Right click on PrintService and select "start"

![Print Configuration 1.5](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.5.png)

### Setting Up a New Printer

To set up a new printer, new parameters will need to be setup. To add the parameters, open the app.config file in the project and add the following:

- ServiceBusConnectionString
- ServiceBusTopicSubscription
- ServiceBusTopic
- PrinterName
- SiteID

Two parameters will also need to be updated.
These are the printer name and the SiteID.
These two need to be changed for the printer that is being printed to.
The Site ID is the customer site code from CRM.

![Print Configuration 1.6](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.6.png)

For debuggin the Service, we can use the Windows Event Viewer. Go to Administrative tools in the Control Panel and Open Event Viewer.

![Print Configuration 1.7](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/Print%20Configuration%201.7.png)

### Additional Information and Documentation

In CRM on the sales odered details header, there is an Auto Print Field. Set to Yes and click save. The sales order will then print. 
 

# Configuration Setup CRM
To begin configuration setup in CRM, first import LevCore Solution followed by importing
Agronomy Solution.

Migrate the ESG Configuration data using the Configuration Migration Tool
   - This tool can be downloaded at https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/download-tools-nuget

Ensure an Application User has been created with admin secuirty roles assigned.

If integrating records from CRM to AX, you will need to create steps on the service endpoint using the Plugin Registration tool.

Steps will also need to be created on plugins which require the pricing service. The configuration will look like this:
```<language>
   {
     "clientappid": "da7c3de3-5555-49ab-8465-d01e8cd22e58",
     "clientappsecret": "dradgg38ddszLzgqbcZ3/8sG2FbC/BSWxnCtXzJsWP8=",
     "tenant": "https://login.microsoftonline.com/5555a5b1-fbt8-465b-ad9d-21e21129e610/oauth2/token",
     "uristring": "https://environment22c2251c662a7e541devaos.cloudax.dynamics.com/api/services/LevPricingServices/PricingService/getPricing",
     "resource": "https:// environment22c2251c662a7e541devaos.cloudax.dynamics.com",
     "username": "John.smith@email.com",
     "password": "plaintextpassword"
   }
```

Setup the data through integrations, create it in CRM, or import data packets.

![2.1](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/2.1.png)

Entities in pink must be set up in CRM
Entities in yellow will integrate over from FinOps
Entities in Green will integrate from Agsync

![2.2](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/2.2.png)

![2.3](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/2.3.png)

![2.4](file:///C:/Users/emilys/Source/Repos/LevridgeIntegrationDocs/docs/assets/images/2.4.png)

Once item categories have been either created or imported in, the filtered xmls on the Plans and Batch Plans will need to be updated to reflect the item category GUIDs within 
your environment
   
  - The Proposal OOB Propposal line Subgrids will also require filter updates to reflect the Item Category's in your environemnt.



 