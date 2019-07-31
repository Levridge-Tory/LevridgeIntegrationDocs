# Print Configuration Notes
### Installing Print Service Application
To first install print service application open Visual Studio.
In Visual Studio, the print service is checked-in at "$/Levridge/CRM/Main/PrintService".

Double click this and map it to a path on your machine.




In Visual Studio click Build > Build Solution.
Activate the service as detailed below in PowerShell:
- Right click on the windows icon and select "Windows PowerShell (Admin)"
- Enter the following command once Be sure to substitute the local path!

      New-Service-Name "PrintService"-"{Your Local path to project}\PrintService\bin\Debug\PrintService.exe-k netsvcs" 
### Locating Printer Network Name
If a printer is a network device, its name will be more difficult to locate.
Use these steps to find the name that
the Print Service application will use to print:
1. Go to control panel and locate the setting titled "Devices and Printers"
(Note: Not all setting are in this screenshot. This view is set to "Small icons")


 