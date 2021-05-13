# How to Update Levridge Scale

#### Prerequisites
An older Version of Levridge Scale must be installed and configured

#### Setup
1. Download the new version installer exe file   
2. Right click and Run as Administrator 
3. Agree to terms and click Install 
4. When the install is complete, click Finish 
5. Open IIS 
6. On the LevScaleAPI and LevPrint Application Pools, right click > Advanced settings 
7. In the Identity field select Custom account > Set and enter username and password 
8.	Open Services
    - On the **LevHardwareInterfaceService** and **LevScaleClient services**, right click > Properties 
    - Click the Log On tab 
    - Enter account and password and click OK. If the account is part of a directory, click Browse. Then enter the username and click Check Names.
9.	Check the configuration of appsettings
    - Open file explorer and go to C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Servers 
    - In the LevScaleAPI and LevScaleClient folders, configure `appsettings.json`
    - Open file explorer and go to C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Services 
    - In the **AxToScaleIntegration** and **ScaleToAxIntegration** folders configure `appsettings.json`
10.	Restart the PC
