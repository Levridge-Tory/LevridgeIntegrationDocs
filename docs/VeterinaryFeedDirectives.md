# Veterinary Feed Directives
Veterinary Feed Directives (VFDs) are prescriptions for antibiotics written by veterinarians for livestock.  The antibiotics specified in VFDs are dispensed in certain dosages for a herd and are placed/hosted with the feed given to livestock.  VFDs and the antibiotics with them are governed and restricted differently by the various states and countries. Levridge supports the legal tracking, creation and consumption of Veterinary Feed Directives (VFD) within host feed items.  

Prior to creating VFDs perform these initial system setup steps:

1. Create a VFD drug group

    - Feed and livestock > Setup > Veterinary feed directive (VFD) drug groups
    - Click New 
    - Enter a VFD group and description
    - Click Save

2. Create a restricted product regional list

    *Note* - An inclusive restricted product regional list needs to be created for each country before an exclusive list is created.

    - Product information management > Setup > Product compliance > Restricted products regional lists
    - Click New
    - Select a country, state, list ID and description.
    - In the Restricted list type field select Exclusive and save.

3. Create a restricted product which will host the active ingredient listed in the VFD

    - Product information management > Products > Released products
    - Select an item
    - In the Manage inventory action pane click Restricted products
    - Click New
    - Enter data and select the product regional list created earlier.
    - Save the new record.
    - Click Restricted VFD groups
    - Click New
    - Select the VFD group created earlier and save
    - Close the Restricted VFD groups form
    - In the released products form, go to the Active ingredient fast tab and enter an Active ingredient
    - Enter a rate like 4000 mg per 1 lb

4. Indicate what actions should happen when delivering and invoicing sales orders containing host items that have Active ingredients/antibiotics and there is not a valid VFD or if the customer's VFDs have been consumed

    - Feed and livestock > Setup > Veterinary feed directive (VFD) compliance
    - In the compliance form, mark the desired settings for enabling warnings and/or preventing postings for deliverying and invoicing orders

### To begin entering and consuming VFDs:

   - Create a VFD
   - Accounts receivable > Customers > All customers > Select the customer with a VFD > Agriculture > Veterinary feed directives
   - Click New
   - In the VFD drug group field, select the drug group set up earlier
   - Enter the customer operation the VFD is written for
   - Enter values for the prescription name, issued and expiration dates, dosage quantity and unit, number of head and head quantity.  

If desired, to determine the rate of consumption of the active ingredient:

   - In the Dosage calculator section of the VFD form, enter values for the rate, base weight and herd average weight and click the Calculate dosage button.

If desired, to quickly create a sales order for this VFD:

   - Click the Create sales order button in this VFD form and in the dialog that opens fields will be defaulted from the VFD.
   - In the Items section of the dialog, click the ellipses button (three dots) and click Find items.
   - The Items grid will be populated with all the possible host products for the active ingredient/antibiotic in the VFD.  In the grid on the line for the desired host product, enter the quantity of the host product to consume.
   - Click OK and a new sales order will be created.

### To consume the VFD

   - Accounts receivable > Orders > All sales orders
   - Click New and enter values including the customer operation the VFD is written for
   - On the sales order line, create a new line and select the restricted product created earlier that is a host for the active ingredient in the VFD
   - Enter a quantity for the selected item.  

Once the quantity is entered, the VFD created for the current customer operation will be defaulted onto the sales line.  When the sales order is delivered, the VFD will be consumed according to the quantity on the sales line and the rate of active ingredient specified on the item.  If an active, valid VFD does not exist for the customer operation, a warning or error will be presented based on the settings specified earlier.
