# Commodity Accounting Setup - Discount Schedules

## Overview
Step by step process of how-to setup discount schedules within the Commodity Accounting module of the Levridge Environment. 

## Goal
By the end of this document, you will be able to setup discount schedules within the Levridge Environment.

### Discount Schedules Setup

1.	Main menu > Modules > Commodity accounting > Setup > Discounts & fees > Discount schedules
    1. When the discount schedules window opens, you are able to see all existing discount schedules out there already. You can view those at any time.
2.	Add (+ New)
3.	Input Discount schedule name
4.	Select Commodity
    1. Discount schedule is for one commodity only.
5.	Input Description
6.	Input Notes
    1. Strictly an internal item.
7.	Add Discount tables
    1. You can enter a click new and enter each line as you choose to.
        1. Select Discount table
        2. Select Discount gross or net
        3. Select Discount net type
        4. Input Discount net line 
        5. Select Shrink
            1. If you select no shrink, all following columns (shrink or discount first, shrink gross or net, shrink net type, shrink net line, shrink sequence) are irrelevant and do not need to be filled in.
        6. Select Shrink or discount first
        7. Select Shrink gross or net
        8. Select Shrink net type
        9. Input Shrink net line
        10. Input Shrink sequence 
            1. The Shrink sequence column is significant if you have more than one table in your schedule that will be shrinking. The system must know it can’t shrink them both at the same time, both on gross, so it has to know which one to do first. If you only have one shrink item in your table, then shrink sequence at number one will be the only one you need.
8.	Repeat the above process until you have added all applicable discount tables or deleted any unnecessary discount tables 

### New (Prompted)

New (Promoted) is a wizard that guides you through the process of creating a discount schedule line. 

1.	Click on New (Prompted)
2.	Input Line number
3.	Click Next
4.	Select Discount table 
5.	Select Gross/Net
6.	Select Calculation type
7.	Select Discount net line
8.	Next
9.	Select Shrink
    1. Yes
        1.Select Shrink or discount first
        2. Select Gross/Net
        3. Select Net calculation type
        4. Input Line
        5. Input Shrink sequence
    2. No
        1. All other fields will not be active, so you do not need to complete them
10.	Click Next
11.	Check to ensure line information is correct
12.	Click Finish
13.	Click Save to complete discount table setup 












