# How to Update Levridge Scale

#### Prerequisites
An older Version of Levridge Scale must be installed and configured

#### Setup
1.	Open Services
2.	Stop all Levridge Scale services
    a.  LevEstimatedTicketService
    b.  LevHardwareInterfaceService
    c.	LevridgeAxToScale
    d.	LevridgeScaleToAx
    e.	LevScaleClient
    f.	LevScalePrinterService
3.	Download the new version installer file Levridge Scale House Install.exe 
4.	Right click and *Run as Administrator*
5.	Agree to terms and click Install
6.	Click Next on the setup Wizard
7.	Accept the terms and click Next
8.	Select Typical for the setup type
9.	Click Install
10.	When the install is complete, click Finish
11.	When the installer displays “Installation Successfully Completed”, click Close
12.	Open Services
    - On the **LevHardwareInterfaceService** and **LevScaleClient services**, right click > Properties 
    - Click the Log On tab 
    - Enter account and password and click OK. If the account is part of a directory, click Browse. Then enter the username and click Check Names.
13.	Check the configuration of appsettings
    - Open file explorer and go to C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Servers 
    - In the API and Client folders, configure `appsettings.json`
    - Open file explorer and go to C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Services 
    - In the **LevEstimatedTicket** and **AxToScaleIntegration**, **ScaleToAxIntegration** folders configure `appsettings.json`
14.	Restart the PC

