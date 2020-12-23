# Agronomy Processes

## Overview
There are three distinct end-to-end business processes in which Agronomists will participate.

1. *Field Plan to Agronomy Contract* - A set of sales tools within CE used to price product and transition growers into contracts.
2. *Fertilizer Calculation* - A utility that allows a salesperson to determine and calculate fertilizer requirements such as what product best fits the need of the customer and how much of that product is needed to fulfill the order (some work order is still needed and is anticipated to be ready in Fall 2020).
3. *Sales Order Management* - The integration of all Levridge pieces, specifically split billing, and its close integration with sales orders in F&O. 

## Field Plan to Agronomy Contract
There are three methods for kicking off a field plan to agronomy contract with Dynamics 365 CE: 

1. <strong>*[Batch plans](#batch-plans)*</strong> [^10]
2. Regular plans
3. Proposals

### Batch Plans
Batch plans are a way to quickly create a proposal or sale agreement. 
<strong>*There are three types of batch plans that can be used:*</strong>   [^1]

- Field type – <strong>*The field batch plan type is used to ...*</strong> [^2]
  All product needs across all fields may be added as a batch.  
  Individual products can then be added after the plan is created.  For example, 
  fertilizer, and chemical may be the same for all fields, <strong>*with the seed added to 
  different areas of the field after the batch process.  Required to know field details, but not customer.*</strong> [^3] 
- Prospect type – Potential customer information is added to capture pricing for products in a proposal to provide to the prospect.  
  Limitations include not able to move proposal to a contract.  This is a draft proposal for beginning negotiation.
- Customer type – Does not require field details.  Creates proposal for seed, fertilizer or crop protection as needed.

You can generate a proposal or go directly to a sales agreement for the field and customer types.
<strong>*The prospect type ...*</strong>[^2]

To use the batch plan method to create an agronomy contract:
1. Select the Bath Plans tab
2. Select Generate new
3. Populate required fields
    - Name: this field will auto populate when you click save
    - Proposal Type: there are three proposal types: Customer, Field, Prospect. The default proposal type is Customer.
    - Customer Operation
    - Split Group
    - Sales Period: Needed to accurately price
4. Select Save
5. Select the Programs tab
6. Populate fields:
    - Farmable Acreage: This field is required
    - Preconfigured set of products: 
      In many cases on agronomist recommends the same products at the same time so 
      instead of calculating these rates each time, you can set up a program so it 
      automatically calculates product and rate.
6. Add products utilizing the tabs across the top of the batch plan (seed, fertilizer, chemical, etc.)
7. After adding your products, you can either:
    - Generate a proposal
    - Generate a sales agreement

### <strong>*Proposal Types*</strong> [^4]

Programs, recommendations, plans and batch plans include products. Proposals will now include pricing.  Proposal is way to take all the products for field or group of fields for an operation, puts them on one document and adds pricing for a grower. The proposal rolls all of the same products together. A detailed breakdown is available that includes how much product for each field with breakdown by owner for financial responsibility based on split groups.

The pricing service is an integration with FinOps where product, accounts in split group, individual product quantities for the product are shared. FinOps will look at trade agreements per sale period to capture the appropriate pricing. The customer has the option to include volume pricing, which will review previous contracts for this sales year which can then be applied to pricing.

The initial price is returned from FinOps to CE. Charge codes may be added in CE to provide a discount. Thresholds are defined in the charge code and validated for each proposal line. If the threshold is exceeded, management must approve or deny the discount. Example, an LCR (local competitive response) charge code may be added in CE to the proposal at $15. Management has setup a threshold of $10 for that charge code, therefore during the approval process the system would send the proposal to the agronomist manager to approval prior to submission to the grower.

Credit checking is also validated for the customers on the proposal through FinOps and returns a yes or no. If no, the overage for the credit limit is displayed. This could be in the form of a warning or a stop. Note:  If a customer is on credit hold, a plan would not be allowed.	

Once the proposal is approved, the proposal form may be printed for the customer.
 
<strong>*There are three different proposal types within a batch plan: Customer, Prospect, and Field.*</strong> [^5]

1. Customer: Simplest proposal type and is the most used proposal type for a batch plan
2. Prospect: Individual the salesperson is pursuing that is not a current client and would like to generate a price for product and contract. 
    - Generate contract
    - Sales period
    - Farmable Acreage approximation
    - Navigate to the seed, fertilizer, or chemical tab(s) to add product
    - Create proposal
    - Open proposal 
    - Proposal lines tab
    - Run report
    - Print proposal
    - Give to potential client
3. Field: Least common proposal type used
    - Only benefit of the field is if we go through and make individual plans
    - You can add products once to all applicable fields

### Creating a Regular Plan 
Sales agreements are generated from proposals that have been approved by a grower. 
Agreements are separated by product types of seed, fertilizer and chemicals. 
This is standard as there may be different fiduciary requirements for these different product types.  
For example, 3 agreements could be created, one for seed, one for fertilizer and one for chemicals. 
The sale agreements include customer, prepayment details, payment terms, with products, quantity and pricing. 
<strong>*Each agreement can be associated with company branch.*</strong> [^6]

<strong>*These sales agreements are integrated with FinOps.*</strong> [^7]

1. <strong>*Plan to sales agreement*</strong> [^8]
2. Plans
3. Generate new plan record
4. Populate applicable fields
    - Account
    - Customer Operation
    - Customer Site: Physical piece of land that you are putting product on
    - Split group
    - Description: Multiple plans for a field may be created so a detailed description is important
    - Desired Crop
    - Growing Season: The year the product will be applied to the field
5. Utilize the tabs (Programs and Reccomendations, seed, fertilizer, or chemical) to add applicable product(s) 
    - Programs and Recommendations:
      - Programs: Ability to add existing or new programs
      - Recommendations: Attachment to precision mapping tools
    - Seed (unit):
      - Seed calculator: Helps to easily populate the quantity field
      - Add product line(s) for all required seed
    - Fertilizer:
      - Timing: When to apply product
      - Product
      - Rate
      - Unit/Rate
        - This calculation not only helps get the product pricing but also helps to know when the grower needs specific products applied. 
    - Chemical: 
      - Timing: When to apply product
      - Product
      - Rate
      - Unit/Rate
        - This calculation not only helps get the product pricing but also helps to know when the grower needs specific products applied. 
      - Plan is complete and proposal can be generated

### New Proposal

1. Plan to sales agreement
2. Proposals
3. Generate new proposal
4. Populate applicable fields
    - Description
    - Amount
    - Customer Operation
    - Split Group
    - Growing Season
    - Sales Period
    - Manager: the client will have a workflow that sets who the Manager is so it is auto-generated. This is a customization. 
5. Associated plans
    - Add existing plans
    - Select all associated plans created for this specific grower
    - Add
6. Create lines
    - This function goes through each plan taking all product information and the split groups behind them and generates individual product lines for them and creates pricing. 
7. Item category terms
    - Allow syou to set different payment methods by product. 
    - Select item category (product)
    - select payment method
    - Save
8. Proposal lines
    - Discounts/incentives to support with proposal price
    - Launch line you would like to discount
    - Charge codes
    - Add new proposal line change
    - Select charge code: Charge codes are user defined data that are defined in F&O/AX and are integrated over to CE
    - Value: dollar amount to be deducated off total product price
    - Save
    - Refresh
    - Proposal line will be updated to reflect new unit price after charge code has been applied.
    - Unit price: You can manually override this field to decrease price as well. 
    - Calculate prices

### Add product lines from proposal lines tab
In some instances, a customer will decide to add products after you have generated the proposal. 
Using the add new proposal line within the proposal lines tab will allow you to add last minute 
products to the proposal and recalculate prices. 

1. (+) New proposal line
2. Select product
3. Quantity
4. save
5. Calculate prices
6. Line will be added to the proposal lines toab and price will be updated for that product from data from F&O/AX.

### Submit for Approval
Once your proposal is priced and complete, it is ready to be submitted for approval. 
The submit for approval function/button ensures that margin on products are maintained 
throughout the sales process.

1. Submit for approval
    - Looks for any charge code or line item changes that were made and compares them to the defined thresholds that have been set. 
    - If any changes rise above threshold set it will stop the process, lock down proposal, and send to the Manager that the proposal needs approval before moving forward to contract/agreement
    - Seed:
      - Patented traits owned by specific manufacturer that you must have a license from before you can purchase and use product
      - The system will look and see if grower has  avalid agreement to buy this product and if there is configuration fin F&O/AX to either warn or stop theprocess.
      - With seed, you will typically use the "warn" function instead of full stopping the process. 
    - Restricted used pesticides:
      - Based on federal and state laws, before restricted products can be picked up, we must ensure the applicator has a valid license to apply the product. This license number needs to be physically listed on the invoice. This will warn the process this item needs to be reviewed. 
      - At this point in the process, it is important to check back in unti lthe license number has been documented. 
2. Generate sales agreement
    - The sales agreement will be sent to F&O/AX once generated. 
    - The process is then complete within CE.
    - The final step in the sales process would be to pull up the third-party integration (ex: Hello Sign) to capture a digital signature.

### Setting up Dynamics 365 CE
<strong>*Record information setup in CE is shared with FinOps for processing of data.*</strong> [^9]

**Crops**: CE>Agronomy>Configuration>Crops

A prepopulated list is available that includes crops such as alfalfa, canola, or corn.  
A user may add/edit/delete records from the crop list.

**Required Crop Units**: CE>Agronomy>Required Crop Units

Defines the crop unit size.  How many seeds are in the bag?  80,000 kernels of corn in a bag.  Other crops by be sold by pound. No link to unit of measure. This is used on the seed calculator which calculates the number of seeds to cover a field and converts to quantity of seed in a bag, and therefore, how many bags are needed.

**Timings under agronomy**: 

Timing defines when the product, program or plan will be used.  For example, the timing of applying chemicals to a crop could be considered pre or post planting or based on the amount of vegetation such as V1 or V2.  

**Charge Code Configurations**: CE> Agronomy>Charge code configurations

Allows percentage or amount thresholds to be defined for the charge code. When charge code is used, validation to this configuration is completed.  Approval would be required to override the configuration. For example, a price override threshold may be setup for a proposal.  If the threshold is exceeded, further approval may be required.  

**Pest Types**: CE>Agronomy>Pest Types

A data package will be provide for this listing including examples of bacterial, fungal, or insect.  

**Pests**: 	CE>Agronomy>Pests

A data package will be provided that includes a list of pests with type of pests. 
Examples include Aspergillus Ear Rot (fungal), Bean Leaf Beetle (Insect).   Pests may be identified in a work order to apply herbicides to the field.  This information may be manually added to crop history for review by the agronomist for future planning.

Note:  A pest applicator license if required by federal and state to apply.  

**Item Categories**: CE>Agronomy>Item Categories

Sync with FinOps including path.  Used for filtering in CE, for example, fertilizer or chemical categories. Flex Grids within the plan and batch plan are filtered by item category. 

## Process #2 Fertilizer Calculator
The Fertilizer Calculator is a tool used to generate blends of fertility products. 
1. Planning Tools
2. Fertilizer Calculator
3. Generate New
4. Populate applicable fields
    - Customer
    - Customer Operation
    - Batch size: Blender capacity when generated relays how many batches will need to occur to fill order. 
    - Fertilizer State
      - Dry
      - Liquid

   ![Dry Calculation Method](.\assets\images\DryCalculationMethod.PNG)

5. Save
6. Blend lines will populate with nutrient and product
7. Input either input value (lbs.) or ratio (percentage)
8. Click Calculate to populate output 
    - Quantity needed
    - Total blend amount
    - Number of batches needed
    - Blend percent
9. Generate sales order and release report to blender facilities to begin blending product (this function is not currently available but will be once it is fully developed and tested.)

## Process #3 Sales Order Process
The sales order is comprised of two pieces: the sales order and the work order. 
Both are tightly integrated within FinOps. The purpose of the sales order is to 
give users that only have access to CE the ability to enter orders for delivery 
and perform some of the functions that are usually completed in FinOps. 

### Generating New Sales Order in CE
1. Sales order tab
2. Generate new
3. Populate applicable sales order fields
    - Account
    - Customer Operation: It will default to one if the customer only has one operation. 
    - Split group: The individual paying for the product
    - Delivery address: A requirement for many of the actions in F&O
    - Inventory site: Where the inventory is arriving from
    - Branch: Who is responsible for the customer or in charge of handling the billing
    - Sales period: Used to price products against
    - Ship date: Will default if not manually if not populated. Not a requirement. 
    - Save

### Enter Sales Order Lines

1. Add product
2. Pick quantity
3. Save
After saving the estimated price, which is pulled from CE, will be populated. This may not be the price that is actually paid but is a stored list price that adjustments can be made to. 
4. Submit for Approval
    - Checks for any products that need an applicator license
    - Checks for any seed tech licenses that may be required
    - Credit check (*based off the credit settings with F&O. It will either warn or deny a generating sales order.*) 
5. Generate Sales Order
    - Once your submission has been approved, you will need to generate a sales order in F&O. 
    - You will receive a pop-up notifying you the sales order was created successfully in F&O/AX.
    - Once order is acted upon in F&O, you can go into details within CE and will provide more information on the split group allocations so the person in CE has access to details. 

### Work Order 
The work order is a type of sales order where the Ag Retailer will be performing a service. A work order requires more detail than a basic sales order. 

A third-party dispatching software defines the following setups and integrates with FinOps to create a work order type of sales order:

- Field(s) where products will used
- The product to be used on the field(s)
- The proper ratio to blend the fertilizer or chemicals for the field(s)
- Define the service to apply the product to the field(s)

Within FinOps the work order type of sales order which includes the products and services from the dispatching software. CE will be updated with a summary view of the work order from FinOps.  When a work order comes into CE an auto print service will print the work order and driving directions to be shared with the driver.

####  Blending and Dispensing
Lastly the work order information integrates with an additional third-party application to create a production order.  Setups regarding the product and warehouse storage within the third-party application is required. This order will provide the blending and dispensing of the fertilizer or chemicals and confirm the completed quantities.  

Once the production order is complete:

- Transfer orders will be created for the movement of inventory 
- Inventory will be reduced in the sales location
- Sales agreement will be applied to the details of the work order
- Equipment usage will be shared with the Rolling Stock module

To generate a new work order:

1. Orders
2. Work Orders
3. Generate new
4. Populate applicable fields
    - Account
    - Customer Operation
    - Customer Site
    - Auto Print: Printer logic exists to automatically print a report remotely. Would be needed when a hard copy is necessary for the remote location to send with the driver. 
    - Sales site: Party who is responsible for the sale of the product. 
    - Application Site: Paraty performing task
    - Application Operation: Type of work beign done (synced with AgSync). 
    - Application Date: Anticipated application date of the product
    - Application Window: For chemical product this is important because depending on stage of the crop, it could cause harm if applied outside a specific timeframe. 
    - Crop: Crop the product will be applied to
    - Order Status:
      - Planned: Occurring in the future
      - Booked: Occurring in the future
      - Released: Moved to queue to get done and application date is set
      - Scheduled: Has been assigned to an applicator for a scheduled date
      - In-Progress: Product was administered partially and due to an unforeseen event, the job was not completed and requires further attention. 
      - Completed Pending Review: Applicatoin is complete. 
      - Archived
      - Rejected
    - Work Order ID: Generated number out of AgSync
    - Dispensing Order Number: Only comes into effect if there is a blender/Kahler integration. This number is created when the picking list/mixed ticket is dispatched out to the warehouse. 
    - Ordering Notes:
      - Notes that are specific to the field
      - Notes that are specific to the application
    - Application Notes: Notes or observations the equipment operator made while in the field. 
    - Save

#### Enter Work Order Lines
1. Work Order Lines tab
2. Add new line
3. Populate applicable fields
    - Sales Sites
    - Customer
    - Product 
    - Pests: Certain states require documentation that states the application and purpose of the sprayed chemical. 
    - Application Site
    - Quantity
4. Submit for Approval
    - If this is an integrated order from AgSync or a third-party dispatch, the submit for approval function would not be present. The "Submit for Proposal" would show up if generated in CE.
5. If you open a work order line, you will be able to view the Work Order Completion tab which provides more information on the application and applicator. 
    - Application Worker
    - Application License
    - Rolling Rock: Equipment that was used to perform application
    - Weather data: Required by law to be tracked
      - Wind speed
      - Wind Direction
      - Temperature
      - Humidity
    - Completion date
    - State/End Times

[^1]: I'm not sure if this is correct information. I am assuming from the context.

[^2]: Should add a sentence for each type explaining the purpose of each type

[^3]: The last part of the sentence about seed doesn't make sense. The next sentence isn't a complete sentence.

[^4]: This doesn't seem like a list of proposal types. Probably has the wrong header name
Much of this doesn't include full sentences. It should be rewritten using sentences.

[^5]: This is redundant. There is an entire section for this above. Combine this information
with the information above

[^6]: Explain why this is significant. What is the purpose for specifying a branch for each contract?

[^7]: This sentence doesn't make sense standing alone like this. It obviously isn't 
explaining the list below it. What is the purpose. There should be a sentence or paragraph
explaining the list below. What is that list?

[^8]: Every place there is a step instruction, be clear what the step is. For example: Select "Batch Plan"
or Select the "Batch Plan" menu.

[^9]: What is this sentence? It doesn't look like a user instruction.

[^10]: Add links to the sections for each item. I added the first one.