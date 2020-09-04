# Patronage Implementation Activities


## Overview
The following is an overview of the implementation activities necessary for getting started with processing Patronage.  
   
### Initial Implementation Activities
1. In FinOps, update released products with a patronage unit
2. In FinOps, setup equity vendor journals
3. In FinOps, setup equity vendor payments including checks
4. In FinOps, setup any patronage payment distributions on customers
5. From FinOps, push via the Levridge integration customers, contacts, item categories, units of measure, branches and addresses to CE
6. In CE, setup patronage specific information:
    a. Stock classes
    2. Sources
    3. Periods
    4. Patronage split lines
7. Into CE, import stock subscriptions
8. Into CE, import stock subscrptions
9. Into CE, import any equity credits from other systems (if applicable)
10. In CE, create patronage categories
    a. Setup per unit and revenue allocations
    2. Setup 199A allocations
11. In CE, setup requirements equity
12. In CE, setup equity revolvements


### Year-End Activities

1.	In FinOps, export out patronage sales
2.	In CE, import imported transactions (these are what was exported from FinOps or other systems)
3.	In CE, run patronage detail to create eligible transactions
    a.	Verify results (this takes most of the time)
    i.	Eligible transactions were created properly
    ii.	Split look as expected
4.	In CE, run patronage category allocations
    a.	Verify results (this takes most of the time)
    i.	Payments
    ii.	Equity credits
5.	In CE, run equity revolvements
    a.	Verify results
    i.	Payment details
    ii.	Equity credits updated accordingly
6.	In CE, run retirement equity summaries
7.	In CE, create payment summaries
    a.	Verify results
8.	In CE, export payment summaries
9.	In FinOps, import payment summaries which become vendor journals
10.	In FinOps, post vendor journals
11.	In FinOps, pay equity vendor invoices

### Calendar Year-End Activities
1.	In CE, create non-patronage distributions for 1099 PATR
2.	In CE, create 1099 PATR credits
3.	In CE, create 1099 PATR records
    a.	Verify results
4.	In CE, build 1099 PATR electronic file
    a.	Verify results
5.	In CE, print copy B and copy C of the 1099 PATR records
