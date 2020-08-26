# Scale Implementation Activities and Estimates

## Overview
The following is an overview of the implementation activities and estimates necessary for getting started with scale.  

### Full Implementation - Includes Integration to FinOps
At the scale:
1.	Install the [scale application](how-to-stall-levridge-scale.md) (4 hrs)
2.	Setup Azure service bus 
    - 3-5 days if don't already have the subscription
    - 2 hrs if creating new topic and subscription from existing Azure namespace
3.	Configure the Azure service bus to connect to FinOps (2 hrs)
    - Setup event endpoint in FinOps
4.	Configure the [appsettings.json](appsettings.json.md) files for the scale application (2 hrs)
5.	Connect [hardware](ScaleHeadHardwareSetup.md) to the application (2-5 hrs)
6.	Configure the scale application settings (2-4 hrs)
    - Customer short list
    - Gross quantity settings
    - Printer settings
    - Equipment mgmt
    - Main settings page
### In FinOps
1.	Set up the event framework events for integrating to the scale (2-3 hrs)
2.	Configure data that will be sent back-and-forth to the scale (2-5 weeks) (requires input from client on how they want to use the scale)
    - Products
      - Carrier services
      - Use in scale flag
      - Net weight
      - Units of measure
      - Create estimated ticket flag
      - Use TMS parameters
    - Scale operators from the workers table
    - Rolling stock
      - Equipment types and container weights (if using estimated tickets)
    - Grade factors
    - Grade factor sequencing
    - Growing seasons
    - Hazardous materials
    - Freight carriers
    - Customers
    - Customer split groups
    - Customer operations and sites
    - Units of measure
    - Inventory sites
    - Pits
    - Bins
3.	Setup number sequences (2-4 hrs)
4.	Setup scale parameters under AR > Setup > Ag > Ag parameters (1 hr)
    - All scale tickets
    - Agronomy scale
5.	Configure batch processes for generating orders from tickets (sales orders, transfer orders, etc.) (2-4 hrs)
6.	Configure TMS (4-6 days) (requires input from the client on how they want to configure)
    - Delivery terms
    - Shipping carriers
      - Grower and company
    - Carrier services
    - TMS parameters under TMS > Setup > TMS parameters > General > Agronomy scale
      - Default settings for grower and company carriers
    - Rating and routing
7.	Synch initial data to the scale prior to running (3-6 hrs) 

