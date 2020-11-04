# Agriculture Tax Calculation and Payments
Functionality has been added to support the calculation ad payment of agricultural taxes in addition to that of standard Sales Tax.

## Feature Summary:

- **Multi-Taxing:** Made it possible for Customers, Vendors, Addresses and Items to be assigned multiple tax groups. Taxation is determined based on the intersection of assigned tax types and groups between Items and the relevant Customers, Vendors and/or Addresses.
- **Customer Use Tax:** Implemented the ability to accrue tax amounts on a Sales Invoice based on a specific product, where calculated tax is not part of the amount due from the Customer.
- **Tax Basis:** Product Composition: Created tax rules to address taxation based on the percentage of a Product’s chemical composition.
- **Tax Basis:** Percentage of Gross Sales: Created tax rules to address taxation based on the percentage of gross sales on a sales order (total price, prior to discount).
- **Min/Max Tax Thresholds and License Fees:** Incorporated a minimum or maximum payable amount into the Tax Settlement Period.
- **Grain Settlements:** Allow for the reduction of a payable by the amount of assessed tax.

## Multi-Taxing

Levridge allows users to assign a Customers, Vendors and Items to multiple tax groups, to support agricultural tax calculations. Customers can also have different Agricultural Tax Groups assigned at the address level to facilitate taxation for multiple delivery locations.

Agricultural Taxes are categorized into one of four different Agricultural Tax Types:

1. Tonnage Tax
2. Pesticide Tax
3. Check-Off Fees
4. Indemnity Fund

Agricultural Sales Tax tables have been added to the Customer, Vendor, Address and Item forms to allow for assignment of the applicable Agricultural Tax Groups. 

- Items can be assigned one Item Sales Tax Group from each of the four Agricultural Tax Types. 
- Customers, Vendors, and Addresses can be assigned as many Sales Tax Groups from each of the Agricultural Tax Types as needed.

In addition to standard sales tax calculation, each Sales Order or Purchase Order line can be subject to one of each of the above Agricultural Tax Types. The applicable tax groups are assigned by identifying matching tax groups between the Item and the Customer (or Vendor) information on the order. All matching tax groups will be applied.

## Customer Use Tax
Certain agricultural taxes do not create a liability on the part of the consumer and cannot be include as charges on the Customer Invoice. To support this requirement, Levridge allows Sales Tax Codes to be designated as “Customer Use Tax”. 

When flagged as “Customer Use Tax,” the Agricultural Tax will calculate on a Sales Order line based on the specifications in the Sales Tax Code, but those tax amounts will not appear as charges on the Sales Invoice.

Specific General Ledger Accounts can be specified for posting of Customer Use Tax, and payments to tax authorities will be settled using standard Tax Settlement functionality.
## Tax Basis: Product Composition 
Some states require that a fee be remitted based on the percentage content of certain product components (such as nitrogen content in fertilizers and soil conditioners). Levridge has enhanced the Released Product to include a new “Nutrients” fast tab to record the type and percentage of nutrients included in the product.

Levridge has also enhanced Tax to provide a new tax calculation for “Net amount per unit - % unit attribute.” Tax will then be calculated based on the percentage of the nutrient specified on the tax code.

## Tax Basis: Percentage of Gross Sales 
Some agricultural taxes are calculated as a percentage of gross sales. Levridge has added a new tax calculation to support this requirement.

Sales Tax Codes configured with this basis will calculate tax based on product list price, prior to application of any discounts.

## Min/Max Thresholds and License Fees
To support the payment of license fees or flat amounts that are payable for a specific time period, Levridge has enhanced the Sales Tax Settlement Periods to include optional fields for a Minimum Tax amount and a Maximum Tax Amount.

If the Minimum Tax field is populated, the amount to be settled will always be either the Minimum Tax amount or the actual tax calculated – whichever is greater.

If the Maximum Tax field is populated, the amount to be settled will always be either the Maximum Tax amount or the actual tax calculated – whichever is less.

If these fields are left blank, Sales Tax will be calculated and settled according to actual values posted.
## Grain Settlements
Levridge has implemented a new “Reduction in Payable” setting on the Sales Tax Code. When enabled, this setting will reduce the amount of a payment issued to a vendor by the tax amount. The tax will be recorded as a liability. The payment will be remitted to the tax authority rather than the vendor collecting and remitting the tax.

