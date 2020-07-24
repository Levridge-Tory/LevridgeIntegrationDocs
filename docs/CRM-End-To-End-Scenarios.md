# CRM End-to-End Scenarios

## Overview
1.	Planned to Sales Agreement - sales tool within CRM used to price product and transition growers into contracts. 
2.	Fertilizer Calculator - utility that allows a salesman to determine and calculate fertilizer requirements such as what product best fits the need of the customer and how much of that product is needed to fulfill the order (some work is still needed and is anticipated to be ready in Fall of 2020). 
3.	Sales Order Process - integration of all Levridge pieces, specifically split billing, and its close integration with sales orders in FinOps.
### Process #1: Planned to Sales Agreement
There are three separate methods of kicking off a planned sales agreement within CRM: batch plans, regular plan, and proposals.
#### Batch Plans
1. Batch Plans tab
2. Generate New
3. Populate required fields
- Name – this field will auto populate when you save
- Proposal Type - there are three proposal types: Customer, Field and Prospect. The batch plan will auto populate to the Customer Type. 
- Account
- Customer Operation
- Split Group
- Sales Period – we need this so we can accurately price 
- Save
4. Programs Tab
- Farmable acreage field is required
- Preconfigured set of products in many cases an agronomist recommends the same products at the same rate so instead of calculating these rates each time, you can set up a program, so it automatically calculates product and rate. 
5. Add products utilizing the tabs across the top of the batch plan, (seed, fertilizer, chemical, etc.)
6. After adding your products, you can either
- Generate a proposal 
- Generate a sales agreement 
#### Proposal Types
There are three different proposal types within a batch plan: Customer, Prospect, and Field.
1. Customer - simplest proposal type and is the most used proposal type for a batch plan 
2. Prospect - individual the salesman is pursuing that is not a current client and we want a way to generate a price for product and a contact for the potential client
- Generate contact
- Sales period 
- Farmable Acreage approximation 
- Navigate to the seed, fertilizer, or chemical tab(s) to add product
- Create proposal 
- Open proposal
- Proposal lines tab
- Run report 
- Print Proposal
- Give to potential client 
- Field - least common proposal type used  
  - Only benefit of the field is if we go through and make individual plans in a lot of cases, we will use the same product on all of them
  - You can add products once to all appliable fields 
#### Creating a Regular Plan 
1. Plan to sales agreement 
2. Plans
3. Generate new plan record
4. Populate applicable fields
- Account
- Customer Operation
- Customer site – physical piece of land that you are putting the product on
- Split group
- Description - multiple plans for a field may be created so a detailed description is important
- Desired Crop
- Growing Season – what year this product will be applied to the field 
5. Utilize the tabs (Programs and Recommendations, seed, fertilizer, or chemical) to add applicable product(s)
- Program and recommendations 
  - Programs – ability to add existing or new programs 
  - Recommendations – attachment to precision mapping tools 
- Seed (Unit)
  - Seed calculator – helps do the math to easily populate the quantity field
  - Add product line(s) for all required seed
- Fertilizer 
    - Timing – when to apply product
  - Product
  - Rate
  - Unit/Rate
  - This calculation not only helps get product pricing but also helps us know when the grower needs specific products applied
  - Chemical
  - Timing – when to apply product
  - Product
  - Rate
  - Unit/Rate
    - This calculation not only helps get product pricing but also helps us know when the grower needs specific products applied
6. Plan is complete and proposal can be generated  
#### New Proposal
1. Plan to sales agreement
2. Proposals
3. Generate new proposal
4. Populate applicable fields
- Description
- Account 
- Customer operation
- Split group
- Growing season
- Sales period
- Manager – the client will have a workflow that sets who the Manager is so it is auto generated, this is a customization
5. Associated plans
- Add existing plans
- Select all associated plans created for this specific grower
- Add
6. Create lines
- This function goes through each plan taking all product information and the split groups behind them and generates individual product lines for them and creates pricing for them
7. Item category terms
- Allows you to set different payment methods by product 
- Select item category (product)
- Select payment method
- save 
8. Proposal lines
- Often discounts/incentives are provided to get the producer to agree to the proposal price
- Launch line you would like to discount
- Charge codes
- Add new proposal line change
- Select charge code – charge codes are user defined data that are defined in FinOps/AX and are integrated over to CE/CRM
- Value – dollar amount to be deducted off total product price 
- Save
- Refresh
- Proposal line will be updated to reflect new net unit price after charge code has been applied
- Unit price – you can manually override this field to decrease price as well 
- Calculate prices
#### Add product lines from proposal lines tab
In some instances, a customer will decide to add products after you have generated the proposal. Using the add new proposal line within the proposal lines tab will allow you to add last minute products to the proposal and recalculate price. 
1. (+) New proposal line
2. Select product
3. Quantity
4. Save
5. Calculate prices
6. Line will be added to the proposal lines tab and price will be updated for that product from data from FinOps/AX.
#### Submit for Approval
Once your proposal is priced and complete, it is ready to be submitted for approval. The submit for approval function/button ensures that margin on products are maintained throughout the sales process.
1. Submit for approval 
- Looks for any charge code or line item changes that were made and compares them to the defined thresholds that have been set
- If any changes rise above threshold set, it will stop the process, lock down proposal and send to the Manager that the proposal needs approval before moving forward to contract/ agreement
- Seed
  - Patented traits owned by specific manufacturer that you must have a license from that manufacturer before you can purchase and use product 
  - The system will look and see if grower has a valid agreement to buy this product and there is configuration in FinOps/AX to either warn/stop continued process 
  - With seed you will typically use the “warn” function instead of fully stopping the process
