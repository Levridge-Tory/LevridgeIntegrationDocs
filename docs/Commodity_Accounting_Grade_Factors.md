# Commodity Accounting Setup - Grade Factors

## Overview
Step by step process of how-to setup quality grade factors within the Commodity Accounting module of the Levridge Environment. 

## Goal
By the end of this document, you will be able to setup quality grade factors within the Levridge Environment.

### Quality Grade Factor Setup

1.	Main Menu > Modules > Commodity accounting > Setup > Quality and grade factors > Grade factors
2.	Add new grade factor (+New)
3.	Input Grade factor 
4.	Input Name
5.	Input Description
6.	Input Grade value type
    1. Numeric – this is field what most of the grade factors will go by
    2. Yes / No
    3. Text 
7.	Input Direction of range
    1. Increase – the number ranges get greater as they go
    2. Decrease – the number ranges get smaller as they go (i.e. Test Weight)
        - The summary toggle switch is used if you are going to combine two other grade factors together to create one. An example of that would be damage and heat damage would combine to create total damage and then total damage would be the summary grade factor that is setup.
8.	Add Applicable product categories (+New) – this establishes which commodity it will be used for
9.	Input Commodity
10.	Select Use required and default values for all sites
    1. If box is checked, this grade factor can be used in any of the locations that are in the system
    2. If box is unchecked, you can select an individual branch, so it only applies to a specific branch
11.	Input Branch 
    1. If use required and default values for all sites box is checked, select “ALL” for Branch field. 
    2. If use required and default values for all sites box is unchecked, select the applicable Branch.
12.	Select Required box 
    1. If box is checked, for every scale ticket that is entered for this commodity, it will require that grade factor to be entered before the scale ticket can be saved and posted.
13.	Input Default value 
14.	Summary grade factors – this is where you would add changes if the summary toggle option is used so you can add what other factors make up the summary. 
15.	Once you have all information entered the grade factor form, click Save and now your grade factor is setup within the system.

### Quality Grade Factor Sequences 

1.	Main menu > Modules > Commodity accounting > Setup > Quality and grade factors > Grade factors sequencing

Note: Quality grade factor sequences allows you to establish the sequence that the grade factors used will show up for ticket entry by commodity. Each commodity can have its own sequence if applicable.








