# Commodity Accounting Inbound - Delivery Sheet Setup

## Overview
Step by step process of how-to setup delivery sheets within the Commodity Accounting module of the Levridge Environment. 

## Goal
By the end of this document, you will be able to setup delivery sheets within the Levridge Environment.

### Delivery Sheet Setup
The purpose for delivery sheets in the Levridge software is to group Inbound tickets together. You may want to group Inbound tickets together for multiple reasons a couple of examples would be to group by average grades together as a function or group tickets by farms or operations. The delivery sheet function is usually used minimally within the system. 

1.	Main menu > Modules > Inbound > Delivery > Delivery sheets 
    1. Once you are in the Delivery sheets program, you will see a listing of all the open delivery sheets. 
    2. You can filter by branch for easy sorting.
    3. You can use the Show completed toggle to show completed delivery sheets so if there have been any delivery sheets that have been completed and closed out you are able to view those.
    4. You can use the Show voided toggle to show voided delivery sheets.
2.	Create (+ New)
3.	Select Branch 
4.	Select Date
    1. Current date will be defaulted.
5.	Select Customer account
6.	Select Commodity 
7.	Select Customer operation
    1. Customer operation is required for this setup.
8.	Select Customer site
    1. This field is optional if you would like to attach a specific site to the operation.
9.	Select Split group
    1. The operation and site have a default split group attached to them and you can override that and change it if necessary.
10.	 Select Estimated start date
    1. This is an optional field.
    2. The idea behind the Estimated start date is that it allows the elevator to plan for future deliveries. 
11.	Input Estimated delivery quantity
    1. This is an optional field. 
12.	Select Unit of measure
    1. This will default from the Commodity chosen above.
13.	Click Create
14.	Delivery sheet is now setup in the system.
    1. Header information is based off the information input above.
    2. Operations and schedules
        1. Customer operation information that is attached to delivery sheet.
        2. Split group information that is attached to delivery sheet.
        3. Grade average schedule is used if you have the need to average grades within in the delivery sheet.
        4. Comments can be added to delivery sheet if necessary/applicable.
    3. Delivery sheet ownership splits
        1. You can add or remove ownership splits if necessary. You can add as many ownership splits as you would like but you need to ensure for each ownership split line you add, you complete the setup for each line.
        2. Default disposition – allows you to select what disposition tickets on this delivery sheet are applied to. 
        3. Default contract number – allows you to select what contract should be the default for all tickets added to the delivery sheet. This default contract number can be changed later in the process if necessary, to move tickets to another contract. Once you select the default contract number, the following fields will be populated: Default delivery period, Board price, Basis, Net price and Default fee schedule. 
    4. Delivery sheet completion details
        1. Once the delivery sheet has been completed, you are able to view how everything was applied and act as the record for the delivery sheet.






