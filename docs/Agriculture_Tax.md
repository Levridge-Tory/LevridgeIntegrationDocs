# Agriculture Tax Calculation
Functionality has been added to support the calculation of agricultural taxes.

## Feature Summary:

- **Multi-Taxing:** Made it possible for Customers, Vendors, Addresses and Items to be assigned multiple tax groups. Taxation is determined based on the intersection of assigned tax types and groups between Items and the relevant Customers, Vendors and/or Addresses.


## Multi-Taxing

Levridge allows users to assign a Customers, Vendors and Items to multiple tax groups, to support agricultural tax calculations. Customers can also have different Agricultural Tax Groups assigned at the address level to facilitate taxation for multiple delivery locations.

Agricultural Taxes are categorized into one of three different Agricultural Tax Types:

1. Tonnage Tax
2. Pesticide Tax
4. Indemnity Fund

Agricultural Sales Tax tables have been added to the Customer, Vendor, Address and Item forms to allow for assignment of the applicable Agricultural Tax Groups. 

- Items can be assigned one Item Sales Tax Group from each of the four Agricultural Tax Types. 
- Customers, Vendors, and Addresses can be assigned as many Sales Tax Groups from each of the Agricultural Tax Types as needed.

In addition to standard sales tax calculation, each Sales Order or Purchase Order line can be subject to one of each of the above Agricultural Tax Types. The applicable tax groups are assigned by identifying matching tax groups between the Item and the Customer (or Vendor) information on the order. All matching tax groups will be applied.


