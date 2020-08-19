# Customer Operations, Customer Sites and Split Groups


## Overview
The following provides an overview of customer operations, customer sites and split groups in Levridge. Customer operations and sites are master data concepts in Levridge.  They are defined as: 

- Account/Customer: A farm or production organization
- Customer operation: A farm or livestock operation 
- Customer site: A field or barn 
- Customer site location: A zone in a field or a pen in a barn
- Contact: Members of a farm or livestock organization.  These contacts can be involved in the organization in different ways.  For example, a veterinarian or farm hand might be contacts for a farm.

An account or customer is who the ag retailer does business with.  This party is often referred to as the grower.  This party has the financial responsibilities with the Ag retailer.

The customer operation is the business entity the account or customer participates in.  A customer might be part of multiple customer operations.  Products and services are exchanged between the Ag retailer and the customer and the operation the customer is participating in.  In Levridge, an Ag retailer could provide feedback in the form of a return on investment (ROI) or balance sheet to the grower based on information delivered to a specific customer operation. Historical information can also be tracked to individuals assigned to or working on the specific operation (ex: agronomist, feed salesperson, tractor driver). This is helpful for corporate farms to be able to break down who is handling what operation. 

A customer site is a subset of a customer operation.  A customer operation might have many customer sites/fields.  Data is stored on customer sites and tasks are performed against the sites.  

For example, the following information can be tracked on a customer site: 
- Farmable Acres – used in calculations of seed requirements and fertilizer amounts
- County, Township, Plat, etc.
- Field Photo
- Crop History
- Commodity varieties and yields over time
- Pest pressures

The following example tasks that can be performed against customer sites:
- Applications – track all applications per growing season
- Soil Samples – track all sampling activity

As a customer operation can have several customer sites, within the animal feed space, customer sites can have several customer site locations. For example, a barn can have several bins. 

## Split Groups
Split groups (commonly referred to as splits) are the link between customers and customer operations. Split groups define how to allocate costs or revenue across the one or more customers involved in the split.  For example, if there are 3 different participants involved in a single customer operation, the split group might look like this:

    Customer A – 40%
    Customer B – 30%
    Customer C – 30%

Default split groups can be defined for ordering purposes and for commodity interactions with the Ag retailer.  These default splits can be set on customer operations or on each customer site which means, if desired, each field can have a different default split group.  Default split groups can also be defined at the item category or product level as well. 

In Levridge, there are two different types of default split groups: 
1. Ordering split
2. Commodity split

The Commodity default split defines ownership of products when the grower is selling to the Ag retailer. The Ordering default split is used when the grower is buying products from the Ag retailer (that will be utilized in customer sites and operations). 

Here is [How to Create a Split Group in F&O](./Create-Split-Group-in-F&O.md) and information on how to [Manage Splits, Sales Contracts and Prepayments](./ManagingSplits_SalesContracts_Prepayments.md). 

