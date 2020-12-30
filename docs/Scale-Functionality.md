# Scale Functionality

## Overview

Levridge Scale allows you to improve efficiency and accuracy by automatically capturing weight and quality attributes during scale ticket creation when weighing trucks containing bulk products. Scale tickets and bill of ladings can easily be issued to drivers as well as synchronized real-time to Levridge Commodity accounting built in Microsoft Dynamics 365 Finance and Supply Chain Management.  Scale tickets can also be exported to other ERP systems. Levridge Scale provides a modern and easy to understand interface, allowing users to create scale tickets quickly and accurately.   

  - [Scale Application Configuration](scale-application-configuration.md)
  - [How to Install Levridge Scale](how-to-install-levridge-scale.md) 
  - [How to Update Levridge Scale](HowtoupdateLevridgeScale.md)
  - [ScaleHead Hardware Setup for Rice Lake 920i and Rice Lake 1280](ScaleHeadHardwareSetup.md) 
  - [Scale Appsettings Configuration](scale-appsettings-configuration.md)
  - [Scale Implementation Activities](ScaleImplementationActivities.md)
 
### Scale Ticket Types

Different types of scale tickets can be entered into the Scale app depending upon what type of transaction needs to be recorded. The type of scale tickets that can be entered include:

- Inbound Grain
- Outbound Grain
- Agronomy Sales
- Transfer
- Weight Only

### Customer Account

Select the correct Customer Account from the list.

Note: Customers appearing in the list are configured by setting them up in Setup > Application Configuration > Customer Short List.  See <strong>*[Scale Customer Short List](./scale-application-configuration.md###Scale-Customer-Short-List)*</strong> for more details. 

You can also search for any customer using the Search field. 

### Driver On

If the driver is in the truck when it is being weighed the Driver On toggle should be set to Yes.  If the Driver On toggle is not visible, it can be turned on by going to SETUP > Application Configuration > Settings > Is Driver On

### Weight

The weight from the scale can be recorded by selecting the Capture button.  You can also manually enter the Weigh-In and Weight-Out values.

### Gross Quantity

The gross quantity is calculated by taking the net weight and dividing it by the Factor entered in SETUP > Application Configuration > Gross Quantity Settings.   For example, when weighing Corn by the bushel, if a Factor of 56 has been entered and 53,300 has been captured as the Net Weight the Gross Quantity would be: 955.36 bushels.   

### Trucks in Yard

This contains the list of scale tickets that have been saved, but not yet complete or printed as either the truck is emptying its contents or is being filled and still needs to have its Weigh-Out amount captured on the scale ticket. 

### Grade Factors

Grade factor values used to determine quality discounts and premiums can be manually entered in the Scale Application or brought in with integrations to grain analyzers, such as the GAC 2500. 

If the Scale Application is integrated to one or more grain analyzer, the grade factor information taken from a sample will display in the Open Grade Factor Results and can be matched with the correct corresponding scale ticket. 
Grade factors can be printed on Grade tickets as well as the Scale ticket.

If grade factors are entered and maintained in Levridge they can be integrated with the Scale Application.  

### Scale Ticket History

The Scale Ticket History window displays today and yesterday’s printed scale tickets.  If you do not see a scale ticket in the history window that you expect it may be that the truck is still in the yard and that the ticket has not yet been printed. 

### Application Configuration

This is where the settings to change Site, Print, Etc. are located.

