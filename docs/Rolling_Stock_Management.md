# Rolling Stock Management

## Overview
The rolling stock module addresses the gap between the fixed assets and operational equipment management dashboarder module. Rolling stock is fixed assets on wheels such as trucks, application equipment, etc. With rolling stock you can track what the equipment is, where it is located, when it was last serviced, when the license or insurance is due, what the equipment’s weight is, with or without product, and lastly, who is the equipment assigned to. The tracking will assist with the recognition of revenue and expenses, tracking for maintenance and location of the equipment assets. Fleet tracking captures information from the scale application, work order, and third-party dispatching application. 

Fixed Assets – geared towards managing assets that we find on a balance sheet typically managed by the accounting staff.

Rolling Stock – geared towards operational management of large volumes of equipment typically managed by the operational staff.

### Fixed Asset to Rolling Stock Integration

This integration allows an accountant to go ahead and start the setup of a fixed asset and then copy some of those elements of that setup over into a pending status piece of rolling equipment that then the operations team can pickup and add additional details and maintain those records separately from the fixed assets.  

#### Setup of a Fixed Asset

1. Fixed assets > Fixed assets > Fixed assets
2. Create new fixed asset (+New)
3. Assign Fixed asset group
4. Input number – in most environments you would have a number sequence that would automatically assign your fixed assets, but you can also manually input this number as well. 
5. Input name 
6. Input Make 
7. Input Model 
8. Input Model year
9. Input Serial number – this is mapped to a vehicle vin number. 
10.	Input Asset condition – this is mapped over. Typically, this field would be used if you bought something new or used or want to list condition.

    **Note:** The accountant or the person that manages fixed assets could input any additional information that they would like to store for that fixed asset.

11. Rolling Stock Flag - when turned to *yes* this is what copies the data from the fixed asset over to the rolling stock module. 
12. Save

    **Note:** Once you have saved the fixed asset, if you scroll to the reference and notes section, the Copied to Rs list is populated with the date you created the new rolling stock item based off the date a copied from the fixed asset record.

#### Rolling Stock Module

1.	Rolling stock > Equipment > Pending equipment
2.	Open the rolling stock record you would like to make updates to 
3.	Update status
      - Active – allows the equipment to be used transactionally and will also show this piece of equipment in a financial dimension
      - Inactive
      - Pending 
      - Retired
4.	Input Equipment type 
5.	Capture License plate number (if appliable) 
6.	Input Issuing state 
7.	Input Issuing county 
8.	Input License expiration date 
9.	Input notes (if applicable) 
10.	Input Equipment color
11.	Input Cab configuration 
12.	Input door number
13.	Input Drivetrain
14.	Designate Owning branch – what location is accountable for this piece of equipment
15.	Input Vehicle tare weight 
16.	Input Tare unit of measure 
17.	Input Licensed weight – this weight is the basis for license fees 
18.	Input Licensed weight unit of measure
19.	Input License fee
20.	Input Capacity
21.	Input unit of measure for capacity 
22.	Input Mileage 
23.	Input Mileage updated 
24.	Designate if GPS is enabled 
25.	Assign financial dimension 
26.	Save

#### Linking Fixed Asset Number to Rolling Rock

Sometimes what may occur is a piece of equipment is brought in and may be leased or may be bought later, so it is not listed as a fixed asset yet. We do have the ability to take a piece of rolling stock and link it to a fixed asset number. 

1. Rolling Stock > Equipment > All equipment  
2. Select applicable equipment 
3. References and notes > Fixed asset reference > Fixed asset number

    **Note:** You can go back and link the equipment even though the fixed asset was not already created. 

4. Select fixed asset number that should be linked to equipment 

    **Note:** When a fixed asset is created through the procurement process, the Vendor number and Purchase order fields would be populated in the references and notes section for that piece of equipment.

#### Equipment Parameters

We can configure our rolling stock so that disposal of the fixed asset would automate the disposal and status change of the linked rolling stock. 

1. Rolling stock > Setup > Equipment parameters
2. General tab
3. Designate Automatic disposal 
      - Yes
      - No
4. Designate Disposal status
5. Designate Disposal reason code 

    **Note:** This is an optional configuration, and the status and reason codes would be defined/created for that specific organization’s need. 

### Tracking Temporary Transfers or Equipment Loans

#### Loaning Equipment Out

1.	Create new loan of equipment (+New)
2.	Input Rolling stock ID 
3.	Input Borrowing branch – where it is being loaned to 
4.	Add any applicable notes to record – i.e. expected date of return 

    **Note:** You will be able to view who the record was created by and the date and time it was recorded. 

5. This record will show in the list of things that are in process 

#### Check Equipment Back In

1. Select line of equipment that is being returned 
2. Click on Equipment returned in header 
3. Add comment to the Complete loan form
4. Input date that equipment was returned
5. Click OK 

