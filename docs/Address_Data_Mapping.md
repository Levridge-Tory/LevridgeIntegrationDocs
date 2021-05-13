# Address Data Mapping

## Overview

Address Data Mapping functions to set a primary addresses on the Account and Contact form which come from the Account Address, Account Electronic Address, Contact Address, and Contact Electronic Address ESG. This is done through the use of the LevridgeCore.AddressDataMap plugin and Address data Mapping configuration records. The plugin will be part of the solution, but pluggin steps will need to be created for the entities you want the address data mapping on. Address Data Mapping records will need to be either migrated into the environment or they will need to be created by the implementation team. 

The Address Data Map plugin currently will set the address fields and electronic address fields on the default Account and Contact form. 

In order to create an Address Data Mapping file, navigate to your environment>Advanced Find>Look for Address Data Maps>Results> New Address Data Map.

![AddressDataMapping1](.\assets\images\AddressDataMapping\AddressDataMapping1.png)

Above is an Address Data Map for the Account Address. Essentially the main areas you need to focus on is entering in a name, correct primary entity, in this case it is Account, and then the Child entity which is lev_address. Because this is the not dealing with the electronic addresses, you can set the electronic address field as none. In the Data Mapping section you will want to focus on mapping the address fields to the fields present on the form you are mapping to. 

In the Case you are creating an Electronic Address Address Data Map, you will once again enter in a Name, primary and child entity. Now you will select an Electronic Address Type, in the case below it is an Email Address. In the Electronic Address section you will have to map the field in which you want the Primary Electronic Address to present. Click Save, and make sure to activate the record.

![AddressDataMapping2](.\assets\images\AddressDataMapping\AddressDataMapping2.png)

### Setting up the plugin steps for Address Data Mapping

You will need to setup a create and update plugin step for each entity utilizing the address data mapping such as the Account Address or Contact Address.
To set up the plugin steps for address data mapping, you will use the Plugin Registration Tool which is a Microsoft tool.
1.	Connect to your CRM environment.
2.	Click/expand the LevridgeCore assembly, then click on the LevridgeCore.AddressDataMap pluggin

![AddressDataMapping3](.\assets\images\AddressDataMapping\AddressDataMapping3.png)

3. With the plugin selected, click the Register dropdown on the top left of the screen, and click Register New Step

![AddressDataMapping4](.\assets\images\AddressDataMapping\AddressDataMapping4.png)

4.	Next fill out the form using the Template in the screenshot below, one is for Create and another for Update. Then click Register Step

![AddressDataMapping5](.\assets\images\AddressDataMapping\AddressDataMapping5.png)

![AddressDataMapping6](.\assets\images\AddressDataMapping\AddressDataMapping6.png)

