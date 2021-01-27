# Commodity Accounting Setup - Contract Types

## Overview
Step by step process of how-to setup of contract types, weights and grades to govern, delivery periods and commodity tickers within the Commodity Accounting module of the Levridge Environment. 

## Goal
By the end of this document, you will be able to these items within the Levridge Environment.

### Contract Types Setup

1.	Main menu > Modules > Commodity accounting > Setup > Contracts > Contract types 
Note: Majority of organizations will use the following contract types: Basis, Cash, Futures Fixed, Min Price, or Price Later.
2.	Add new contract type (+New)
3.	Input Contract type name
4.	Input contract type description
5.	Select pricing type 
    1. The contract type is something that is already established within the Levridge environment and the user must select from that predetermined list. This will indicate how the pricing is handled of the contract type and determine where it shows up in your long and short and how tickets get applied to it. 
    2. Pricing types include: Basis, Cash, Futures, Minimum price, Price later, No price adjustment, Min-max price, and Bonus premium. 
6.	Select disposition 
7.	Save

### Weights to Govern Setup

1.	Main menu > Modules > Commodity accounting > Setup > Contracts > Weights to govern 
2.	Add new weight to govern (+New)
3.	Input Weights to govern name
4.	Input Description
5.	Select Govern type
    1. The Govern type determines how the contract establishes how the weights will be used
6.	Save 

### Grades to Govern Setup

1.	Main menu > Modules > Commodity accounting > Setup > Contracts > Grades to govern
2.	Add new Grades to govern (+New)
3.	Input Grades to govern name
4.	Input Description
5.	Select Govern type
    1. The Govern type determines how the contract establishes how the grades will be used
6.	Save

### Delivery Periods Setup

1.	Main menu > Modules > Commodity accounting > Risk management > Delivery periods
    1. Delivery periods are not located in the setup menu because you must maintain delivery periods more often. Delivery periods must be updated periodically.

### Edit Delivery Period to make Inactive

1.	Select the delivery period you would like to edit by click the far-left checkmark column to the applicable line
2.	Click the box in the Inactive field so that it is also check marked 
    - By making a delivery period inactive – it will no longer show up in the scans for the user to choose. If the user tries to use an inactive period, a warning will pop up notifying them that the delivery period is inactive. 
3.	Save 
    - You can view all inactive Delivery periods by checking the Show inactive box at the top of the Delivery period screen. 

### Add New Delivery Period Setup

1.	Add new Delivery period (+New) 
2.	Select Delivery period ID 
    1. The Delivery period ID can use any alphanumeric character of your choice. (Example: 2112, first two characters are the year, and last two characters are the month).
3.	Input Description 
4.	Select Start date
5.	Select End date 
6.	Save 

Note: The Delivery periods are user defined. 

### Commodity Tickers Setup

A Commodity ticker is the trading month on the exchange that you are using for hedging purposes. Commodity tickers are user defined.

1.	Main menu > Modules > Commodity accounting > Risk management > Commodity tickers
2.	Add new Commodity tickers (+New)

### Ticker Details Fast Tab
1.	Input Ticker ID
    1. The Ticker ID is user defined. (Example: CH21, C is for Corn, H is for March and 21 is the year).
2.	Input Description
3.	Select Board of trade
4.	Input Option month
5.	Input Option year
6.	Select Expiration date
    1. Expiration date is a user defined field.
7.	Select Default price by date
    1. Default price date is a user defined field. 
8.	Input Full quantity
9.	Input Mini quantity
10.	Select Unit

### Commodities Fast Tab

You can have multiple commodities per commodity ticker. 

1.	Click to drop down the Commodities fast tab 
2.	Add new Commodity (+New)
3.	Select commodity 
4.	Repeat until you have added all applicable commodities 
5.	Save 











