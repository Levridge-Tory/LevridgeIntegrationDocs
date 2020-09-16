# Commodity Accounting Implementation Activities

## Overview
The following is an overview of the implementation activities necessary for Commodity Accounting.  

### Activities

*All of the following tasks are in FinOps:*
 
In Product information management > Setup > Categories and attributes > Category hierarchies 

- Create product categories for commodities and add commodities to the categories - Need client input
 
In Product information management > Products > Released products

- On each product that is a commodity, enter values into the Commodity fast tab
- Enter units of measures and conversions specific to commodities
 
In Accounts receivable > Customers > All customers

- Set up lien holders for commodity customer - timeline dependent on how many customers and lien holders (roughly 10 min per customer/p lien holder)
- Enter ship to addresses for scale tickets, sales contracts and transportation management (often imported with data migration activities)
 
In Accounts receivable > Setup > Agriculture > Split groups

- Enter split groups used for commodity accounting (roughly 5 minutes per split, might be imported during data migration)
 
In Accounts receivable > Customers > All customers > Agriculture tab in the action pane > Operations

- On customer operations and sites set the commodity split defaults for each commodity customer
 
In Accounts receivable > Setup > Agriculture

- Create growing seasons for use on scale tickets
 
In Cash and bank management > Bank accounts

- Enter bank accounts that will be used as hedge accounts
 
In General ledger > Journal setup > Journal names

- Verify a customer prepayment journal type exists for sales advances
- Create journals to be used for grain settlements and payments
 
To utilize the Daily position report (DPR) set up Power BI
 
 In Commodity accounting > Setup

- Configure Commodity accounting parameters
- Setup Inbound ticket auto apply schedule
 
In Commodity accounting > Setup > Discounts and fees

- Create discount tables and schedules
- Create fee schedules and tables
 
In Commodity accounting > Setup > Contracts

- Enter contract types
- Enter weights to govern
- Enter grades to govern
 
In Commodity accounting > Setup > Quality and grade factors

- Enter grade factors
- Enter quality grades
- Enter grade averaging schedules
 
In Commodity accounting > Setup > Risk

- Create dispositions
- Configure DPR parameters (requires input from client)
- Enter hedge charge codes 
- Enter Market zones 
 
In Commodity accounting > Risk management

- Enter commodity tickers
- Create delivery periods
- Enter the bid sheet configuration
- Enter discount schedule defaults
- Enter grade average defaults