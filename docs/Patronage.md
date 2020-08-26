# Patronage

## Overview
Patronage is a dividend or distribution that a co-operative pays to its members or investors. Patronage dividends are given based on a proportion of profit that the business makes. Once this amount is determined, management calculates the dividend according to how much each member has used the co-op's services. It is typically an annual process of generating dividends and equity balances. Managing this process has been streamlined and simplified within the Levridge solution. In a few simple steps, you can accurately set up splits, distributions, equity, reports, and cut checks. 

## Implementation Activities
The [Implementation Activities for Patronage](PatronageImplementationActivities.md) provides an overview of the implementation activities and estimates necessary for getting started with processing Patronage. 
 
## Base Type Functionality
The Patronage solutions is operated on Dynamics 365 Customer Engagement (CE) functionality, with an integration from F&O. There is certain functionality that is reliant on the integration between F&O and CE Patronage to get the data into the system, one of those being “Products” under the Setup navigation area. All the products listed are integrated over from F&O.
## D365 CE Setup Functionality
### Products
The Product form includes multiple views. This is accomplished by clicking on a certain product line. The two main factors related to Patronage are:  
1. Eligible for Patronage:  This field is set to either yes or no.  
2. Patronage unit: The goal is to know how Patronage is paid out on a product. Products can be sold in different types of unit, for example: ounce, pound, ton, vs. bushel, bag, individually. The default sales unit can be different than the Patronage itself. For example, a product sold in pounds but paid in tons.

The Item Category, Relationship to the Product, and Products under Site Navigator are reliant on the integration between F&O and CE Patronage. They are areas integrated from F&O.  An important item to note is outlining what item category relates to which Patronage category. The Patronage category is the determining factor of what items will be calculated and what items will be pulled in at different rates based. 
### Stock Classes 
This section allows a cooperative to set up stock classes. Some cooperatives will have many stock classes, some will have none.  
### Periods
Periods include calendar and fiscal periods. These are not integrated from F&O and set up on CE Patronage. 
- Fiscal period: 1099PATR reporting is run on calendar year, requiring the fiscal period to include a year calendar. 
- Split due date: A Patronage Split is how a grower would like their patronage eligible transactions to be split to another grower. The Split due date is the date the annual member letters must be returned by. This used when cooperatives send their annual letters to their members and the date they request the letter to be returned.  
- Minimum Spend: This is the minimum spend amount within a period to receive patronage. There is currently no functionality around this field and more for informational purposes. 
- Minimum Voting Activity: There is currently no functionality around this field and more for informational purposes.
### Sources
Sources is where the transactional data comes from including previous years. You could have multiple sources if you have had mergers or acquisitions with other cooperatives.  They include rules and regulations from mergers and acquisitions with other cooperatives. With those cooperatives comes different rules and regulations, and this is where cooperatives can identify where those transactions come from, different payout rates, and what rules should apply. If a cooperative has not undergone a merger or acquisition, there will more than likely be only one source information.
- Primary retirement age: This field is used to set up the retirement age that members will get paid out. This annotates what age the member is eligible to receive Patronage.
- Secondary retirement age: This field is used as a secondary option to pay out Patronage. This is the age where Patronage pay outs are mandatory. There is currently no functionality around this field and more for informational purposes.
- Default stock class: There is currently no functionality around this field and more for informational purposes. 
- Minimum payout threshold: Can enter the minimum amount the company will pay patronage on. This is informational and can be used building the payment summary export if included in the query that is built.
- Minimum Dividend percentage: Can enter the minimum percentage to receive dividends. This is informational and can be included when building queries.
- ERP System: This field is to track where the ERP system information comes from. There is currently no functionality around this field and more for informational purposes.
- 1099PATR Filing Entity: This field annotates if a member is filing a 1099PATR. If set to yes, the source is available to create 1099-PATR records for and you can populate the information on the Filing Details tab.
- The Filings Details tab outlines the information required on a 1099PATR electronic filing report. 
    - Address, Phone number, Tax ID number, Name, Contact
