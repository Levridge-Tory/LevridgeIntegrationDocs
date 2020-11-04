# Vendor Purchasing Rebates
Levridge has expanded vendor rebate collection from the manufacturer or distributor based on the sales and purchases they make. Rebates may be cumulated using thresholds or by tagging a product or vendor with multiple rebate groups.

## Vendor Rebate Group
A link has been added to the vendor for access to the vendor rebate table. This will allow the user to select the vendor rebate groups that need to be associated with that vendor.

The vendor rebate group now includes a ‘Vendor Selection’ option that shows all vendors assigned to the selected vendor item rebate group. Vendors may be added or removed from the group.

## Item Rebate Group
A link has been added to the item release for access to the item rebate table. This will allow the user to select the item rebate groups that need to be associated with that item.

The item rebate group now includes an ‘Item Selection’ option to show all products assigned to the selected vendor item rebate group. Products may be added or removed from the group.  Product dimensions may also be displayed. 

## Product Master
A field has been added to store the rebate redemption price. This price is used to calculate rebates and is provided by the vendor.

## Rebate Agreement
The rebate agreement defines parameters that trigger the cumulation of rebates. The agreement parameters include:

- Drop down option for sales order invoices or purchase order invoices
- Switch to allow retroactive rebate as needed
- Switch that looks at items in an item rebate group and if multiple items from a group are purchased, the percentage of rebate will be based off how many products are listed determining the correct percentage.
- Switch for ‘Use redemption price’, new field on product master.

Upon creation of a vendor rebate agreement, the default expiry date of never has been changed to one year following the start date. The user has the option to update the expiry date.

## Brand Pairing
Brand pairing allows rebate records provided by vendors for the purchase of items from two or more brands or manufacturers.  

- Items may be added to vendor rebate item groups that represent the brand to which they belong.
- The Item Selection feature currently available in Vendor Rebate Agreements will be re-purposed as a Vendor Item Rebate Group Selection. (This will allow multiple Vendor Item Rebate Groups to be assigned to a single Vendor Rebate Agreement.) 
- Rebate Agreement form will be modified to enable and disable specific features that support rebates associated with Brand Pairing. 
- Rebate Cumulation will be modified to evaluate the number of Pairs selected during the Cumulation Period and apply that information to the rebate calculation.

## Rebate Process
Once the rebate agreements are setup up properly, every time a Purchase order or sales order is invoiced, the rebate will show up in the accrual account as well as in the Rebate claims screen.  

A rebate claims screen will provide details of rebates processed.  Processing from the claims will create a credit on the vendors account that can be left as a credit or settled against the payment from the 

