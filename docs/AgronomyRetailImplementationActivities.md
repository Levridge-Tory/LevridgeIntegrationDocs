# Agronomy Retail Implementation Activities


## Overview
The following is an overview of the Agronomy Retail implementation activities.  
   
1. Enter setup data under Accounts Receivable > Setup > Agriculture (if not previously imported) 
	a. Customer operation types
	b. Customer site types
	c. Growing seasons
	d. Sales periods
	e. Lines of business
	f. Finance programs
	g. Seed and technology agreement compliance
	h. Dispatching accounts
2.	Enter setup data under Organization administration > Global address book > Relationship types
	a. Need to define a relationship from customer to customer operation
3.	Enter sales agreement classifications under Accounts Receivable > Setup > Sales agreement classifications
4.	Under General Ledger > Journal setup > Journal names set the Prepayment posting profile flag to identify journals used for customer prepayments
5.	Configure parameters under Accounts Receivable > Setup > Agriculture > Agriculture parameters
6.	Under Organization administration > Number sequences > Number sequences enter or generate number sequences
7.	Enter setup data under Accounts payable > Payment:
	a. Terms of payment - set prepayment fields
	b. Cash discounts - set prepayment fields
        i. Within cash discounts set up cash discount schedules
8.	Configure ag specific settings in Accounts Receivable > Setup > Accounts receivable parameters:
    a. Credit rating
    b. Credit limits
    c. Prices
9.	Enter vendor zones under Procurement and sourcing > Setup > Prices and discounts > Vendor zones
10.	Enter master data - involves a lot of client feedback
    a. Customers
       i. Ag specific settings are:
          1. Zone address
          2. Dispatching account id if using a 3rd party dispatching system (like AgSync)
          3. Seed and technology agreements
          4. Membership fast tab for patronage
          5. Taxation fast tab
          6. On customer addresses set ag taxes
          7. Billing notes
    b. Split groups
    c. Customer operations
    d. Customer sites
    e. Customer finance programs
    f. Vendors (if not the same as customers in the Ag parameters config form)
       i. On vendor addresses set ag taxes
    g. Rolling stock
       i. Cab configuration
       ii. Drive train
       iii. Equipment types
       iv. Status
       v. Equipment reasons
       vi. Equipment parameters
       vii. Equipment
    h. Contacts
       i. Setup applicator licenses
11.	Enter indirect ag taxes under Tax > Indirect taxes > Sales tax:
    a. Sales tax codes
    b.	Sales tax groups
    c.	Item sales tax groups
    d.	Sales tax settlement periods
    e.	Tax reasons
12.	Under Inventory management > Setup > Inventory breakdown setup sites and warehouse set ag tax values
13.	Prepare and enter products by setting up ag settings in:
    a. Product information management > Setup > Categories and attributes > Category hierarchies
    b. Accounts receivable > Setup > License and certification:
      i. Certificate types
      ii. Certificates compliance
      iii. Regulated products
      iv. Restricted product regional lists
    c. Feed and livestock > Setup > Veterinary feed directive (VFD):
       i. Veterinary feed directive (VFD) drug groups
       ii. Veterinary feed directive (VFD) compliance
    d. On released products, set the default order settings for each valid site and warehouse for the product
       i. If using Kahler with this item, under Manage inventory on Action pane > Warehouse items > Set the dispensing method
    e. On released products:
        - Assign regional lists
        - Assign certificates
        - Assign drug groups
        - Assign active ingredients
        - Assign nutrients
        - If using scale - set flag to recognize the product as one that will be used at scale
        - If using TMS - under Transportation fast tab set enable TMS and identify the default carrier service
        - Define ag specific settings on supplementary sales items
       i. Setup up substitute items
14.	Under Accounts receivable > Setup > Trade agreement journals enter trade agreement journals including ag specific settings
15.	Define transfer order charges Under Inventory management > Setup > Charge codes
16.	If using Transportation management:
    a. Configure TMS Parameters under Transportation management > Setup > Transportation management parameters
       i. In the parameters form choose to Initialize base engine data
    b. Configure data under Transportation management > Setup > Load building
       i. Load templates
       ii. Equipment
    c. Configure data under Transportation management > Setup > Carriers:
       i. Carrier service codes
       ii. Mode
       iii. Transportation methods
    d.	Enter data under Transportation management > Setup > Rating
        i.	Carrier accessorial charge
        ii.	Break master
        iii. Rate master
        iv. Rating profile
        v. Rating metadata
        vi. Miscellaneous charges
    e. Enter data under Transportation management > Setup> Freight reconciliation
         i.	Reconciliation reasons
        ii.	Freight bill type assignments
        iii.	Audit master
    f. Enter data under Transportation management > Setup > Bing map usage key (if using mapping which most clients will be doing)
    g. Enter data under Transportation management > Setup > Transportation standards
        i. NMFC codes
        ii.	LTL classes
    h. Enter data under Transportation management > Setup > Engines
        i. Mileage engine
        ii. Rate engine
        iii. Transit time engine
        iv. Zone master
    i. Enter shipping carriers under Transportation management > Setup > Carriers > Shipping carriers
       i. On the carriers define services, addresses and rating profiles and assign the shipping carrier to a vendor account