### Customer Information
#### Account Form
- Account Information: The fields are integrated over from F&O. 
    - Patronage Contact: is who would be receiving the retirement benefits. 
    - Estate Contact: in the case if a member dies and want to identify who we should be working out on behalf of their estate. No functional relevance as what is calculated. Purely who we should talk to if there are questions on payouts. 
    - Membership: These fields are integrated over from F&O and include: Membership Type, Tax ID Number, Tax ID Type.
    - Patronage Split Lines: Patronage Split Lines are stored in the Patronage CE and used to calculate the eligible transactions which patronage can be calculated from. 
    - Patronage Summary: Displays the equity and payment summary for the account. Summarized by period, payout type, distribution type, and source
    - Stock Summary: Displays the total stock subscriptions by stock class for the account. 
#### Reports
There are several reporting statements available per account, to include: allocation and payment by account. 
#### Stocks
Stock Subscriptions outline how many shares one has in a certain stock along with payment date, amount, and certificate number. Stock transfers and adjustments can be completed within the system. 
There are two stock types: 
1. Account type: A transfer of stock to another account. There is the option for an approval process under this type.   
2. Stock class type: Changing stocks into another type of stock.

Adjustments: if there was a data entry error or, one can make adjustments. This field is highly auditable with several restrictions
## D365 Finance and Operations Patronage
### Customers
The Customer Account information includes a Membership tab for informational data. It does not drive functionality. It includes the following fields: 
- Membership Type, Patron, Membership Date, Member ID, and Legal Classification
- Legal classification is utilized with 1099PATR reporting

Released Product Details includes the Patronage unit where fields on the product need to be set up. The unit conversions come from the Patronage unit field and needs to be set up through F&O to be able to calculate the right unit when you switch over to D365 CE. 
### Payment Details
By clicking on “Process patronage”, one can pull invoices within a specific date range, reading the invoice lines not creating. Converting the invoiced units to patronage units if the patronage unit is different on the released items. It also pulls in charge codes or discounts. Charge codes can be set up to either increase in price or decrease in price depending on how your rules are set up. 

When a sales order is generated, the F&O will break up the sales order into split allocations, creating an invoice to the customers financially responsible for what was delivered. From the information generated, one can export the data into an Excel file or CSV file to import into CE. This is done by “Imported Transactions” under the standard import functionality. You can then filter the list and “Create Patronage Detail”. This takes the information you have from your patronage splits and whether this item is chargeable and nonchargeable and creates your eligible transactions. The data needs to be in the right format to be imported into CE and can be imported from any system, not just F&O. 
### Eligible Transactions
Patronage processing is generated once all eligible transactions have been created. One does not need to bring in imported transactions if they do not use splits or are already split out, they can import right into Eligible Transactions. These are the records that will be used when calculating the equity credit and payments through Patronage Category allocations.
### Patronage Categories
Patronage categories are set up based on what is being paid out and based on sources. If a cooperative has had mergers or acquisitions, or importing categories from previous years, there will likely be a variety of categories Patronage has been processed under.  

The categories can be calculated by revenue or by units.  Direct products are not associated directly to a patronage category instead they choose the item categories of those products. Based on that relationship between item category and product that is what is determined which eligible transactions to pull in when it runs that calculation. An item category can only belong to one patronage category. 

All the eligible transactions are siphoned into the Patronage Category Allocation. Eligible transactions need to be listed as a sale or purchase. 

The Percent of Revenue is the total percent of revenue and dictates the Cash Percentage, creating a payment detail. The remaining of that would create an Equity Credit paid out later. These calculations can apply to certain branches.  

If a Patronage Category is calculated by Units, instead of reference how much is purchased, you are referencing quantity. It is classified as a rate if based on units. The Cash percentage would create a payment detail record with the rest going to an equity credit. Which the traceability you can view were created from that process. 

If the Patronage Category is calculated by units, Section199A Allocations can be set up which appear on the 1099PATR Deductions will be generated based on units purchased and the payout rate under a Specific Section1 allocation. This feeds into the 1099PATR processing. 

