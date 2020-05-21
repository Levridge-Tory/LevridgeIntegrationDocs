# Levridge Scale Integration

#### Azure service bus explorer for Integration 
1.	Down: F&O to scale
2.	Up: Scale to F&O
3.	Appsettings.json - configuration file, edit file to switch between up and down

#### Integration F&O to scale 
Here is the [Integration List](https://teams.microsoft.com/_#/xlsx/viewer/teams/https:~2F~2Fstoneridgesoft.sharepoint.com~2Fsites~2Flevridge~2FShared%20Documents~2FGeneral~2FDevelopment~2FIntegration~2FIntegration%20Event%20Ordered%20Entity%20List.xlsx?threadId=19:7aa3b4752ccd44c38b06dca038958883@thread.skype&baseUrl=https:~2F~2Fstoneridgesoft.sharepoint.com~2Fsites~2Flevridge&fileId=8AEC9593-E967-4418-8201-6E6158C18F3E&ctx=files&viewerAction=edit)
which lists the entities needed when integrating F&O to scale through System administration > Setup > Event Framework > Event framework events.
1.	System administration > Setup > Event framework > Event framework events
2.	Run azure service bus Down
3.	Run IntegrationConsole.cmd

#### Integration scale to F&O
1.	Run azure service bus Up
2.	Run IntegrationConsole.cmd
3.	When Print is clicked on the scale app, the ticket will then sync to F&O.

#### Printer Server Web Configuration
The Printer Server Web Config inclues two critical functions: 
1. Root Directory
      - This is where the server is in the file pathing and saved in the C-Directory. The printer server should exclude the drive letter and have the path to where the web.config is located since it is looking for its report files. 
2. Default Connection
- This is how the printer server communicates with the database. 
- The key piece is knowing the data source, being eithe rthe IP or the exposed fully qualified domain name to access the database. Fully qualified domain name correlates to the DNS in the internal network. 

#### Scale Entities for Integration
##### Agronomy Release
- Agronomy release
- LevUnitOfMeasureEntity
- HcmWorkerEntity
- LevScaleReleaseProductsEntity
- LevHazardousMaterialsTableEntity
- LevGrowingSeasonEntity
- CustCustomerV3Entity
- LevSplitGroupEntity
- LevSplitGroupLinesEntity
- LevAccountToOperationRelationshipEntity
- LevCustomerOperationEntity
- LevCustomerSiteEntity
- LevRollingStockV2Entity
- LevFreightCarrierEntity
- LevInventSiteEntity
- LevWarehouseEntity
- LevScaleOperatorEntity
- LevScaleHouseSalesOrderEntity
- LevScaleHouseScaleTicketEntity