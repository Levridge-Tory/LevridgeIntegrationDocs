# Managing Splits, Sales Contracts, and Prepayments

## Overview
Within Levridge, when a sales order or invoice is created, the system automatically selects the sales contract (known as sales agreements in F&O) according to the items and categories identified. It also selects a prepayment against it, eliminating the need to manually go in and figure out the process, creating fewer invoicing issues sent to growers. 

Target Audience: This functionality applies to individuals in Ag Retailers who manage splits, contracts, and prepayments on behalf of customers. 

## Sales Orders
Levridge syncs sales orders between CE and F&O. As sales orders are approved in CE, the sales order is then created in F&O. The sales order in CE becomes read only once approved.  As sales orders are entered in F&O, it will be shared with CE.  

### Sales order header 
When a sales order is created, the ordering customer is selected and has the option to select customer operation and a customer site.  The customer site if selected, will be used to default the split group. If no customer operation is selected, then the user must select it manually. Note that the split group may be updated within sales order entry as needed. The operation information will default to the sales order lines.

A branch, line of business, growing season and sales period may also be entered as part of the sales order entry process. The sales period is not required.

Branch and line of business may be used to filter or categorize sales orders for list pages and some reporting. Growing season entry on a sales order will help to determine volume pricing is used, else used as a filter for list pages and some reporting.

### Sales order line 
During sales order line entry, the customer operation, customer site, and split group all default from the header and can be changed by the user. Only split group is required at this point.

Levridge displays only the list pricing during sales order entry as specific customer pricing is determined at time of delivery applying the sales agreements.  

On each line, the split group intended method for pricing may be entered. For example, a counter sale where the seed bag is damaged, could reference a flat price. Another example, during sales order entry, a specific sales agreement for pricing could be requested.  

Validation of license and certification may require a contact for certain products before it can be sent for approval. The contact information is entered in the header area.

### Supplementary items on the sales order line 
On a released item, a product may contain required or optional supplementary items.  Levridge has added functionality to automatically address the use of required supplementary items including:

- A new field linking the supplementary item to the master item is created.
- Automatically adding the supplementary line to an order with the appropriate quantity based on the associated item.  
- If the associated item is deleted or the quantity is changed, the supplementary item is also deleted, or the quantity is automatically changed on the existing supplementary line. The supplementary item’s splits and taxes will also be recalculated.  
- Added a supplementary item flag of ‘Multiple Percentage’ to calculate a percentage of the multiple as needed.  
- New fields for the supplementary item that recognize if a minimum quantity is required and the value of the minimum quantity.

### Packing Slip Post
When the sales order posts a packing slip in F&O, the pricing will be applied to each customer participating in the split group on each line. The system will initially look for intended method for pricing on the participating customer in the split group.  The system then looks at valid sales agreements to apply the sales agreement pricing and any associated prepayments. If there are multiple sales agreements, the oldest will be used first.  

If there is a quantity remaining that is not covered by a sales agreement, any uncontracted prepayments will be applied. The uncontracted price date may be used to determine pricing. For any remaining quantities the pricing will be determined by trade agreements.

The split allocation line is defined from procedures above. If the sales order line includes a Bill of Materials (BOM) item, it will validate the ‘Expand on Sales Order Allocation’ parameter on the item. If the parameter is set to yes, each of the components of the BOM will be broken out on the split allocation line for pricing. If this parament is set to no, the pricing will be based on the BOM item. For example, as fertilizer is blended, there may be a sales agreement for component products supplied by the customer.

Modifications to pricing may be made upon review for billing.

### All Sales Order Split Group Allocations
This view has been created in AR>Order to review all the allocation lines from all sales orders.

### Delivered Not Billed
AR>orders>shipped not invoiced split group allocations

Standard FinOps allows delivery of products that will be ready for invoicing. The invoicing can be today or future billed. This is standard.

There are new list pages that displays deliveries that need to be billed that are broken down per customer (based on splits) by allocation line. The item must be invoiced, so all parties will be billed. Unable to partially bill a product to one customer in a split.

## Product Functionality

### Create Split Groups in F&O 
The split group setup is located under [Create Split Group in F&O](Create-Split-Group.md). 

### Sales Agreement Entry
- In Accounts Receivable > Orders > Sales agreements > Create a new Sales agreement under the “Sales Agreement” tab by clicking the New button. 
- On the new sales agreement, select the customer the agreement is for and the item(s) or a sales category(s) the agreement is for. 
- The sales agreement can include any number of items or sales categories for that particular contract.

### Prepayment Entry
- In Accounts Receivable > Payments > Customer payment journal > Click the New button to create a new prepayment then click the “Enter customer prepayments” button. 
- Enter the customer the prepayment is for. 
- Enter in the amount of the prepayment.
- If the prepayment is being used on a sales agreement, the Sales agreement will show up in the “Sales agreement” table.   Mark the sales agreement the prepayment should be applied against.
- If there is no sales agreement/contract, you can still take a prepayment and enter it as an Uncontracted amount to ensure the funds are accounted for.  A prepayment can have some portion of it applied against an agreement and some set aside as Uncontracted.
- Once the amounts and agreements have been selected, click “Save in Journal”, annotating the prepayment has been accepted. 
- Click “Post” to process and post the prepayment. 

### Sales Order Entry
- In Accounts Receivable > Orders > All sales orders > Click the New button to create a new sales order.
- Enter the customer
  - Once selected, the customer’s account information will auto-populate
- Choose any split group for that customer on your sales order
- Choose specific sales period (this is optional).
- Enter the items for the sales order and their quantities. 
  - Additional order lines can be created.
- Click Save. 
- Click the Post packing slip button to indicate the product has been sent out to the customer. 
- Once delivered, one is now able to view the sales order with a sales agreement and prepayment allocated towards it according to the items that match between the sales order and the sales agreement and/or prepayment.