Once the allocation is run, one can no longer generate a new transaction. It becomes inactive. 

The other section that is created from this allocation is an equity credit. 
### Equity 
#### Equity Credits
If an equity is not paid out in the current calendar year, it moves into an equity credit value that would later determine what would be paid out This is created from the Patronage Calculation. These credits are run every year based on the items purchased or sold within that year to see how much would be paid out in the current year along with future years. An equity credit can be adjusted. 
#### Equity Revolvements
Equity Revolvements are used to determine what to pay out on existing equity credits from prior years. Here is where you annotate what percentage to pay out for a certain source, class, distribution type, or period. Based on that criteria, payment detail records are created. You can set up a Payment Schedule for the credits to be paid out in multiple years.   
#### Retirement Equity
This can be a manual or run process. The equity summary shows how much equity is available to be paid out and is a tracking mechanism to view whether one qualifies for a payout and if they request one. If a payout is requested, one can create payment details and send over to the system being utilized to for payouts. This process is traceable.  
#### Annual Allocations
The 1099 information is located under the Annual Allocations navigation. It includes: 
- Deductions
- Non-Patronage Distribution 
- 1099 Credits
- 1099 PATR
 ##### 1099 PATR
The 1099 PATR is a form a cooperative files for each person whom: 
- The cooperative has paid at least $10 in patronage dividends and other distributions described in IRS tax section 6044(b).
- The cooperative withheld any federal income tax under the backup withholding rules regardless of the amount of the payment.
 
When a cooperative collects new information for a 1099 year, they would create a new 1099 PATR form. Under 1099 PATR, click “Build 1099 PATR”
- A dialog box will open asking to select the following: 
    - 1099 Year (a calendar year)
    - Source (where you want the information to be coming from)
      - This is the information collected previously under Source. 
    - Click Generate. This generates the records requested and pulls in the details required for the form. 
    - Additional items that make up a 1099 PATR form include:  
      - General Account Information
      - 1099 Credit
        - This includes a variety of credit types available. 
    - Deductions
      - Records created from Patronage categories 
    - Non-Patronage Distributions
      - Includes all the source data that made up the record. This is necessary for auditing purposes
    - Payments 
      - Equity Credits 
      - Related 
 
The 1099 PATR form is used for electronic filing. The cooperative can print either 1099 PATR-B or 1099 PATR-C versions of the 1099 PATR to provide to their members for tax purposes. The 1099 PATR form is also available online and can be accessed through a portal for members to download. 
### Patronage Power BI Dashboards
There are several dashboards available for Patronage through Power BI. These are powerful reporting tools to analyze and view key Patronage data and summaries. They are located: Customer Info navigation tab > Customers > Customer Info > Add Dashboards > Patronage Dashboard

The following dashboards are already pre-loaded: 
- 1099A Deductions
- Allocation Summary
- Eligible Transactions
- Equity Credit
- Equity Revolvements
- Patronage Dashboard
### Payment Details and Summary
The Patronage Category Process creates an individual payment detail record for each eligible transaction. There is a summarize payment option that if you use the Advanced Find functionality received with CE, you can put in any sort of query you want to show payment details and from there can “Generate Payment Summary”.  This would summarize all the records. Once you have that summary detail, you can export it to an Excel file. This is the data you would bring into your financial system.
Once the data is exported, you can go into F&O under Accounts Payable and import the data. This will create a vendor invoice for each record. Once you have the vendor invoices, you can create a journal specific to Patronage. There are designations for specific invoice journals for Patronage. 
 
The Patronage journal is different from a standard invoice journal due to bringing in and identifying the customer account. A core function in F&O is when those transactions are processed and imported from CE, F&O can pay out on a different account (a financial split vs payment split). Once in F&O, the customer can decide where they would like the distribution to be sent to and the allocated percentage. 
 
There are variety of payment journals one can choose from. When journals are set up to pay out, ensure equity payment is specified along with the check and device format. There are up to five options to choose from. There is the ability for multiple check formats and the ability to include additional information on check stubs. This is located under Payment Proposal. 
