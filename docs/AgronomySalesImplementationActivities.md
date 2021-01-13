# Agronomy Sales Implementation Activities

## Overview
The following is an overview of the Agronomy Sales implementation activities.  
   
1. Enter setup data under Accounts Receivable > Setup > Agriculture (if not previously imported) 

    - Customer operation types
    - Customer site types
    - Growing seasons
    - Sales periods
    - Lines of business
    - Finance programs
    - Seed and technology agreement compliance
    - Dispatching accounts

2.	Enter setup data under Organization administration > Global address book > Relationship types

	- Need to define a relationship from customer to customer operation

3.	Enter sales agreement classifications under Accounts Receivable > Setup > Sales agreement classifications

4.	Under General Ledger > Journal setup > Journal names set the Prepayment posting profile flag to identify journals used for customer prepayments 

5.	Configure parameters under Accounts Receivable > Setup > Agriculture > Agriculture parameters 

6.	Under Organization administration > Number sequences > Number sequences enter or generate number sequences 

7.	Enter setup data under Accounts payable > Payment:

	- Terms of payment - set prepayment fields
	- Cash discounts - set prepayment fields
        - Within cash discounts set up cash discount schedules

8.	Configure ag specific settings in Accounts Receivable > Setup > Accounts receivable parameters:

    - Credit rating
    - Credit limits
    - Prices

9.	Enter vendor zones under Procurement and sourcing > Setup > Prices and discounts > Vendor zones

10.	Enter master data - involves a lot of client feedback

    - Customers

        - Ag specific settings are:

          1. Zone address
          2. Dispatching account id if using a 3rd party dispatching system (like AgSync)
          3. Seed and technology agreements
          4. Membership fast tab for patronage
          5. Taxation fast tab
          6. On customer addresses set ag taxes
          7. Billing notes

    - Split groups
    - Customer operations
    - Customer sites
    - Customer finance programs
    - Vendors (if not the same as customers in the Ag parameters config form)

        - On vendor addresses set ag taxes

    - Rolling stock

        - Cab configuration
        - Drive train
        - Equipment types
        - Status
        - Equipment reasons
        - Equipment parameters
        - Equipment

    - Contacts

        - Setup applicator licenses
 
11.	Enter indirect ag taxes under Tax > Indirect taxes > Sales tax:

    - Sales tax codes
    - Sales tax groups
    - Item sales tax groups
    - Sales tax settlement periods
    - Tax reasons

12.	Under Inventory management > Setup > Inventory breakdown setup sites and warehouse set ag tax values

13.	Prepare and enter products by setting up ag settings in:

    - Product information management > Setup > Categories and attributes > Category hierarchies
    - Accounts receivable > Setup > License and certification:
      
        - Certificate types
        - Certificates compliance
        - Regulated products
        - Restricted product regional lists
   
    - Feed and livestock > Setup > Veterinary feed directive (VFD):

        - Veterinary feed directive (VFD) drug groups
        - Veterinary feed directive (VFD) compliance

    - On released products, set the default order settings for each valid site and warehouse for the product

        - If using Kahler with this item, under Manage inventory on Action pane > Warehouse items > Set the dispensing method

    - On released products:

        - Assign regional lists
        - Assign certificates
        - Assign drug groups
        - Assign active ingredients
        - Assign nutrients
        - If using scale - set flag to recognize the product as one that will be used at scale
        - If using TMS - under Transportation fast tab set enable TMS and identify the default carrier service
        - Define ag specific settings on supplementary sales items

     - Setup up substitute items

14.	Under Accounts receivable > Setup > Trade agreement journals enter trade agreement journals including ag specific settings

15. Define transfer order charges Under Inventory management > Setup > Transfer order charges 

16.	If using Transportation management:

    - Configure TMS Parameters under Transportation management > Setup > Transportation management parameters

        - General > Vendor invoice
 
            - Write vendor invoice journal - set to yes
            - Assign vendor journal name
            - Freight bill invoice text

        - General > Loads

            - Set flags for when loads get created automatically
            - Enable split of transfer order ship confirmation - set to yes if they want the ability to reverse shipment
 
        - General > Dispensing loads
 
            - Set flags for when loads get created (Kahler integration only)

        - General > Freight reconciliation

            - Enable freight reconciliation - set to yes

    - Configure data under Transportation management > Setup > Load building

       - Load templates
       - Equipment

    - Configure data under Transportation management > Setup > Carriers:

       - Carrier service codes
       - Mode
       - Transportation methods

     - Shipping carriers

         - Name - Specific structure required 
         - Activate Carrier flag set to yes
         - Assign vendor account
         - Activate carrier rating - set to yes
         - Services
         - Assign services
         - Rating profiles

    - Enter data under Transportation management > Setup > Rating

        - Carrier accessorial charge
        - Break master
        - Rate master (Rate base)
        - Rating profile
        - Rating metadata
        - Miscellaneous charges

    - Enter data under Transportation management > Setup> Freight reconciliation

        - Reconciliation reasons
        - Freight bill type assignments
        - Audit master

    - Enter data under Transportation management > Setup > Bing map usage key (if using mapping which most clients will be doing)

    - Enter data under Transportation management > Setup > Transportation standards

        - NMFC codes
        - LTL classes

    - Enter data under Transportation management > Setup > Engines

        - Mileage engine
        - Rate engine
        - Transit time engine
        - Zone master

17.	Warehouse Management Configurations

    - Warehouse management > Setup > Warehouse > Warehouses

        - Warehouse > Use warehouse management processes – set flag to yes for all warehouses that will use TMS

    - Warehouse Management > Setup > Load posting methods > Regenerate methods (button)
    - Warehouse Management > Setup > Warehouse > Location formats
 
       - Configure one location format

    - Warehouse Management > Setup > Warehouse > Location types

        - Configure two location types; Dock and User

    - Warehouse Management > Setup > Location profiles

        - Configure two profiles; Default and User

    - Configure Warehouse management parameters under Warehouse management > Setup > Warehouse management parameters

        - General > Assign location profile & Location Type

    - Warehouse Management > Setup > Load > Item load

        - By item group indicate the load template id
 
18.	Under Inventory management > Setup > Agriculture > Agriculture parameters

     - Dispensing > Load template ID
 
19.	Under Accounts receivable > Setup > Agriculture > Agriculture parameters

    - Dispensing > Load template ID
 
20.	Under Product information management > Products > Released products

    - Transportation > Use transportation management processes
    - Transportation > Carrier service 
    - Manage Inventory > Net Weight

