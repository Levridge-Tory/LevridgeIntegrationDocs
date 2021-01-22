# Agronomy Sales Implementation Activities

## Overview
The following is an overview of the Agronomy Sales implementation activities.  
   
1. Enter setup data under Accounts Receivable > Setup > Agriculture (if not previously imported) 
	1. Customer operation types
	2. Customer site types
	3. Growing seasons
	4. Sales periods
	5. Lines of business
	6. Finance programs
	7. Seed and technology agreement compliance
	8. Dispatching accounts
2.	Enter setup data under Organization administration > Global address book > Relationship types
    1. Need to define a relationship from customer to customer operation

3.	Enter sales agreement classifications under Accounts Receivable > Setup > Sales agreement classifications

4.	Under General Ledger > Journal setup > Journal names set the Prepayment posting profile flag to identify journals used for customer prepayments

5.	Configure parameters under Accounts Receivable > Setup > Agriculture > Agriculture parameters

6.	Under Organization administration > Number sequences > Number sequences enter or generate number sequences

7.	Enter setup data under Accounts payable > Payment:
	1. Terms of payment - set prepayment fields
	2. Cash discounts - set prepayment fields
        1. Within cash discounts set up cash discount schedules
8.	Configure ag specific settings in Accounts Receivable > Setup > Accounts receivable parameters:
    1. Credit rating
    2. Credit limits
    3. Prices

9.	Enter vendor zones under Procurement and sourcing > Setup > Prices and discounts > Vendor zones

10.	Enter master data - involves a lot of client feedback
    1. Customers
       1. Ag specific settings are:
          1. Zone address
          2. Dispatching account id if using a 3rd party dispatching system (like AgSync)
          3. Seed and technology agreements
          4. Membership fast tab for patronage
          5. Taxation fast tab
          6. On customer addresses set ag taxes
          7. Billing notes
    2. Split groups
    3. Customer operations
    4. Customer sites
    5. Customer finance programs
    6. Vendors (if not the same as customers in the Ag parameters config form)
       1. On vendor addresses set ag taxes
    7. Rolling stock
       1. Cab configuration
       2. Drive train
       3. Equipment types
       4. Status
       5. Equipment reasons
       6. Equipment parameters
       7. Equipment
    8. Contacts
       1. Setup applicator licenses

11.	Enter indirect ag taxes under Tax > Indirect taxes > Sales tax:
    1.	Sales tax codes
    2.	Sales tax groups
    3.	Item sales tax groups
    4.	Sales tax settlement periods
    5.	Tax reasons

12.	Under Inventory management > Setup > Inventory breakdown setup sites and warehouse set ag tax values

13.	Prepare and enter products by setting up ag settings in:
    1.	Product information management > Setup > Categories and attributes > Category hierarchies
    2.	Accounts receivable > Setup > License and certification:
         1.	Certificate types
         2.	Certificates compliance
         3.	Regulated products
         4.	Restricted product regional lists
    3.	Feed and livestock > Setup > Veterinary feed directive (VFD):
         1.	Veterinary feed directive (VFD) drug groups
         2.	Veterinary feed directive (VFD) compliance
    4.	On released products, set the default order settings for each valid site and warehouse for the product
         1.	If using Kahler with this item, under Manage inventory on Action pane > Warehouse items > Set the dispensing method
    5.	On released products:
         1.	Assign regional lists
         2.	Assign drug groups
         3.	Assign active ingredients
         4.	Assign nutrients
         5.	If using scale - set flag to recognize the product as one that will be used at scale
         6.	If using TMS - under Transportation fast tab set enable TMS and identify the default carrier service
          viii.	Define ag specific settings on supplementary sales items
    6.	Setup up substitute items

14.	Under Accounts receivable > Setup > Trade agreement journals enter trade agreement journals including ag specific settings

15.	Define transfer order charges Under Inventory management > Setup > Transfer order charges

16.	If using Transportation management:
    1.	Configure TMS Parameters under Transportation management > Setup > Transportation management parameters
         1.	General > Vendor invoice
             1. Write vendor invoice journal - set to yes
             2. Assign vendor journal name
             3. Freight bill invoice text
         2.	General > Loads
             1. Set flags for when loads get created automatically
             2. Enable split of transfer order ship confirmation - set to yes if they want the ability to reverse shipment
         3.	General > Dispensing loads
             1. Set flags for when loads get created (Kahler integration only)
         4.	General > Freight reconciliation
             1. Enable freight reconciliation - set to yes
    2.	Configure data under Transportation management > Setup > Load building
    3.	Load templates
    4.	Equipment
    5.	Configure data under Transportation management > Setup > Carriers:
    6.	Carrier service codes
    7.	Mode
    8.	Transportation methods
    9.	Shipping carriers
         1.	Name - Specific structure required
         2.	Activate Carrier flag set to yes
         3.	Assign vendor account
         4.	Activate carrier rating - set to yes
         5. Services
         6.	Assign services
         7.	Rating profiles
    10.	Enter data under Transportation management > Setup > Rating
         1.	Carrier accessorial charge
         2.	Break master
         3.	Rate master (Rate base)
         4.	Rating profile
              1. Rating metadata
         5.	Miscellaneous charges
    11.	Enter data under Transportation management > Setup> Freight reconciliation
         1.	Reconciliation reasons
         2.	Freight bill type assignments
         3.	Audit master
    12.	Enter data under Transportation management > Setup > Bing map usage key (if using mapping which most clients will be doing)
    13. Enter data under Transportation management > Setup > Transportation standards
         1.	NMFC codes
         2.	LTL classes
    14.	Enter data under Transportation management > Setup > Engines
         1.	Mileage engine
         2.	Rate engine
         3. Transit time engine
         4.	Zone master

17.	Warehouse Management Configurations
    1.	Warehouse management > Setup > Warehouse > Warehouses
         1.	Warehouse > Use warehouse management processes – set flag to yes for all warehouses that will use TMS
    2.	Warehouse Management > Setup > Load posting methods > Regenerate methods (button)
    3.	Warehouse Management > Setup > Warehouse > Location formats
    4.	Configure one location format
    5.	Warehouse Management > Setup > Warehouse > Location types
         1. Configure two location types; Dock and User
    6.	Warehouse Management > Setup > Location profiles
         1.	Configure two profiles; Default and User
    7. Configure Warehouse management parameters under Warehouse management > Setup > Warehouse management parameters
          1. General > Assign location profile & Location Type
    8.	Warehouse Management > Setup > Load > Item load
          1. By item group indicate the load template id

18.	Under Inventory management > Setup > Agriculture > Agriculture parameters
    1.	Dispensing > Load template ID

19.	Under Accounts receivable > Setup > Agriculture > Agriculture parameters
    1.	Dispensing > Load template ID

20.	Under Product information management > Products > Released products
    1. Transportation > Use transportation management processes
    2.	Transportation > Carrier service
    3.	Manage Inventory > Net Weight

