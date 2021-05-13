# Customer Operations, Customer Sites and Split Groups


## Overview
The following provides an overview of customer operations, customer sites and split groups in Levridge. Customer operations and sites are master data concepts in Levridge.  They are defined as: 

- Account/Customer: A farm or production organization
- Customer operation: A farm or livestock operation 
- Customer site: A field or barn 
- Customer site location: A zone in a field or a pen in a barn
- Contact: Members of a farm or livestock organization.  These contacts can be involved in the organization in different ways.  For example, a veterinarian or farm hand might be contacts for a farm.

An account or customer is who the ag retailer does business with.  This party is often referred to as the grower.  This party has the financial responsibilities with the Ag retailer.

### Customer Operation
The customer operation is the business entity the account or customer participates in.  A customer might be part of multiple customer operations.  Products and services are exchanged between the Ag retailer and the customer and the operation the customer is participating in.  In Levridge, an Ag retailer could provide feedback in the form of a return on investment (ROI) or balance sheet to the grower based on information delivered to a specific customer operation. Historical information can also be tracked to individuals assigned to or working on the specific operation (ex: agronomist, feed salesperson, tractor driver). This is helpful for corporate farms to be able to break down who is handling what operation. 

Customer operations are a way to organize and track how your growers organize and manage their business.  This could be a farm.  Accounts and people with financial responsibility can change, but data is tied to one spot.  Grower/farm/field or Ranch/barn/bin is standard, however Levridge offers the flexibility to allow grower to have breakdown with different operation types with lines of business including agronomy, livestock, energy uses, etc.   For example, a farm may be broken down by different managers, therefore creating different operations.  Another example, a customer may have operations for crops versus cattle.  Or a hog operation with different locations and multiple barns, may define each barn as an operation.

A farm may be owned by a father, mother, with some fields that are rented.  This helps to control dividends or patronage by operation.  Levridge permits you to mirror within the system the structure of your grower’s operation.  A default for ordering split group and commodity split group may be setup under the customer operation. 

Customer operations allow the ability to create a customized profit/loss statement by customer operation.

The setup of customer types resides at:

- FinOps>Accounts Receivable>Setup>Agriculture>Customer operation types
- Types may be viewed in CE at CE>Core>Configuration>Customer Operation Types

The setup of the customer operations resides at:

- FinOps>Accounts Receivable>Customers>All Customers>Agriculture>Operations
- Operations may be viewed in CE at CE>Agronomy>Customer Operations

### Customer Site
A customer site is a subset of a customer operation.  A customer operation might have many customer sites/fields.  Data is stored on customer sites and tasks are performed against the sites.  Customer sites represent the main transactional point in Levridge and defines a breakdown of an operation.  For example, this could represent fields (customer sites) within a farm (customer operation) or pens (customer sites) within a barn (customer operation). The customer site may represent the field, barn, feed lot or pasture.  

Customer sites include the following information:

- Address, legal description, and geo points details 
- Tracking of field boundaries and data layers (field maps with product detail)
- Default ordering split groups tied to allow splitting of revenue and cost
- Contacts may be defined for quick point of contact when deliver feed, etc.
- Historical data, some of which is also tracked in CE including yields, crop history, & pest pressure.  
- Ability to create a customized profit/loss statement by customer site

The following example tasks that can be performed against customer sites:

- Applications – track all applications per growing season
- Soil Samples – track all sampling activity

As a customer operation can have several customer sites, within the animal feed space, customer sites can have several customer site locations. For example, a barn can have several bins. 

### Customer Site Locations
This depends on the type of site.  For example, if the site is a field, then the field can be split into halves or thirds based on productivity.  Different seed or fertilizer.  Allows work orders to be stored by subsection of a field.

There may be a barn, site locations would represent pens within the barn.  For delivery of feed. Physical field or piece of dirt could include grain bins – site location allows tracking of the seed, etc.

### Territory
Entity, or way to assign sales people or company sites, for commission and reporting purposes onto a customer operation.  For example, if I am an agronomist that is covering 40 different operations, it is a way to quickly link for reporting purposes.  Can breakout sales and other analytics.

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

Splits allow the percentage of financial responsibility to be recognized for relationships on sales orders or in CE through proposal or batch.  

Splits may be defined by partnerships, renters, or by family relationships (father/son). Splits also identify the customer to receive any rounding value.  Levridge handles splits uniquely due to customer structure.  Most are rigid, however customer operations will allow splitting of revenue and costs.  

The function that allows you to view and maintain all split groups is at F&O>Accounts Receivable>Setup>Agriculture>Split Groups OR CE>Agronomy or Core>Split Groups.

All the split groups that a customer is participating in may be viewed and maintained under the customer account. Go to F&F>Accounts Receivable>Customer>All Customers>Agriculture>Split Group.

Split Group setups are synced between F&O and CE.

Within the split group setup, each line will define a customer account, the percentage applied to the customer account and which customer will receive rounding. 

The setups include a ‘Where Used’ view that displays all records related to the split group such as customer operations or sales orders.


Here is [How to Create a Split Group in F&O](./Create-Split-Group.md) and information on how to [Manage Splits, Sales Contracts and Prepayments](./ManagingSplits_SalesContracts_Prepayments.md). 

