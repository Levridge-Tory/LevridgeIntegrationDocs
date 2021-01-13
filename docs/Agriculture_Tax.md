# Agriculture Tax Groups
Functionality has been added to support the calculation of agricultural taxes.

## Multi-Taxing

Levridge allows users to assign multiple agriculture tax groups to Customers, Customer addresses, Vendors, Vendor addresses, and Items.

   - Items can be assigned one Item Sales Tax Group from each of the four Agricultural Tax Types.
   - Customers, Vendors, and the addresses can be assigned as many Sales Tax Groups from each of the Agricultural Tax Types as needed.


Agricultural Taxes are categorized into one of three different Agricultural Tax Types:

1. Tonnage Tax
2. Pesticide Tax
4. Indemnity Fund

In addition to standard sales tax calculation, each Sales Order or Purchase Order line can be subject to one of each of the above Agricultural Tax Types. The applicable tax groups are assigned by identifying matching tax groups between the Item and the Customer (or Vendor) information on the order. All matching tax groups will be applied.




