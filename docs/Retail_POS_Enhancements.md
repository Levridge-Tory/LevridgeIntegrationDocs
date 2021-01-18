# Levridge Retail POS Enhancements

## Retail Configuration

To fully utilize Levridge Agronomy Sales with FinOps Point-of-sale, the call center functionality must be enabled to allow for sales order entry in FinOps and then recalling that order into POS for completion. 

On the call center users form, there is the option to open the sales order form in standard view which will open the sales order detail form in the full order entry view rather than the streamlined counter sales form provided by Levridge. This is the allow call center users who will need to process order deliveries or invoicing full access to all functions. 

## Customer Account

To allow the sales order to process through Levridge when coming from FinOps POS, the customer account has customer operation and split group fields added to the Retail fast tab on the customer account form. These fields are automatically populated when a customer record is created and will be used on a sales order coming from point-of-sale. 

## Counter Sales

A new sales order form is available when using the Levridge retail functionality to help streamline the entry of sales orders in FinOps. From the sales order action pane in the Sales order tab, click new counter sales. 

![Retail1](.\assets\images\Retail\Retail1.png)

The user can select the if this is a cash customer or select an existing customer account. If Cash customer is set to Yes, the system will automatically pull in the store’s customer account.

Once the sales order is created, the Counter sales form provides the user the ability to enter items and view detail specific to a retail POS order. If the user requires access to all the sales order functionality, they can click “Change order view” in the sales order action pane. 

![Retail2](.\assets\images\Retail\Retail2.png)

![Retail3](.\assets\images\Retail\Retail3.png)

There are a few scenarios where the sales order must be initiated from FinOps:

1.	If the product being sold requires a license (certificate).
2.	If the product being sold requires a seed or technology agreement with the vendor.
3.	If the product being sold has a sales agreement.
4.	If the product being sold has a prepayment.

It is possible to sell a regulated product to a cash customer through counter sales. You can add a certificate to the sales order from the Add certificate option in the sales order action pane or select from the certification number . However, it is not possible to use the cash customer for seed or technology agreements, sales agreements, or prepayments. 

If the customer has a sales agreement for the item, the system will identify the sales agreement and apply the unit price to the order. If there is a prepayment associated to that sales agreement or an uncontracted prepayment for the item, the system will apply that prepayment amount. When the order is opened from the POS, the information will be passed into the order. A prepayment will display as a deposit and the customer will only have to pay for any products added to the order from the POS or are not covered by a prepayment.