- Restricted use pesticides
  - Based on Federal/State laws, before restricted use products can be picked up, we must ensure that the applicator has a valid license to apply these products. This license number needs to be physically listed on the invoice. This will warn the process that this item needs to be taken care of.
  - At this point in the process we may not know who is applying the product, so it is important to check back in until the license number has been documented.
2. Generate sales agreement 
- After the sales agreement is generated, it is sent across to FinOps/AX
- At this point, the process within CE/CRM is complete
- The final step in the sales process would be to pull up the third-party integration (ex. Hello Sign) to capture a digital signature 
### Process #2 Fertilizer Calculator
The Fertilizer Calculator is a tool used to generate blends of fertility products. 
1. Planning Tools
2. Fertilizer Calculator
3. Generate New
4. Populate applicable fields
- Customer
- Customer Operation 
- Batch Size – blender capacity so when generated it relays how many batches will need to occur to fulfill the order
- Fertilizer State
  - Dry
  - Liquid
![Dry Calculation Method](.\assets\images\DryCalculationMethod.PNG)
5. Save
6. Blend Lines will populate with nutrient and product
7. Input either input value (lbs.) or ratio (percentage)
8. Click Calculate to populate output
- Quantity needed 
- Total blend amount
- Number of batches needed
- Blend Percent 
9. Generate sales order and release report to blender facilities to begin blending product (this function/button is not currently available but will be once it is fully developed and tested). 
### Process #3 Sales Order Process
The sales order is comprised of two pieces: the sales order and the work order. Both are tightly integrated within FinOps. The purpose of the sales order is to give users that only have access to CE/CRM the ability to enter orders for delivery and perform some of the functions that are usually completed in FinOps/AX. 
##### Generating New Sales Order in CE/CRM
1. Sales order tab
2. Generate new
3. Populate applicable sales order fields
  - Account
  - Customer operation - if the customer only has 1 operation it will default, otherwise, it will filter down to their operations
  - Split group - who will be paying for the product
  - Delivery address - delivery address is a requirement for many of the actions in FinOps
  - Inventory site - where inventory is coming from
  - Branch - who is responsible for the customer or in charge of handling the billing
  - Sales period - sales period is used to price the products against
  - Ship date - not required and will default if not manually populated
4. Save
#### Enter Sales Order Lines
1. Add product 
2 Pick quantity 
3. Save 
After saving the estimated price, which is pulled from CRM/CE, will be populated. This may not be the price that is actually paid but is a stored list price that adjustments can be made to. 
4. Submit for Approval
  - Checks for any products that need an applicators license
  - Checks for any seed tech licenses that may be required
  - Credit check (based off the credit settings within FinOps, it will either warn/deny generating sales order)
5. Generate Sales Order
  - Once your submission has been approved, you will need to generate a sales order in FinOps/AX
  - You will receive a pop-up notifying you the sales order was created successfully in FinOps/AX
  - Once order is acted upon in FinOps, you can go into the line details within CE/CRM and it will give more information on the split group allocations (quantities, dates shipped, etc) so the person in CE/CRM has access to some of that detail
#### Work Order 
The work order is a type of sales order where the Ag Retailer will be performing a service. A work order requires more detail than a basic sales order. 
1. Orders
2. Work Orders
3. Generate New
4. Populate applicable fields
  - Account
  - Customer Operation
  - Customer Site
  - Auto Print – printer logic exists to automatically print a report remotely would be needed when a hard copy is necessary for the remote location to send with the driver
  - Sales Site – party who is responsible for the sale of the product 
  - Application Site – party performing task 
  - Application Operation – type of work being done (synced with AgSync)
  - Application Date – anticipated application date of the product
  - Application Window – for chemical product this is important because depending on stage of the crop, it could cause harm if applied outside of a specific timeframe
  - Crop – crop product will be applied to
  - Order Status
    - Planned – occurring in the future
    - Booked – occurring in the future
    - Released – moved to queue to get done and application date is set
    - Scheduled – it will happen today or tomorrow and has been assigned to an applicator
    - In-Progress – product was administered partially and due to some unforeseen event, the job was not completed and requires further attention 
    - Completed Pending Review – application is complete
    - Archived
    - Rejected
  - Work Order ID – generated number out of AgSync. 
  - Dispensing Order Number – only comes into effect if there is a blender/Kahler integration. This number is created when the picking list / mixed ticket is dispatched out to the warehouse.
  - Ordering Notes 
    - Notes that are specific to the field (ex. Approach on NW Corner)
    - Notes that are specific to application (ex. Spray when wind is coming from NW to ensure surrounding susceptible fields are not sprayed)
  - Application Notes – notes or observation that equipment operator made while in the field
5. Save 
#### Enter Work Order Lines
1. Work Order Lines tab
2. Add new line
3. Populate applicable fields
- Sales Sites
- Customer
- Product
- Pests – when spraying chemicals some states require documentation that states purpose of application 
- Application Site
- Quantity 
4. Submit for Approval – if this is an integrated order from AgSync or from some third-party dispatch, the submit for approval function/button would be gone but if you generate in CRM you would see submit for approval 
5. If you open a work order line, you will be able to view the Work Order Completion Tab which provides more information on the application and applicator.
- Application Worker
- Application License
- Rolling Stock - equipment that was used to perform application 
- Weather data
  - Required by law to be tracked 
  - Wind Speed
  - Wind Direction
  - Temperature
  - Humidity
  - Completion date
  - Start/End Times 
