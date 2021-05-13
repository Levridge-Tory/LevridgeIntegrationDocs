# Commodity Accounting Setup - Discount Tables

## Overview
Step by step process of how-to setup discount tables within the Commodity Accounting module of the Levridge Environment. 

## Goal
By the end of this document, you will be able to setup discount tables within the Levridge Environment.

### Discount Tables Setup

1.	Main menu > Commodity accounting > Setup > Discounts & fees > Discount tables
2.	Add new Discount table (+New)
3.	Input Discount table ID
4.	Input Description 
5.	Select Commodity 
    1. You can only have one commodity with a discount table.
6.	Select Discount lines type 
    1. Range – Need a definition for this 
    2. Quality grades – this will use the quality grade factors you have setup in the system so if the discount falls with that quality grade factor range then it will assign that discount value to it.
    3. Value – is just a string entry. In other words, you just put in whatever item you want, whatever value you want numeric, and if it finds it in the discount table, then it will charge that discount factor. 
    4. Grade factor exists - could also be called a yes or no. In other words, something like odor if it has it. It is a yes, but doesn't it to know? And if it is a Yes, then we assign whatever value that is in there. 
7.	Select Calculation method
    1. Per unit - cost per unit in the schedule.
    2. Percent of price - percentages of price in the schedule.
8. Select Unit of measure
    1. Bushel is set as the Unit default.
9.	Select Currency
    1. Currency defaults to your primary currency. 
10.	Select Grade factor
11.	Direction of range
    1. Determined by Grade factor selected.
12.	Select Gross/Net
13.	Select Charges Code
    1. Charges code is a setup for the accounting side of it. So it's just a matter of which way you want to go with it.- could use a better definition for charges code here
14.	Input Notes 
    1. Strictly an internal item.
15.	Invoice Toggle
    1. The purpose of this toggle switch is if you want to be able to invoice this item. Prior to it being settled, so any tickets that are delivered and the moisture charge is calculated. If I turn this to yes, I can choose the invoice item that I want to use and I will be able to create an invoice. Prior to settlement, so we can charge this out ahead of time if we choose to do that. 
16.	Select Main account
    1. The main account is the General Ledger account that you want to charge. Or recognize the revenue which we've chosen drying income here for our account. So then all of the discounts that are calculated here updates the drying revenue in the General Ledger account. 
17.	Setup is now complete 

### Add Discount Table Line
The next option is to establish the lines and how we are going to calculate.

1.	Click (+ Add line)
    1. In most cases, when adding discount table lines, you do not want to leave any ranges uncovered. 
    2. When you click to add another line, it's going to start at the next available range.

### Auto build Lines

1.	Click on Auto build lines
2.	Input Starting range value
3.	Input Ending range value
4.	Input Increment change amount 
5.	Input Starting discount value 
6.	Select Direction of range
7.	Input Discount change amount
8.	Input Shrink % starting value 
9.	Select Direction of range
10.	Input Shrink increment change amount 
11.	 Premium toggle
     1. If this is a premium calculated, you could throw the toggle and it would then consider to premium and add back to the customer’s settlement if need be.
12.	 Once information is correct, click Generate lines 







