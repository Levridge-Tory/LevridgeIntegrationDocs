# Scale Overview

The purpose of Levridge Scale is to receive all the data measured at the scales at ag retailer locations and incorporate it into a scale ticket
which can be printed out and given to the grower, while also bringing the scale ticket into the Dynamics 365 ERP system. 
Within the accounting technology solution, the contents of the scale ticket can be accounted for and posted against contracts the grower has with the ag retailer.

The LevridgeScaleApp structure is a browser-based Scale application with the functionality of being able to operate as a server or as a desktop.
1. IIS (Internet Information Services) which is a Microsoft web server. 
2. A Windows desktop, which is a background Windows service. 

The functionality is chosen based on the specific requirements of the clients. If the client’s functionality only includes a Windows desktop station, Levridge Scale App can be run as a service capability as not every scale will have a server.  


  - [Scale Settings Configuration](scale-settings-configuration.md)
  - [How to Install Levridge Scale](how-to-install-levridge-scale.md) 
  - [How to Update Levridge Scale](HowtoupdateLevridgeScale.md)
  - [ScaleHead Hardware Setup for Rice Lake 920i and Rice Lake 1280](ScaleHeadHardwareSetup.md) 
  - [Scale Appsettings Configuration](scale-appsettings-configuration.md)
  - [Scale Implementation Activities](ScaleImplementationActivities.md)
 
#### IIS Server Functionality
If LevridgeScaleApp is ran as a server, it would operate with a Reverse Proxy. This is very important for implementation purposes. Required server information include the Printer Server and API Server.  

Clients are always classified as “server” regardless if operating as a service or server. The intent is the client operates to serve content to the client. 

The two servers are: 
1. LevScaleAPI
      - This server handles all the back-end calls. This is where the integration framework communications with the scale. O-Data calls which are in turn the integration framework. O-Data is very necessary due to the ability to operate with other ERP systems. 
2. LevScalePrint
      - This server renders all the reports for printing. It communicates with the client printer service. This is within the .net framework. 

#### Desktop Environment Service Functionality
The four services within a Windows desktop environment include: 

1.	LevPrintService
      - Can install the LevPrintService to any computer within a client’s Intranet. It has the capability of rendering reports at any location if the LevPrintClient is registered at the specific location. This also includes the Zebra printing capability. 
2.	LevHardwareService
      - This is the service that handles communication with hardware such as the scale head.
3.	LevridgeAXToScale
      - Along with LevridgeScaleToAX is the integration framework. The ratio would be one LevridgeAXToScale and one for the current desktop or LevScale instance. This enables F&O to broadcast all internal information that is necessary. LevridgeAXToScale would be looking at the specific service bus channel. It will then write into the LevScale through the LevScaleAPI. 
4.LevScale
      - LevScale is the defining factor between a server and service. LevScaleClient and LevScale are executing the same file path and processes. This is operating a straight web server without the reverse proxy capability. 

#### Scale Ticket Types

- Inbound Grain
- Outbound Grain
- Agronomy Sales
- Transfer
- Weight Only

#### Trucks in Yard
- These will be shown "in the yard" since they are uncompleted tickets that have not been printed.

#### Scale Ticket History
- This is the history of printed tickets from today and the previous day.

#### Application Configuration
- This is where the settings to change Site, Print, Etc. are located.

#### Delivery Sheets
- Here you can view and create delivery sheets for grain tickets.
- The scale tickets and delivery sheets will sync both ways between F&O and the scale app.

#### Create Scale Tickets
- http://levscaledev.corp.stoneridgesoftware.com/
