# Agronomy Implementation Activities and Estimates

## Overview
The following is an overview of the implementation activities necessary for: 
- Integrations with AgSync and Kahler to FinOps
- CE Integrations to FinOps
- Agronomy for CE: A stand-alone CE instances without integration to FinOps

### Integrations with AgSync and Kahler to FinOps (+ Field Reveal)
1.	Which spot does the client want to be the source of truth for customer operations and site? 
    - Can be defined in Field Reveal, or AgSync or FinOps
    - If in Field Reveal - do they want to migrate the data to FinOps?
    - Determine if the client wants to use the customer site - adds some overhead
      - Recommend FinOps as the master
2.	Discovery and deployment of Kahler TM2 module - Client does this piece.
    - Kahler specific configurations
    - Collaboration between client and Kahler
3.	Deploy and install Kahler integration on client machines
    - Local install
    - Uses IIS
4.	Start preparing data for data migrations - Client does this piece.
    - If FinOps is the source of truth, this process can be streamlined
5.	Master data setup
    - Determine if product masters are going to be used
    - Build blended items/product configurator products
    - Setup dispatching account
    - Configure Levridge flags in inventory warehouse - Automatic BOM creator, warehouse items within each product/dispatching warehouse Id
    - Setup unit rates
    - Work order parameters
    - Set site specific settings - default warehouse and site for each product that will be used in a work order
    - Setup rolling stock - needs to correspond to AgSync
    - Determine units of measure for products
      - Sell UOM vs Application UOM
6.	Send clean data to 3rd parties (AgSync and Field Reveal)
7.	Setup and populate CDS with the known Ids from each party (FinOps, AgSync and Field Reveal) 
    - Also needs the blended items
8.	Get Azure AppServices and ServiceBus deployed and configured
    - Can be done in parallel with the data preparation
9.	Setup event framework in FinOps for integrations

### With CE integration to FinOps
1.	All of the above for integrations with AgSync and Kahler to FinOps
2.	CE environment setup
    - Import solutions
    - Setup security roles on users
    - Create an application user for use by the integration and services 
    - References the App Id setup in Azure tenet
3.	Get Azure AppServices and ServiceBus deployed and configured
4.	Get connection string to configure CE to FinOps integration plug-ins
5.	Create secure and unsecure configuration records
6.	Import flex grid configurations
7.	Determine which way data entities will be moving between CE and FinOps
    - Where will entities be mastered
    - Split groups, customer sites
8.	Setup relationship types in FinOps
    - Needed for the integration of data between systems
    - Takes multiple iterations to sort out
9.	Determine how charge codes are going to be setup
    - Charge codes determine how discounting is done in CRM on agronomy contracts
10.	Setup the event framework to include more data for integrations
11.	Import CE system data and run integration push from FinOps
    - Timing, crops, pests, etc.
12.	Configure master data
    - Crop units, blend configurations, fertilizer settings, product nutrients, batch sizes 
13.	Determine desired UI changes or customizations
    - This is up to the client and can take many iterations

### Agronomy for CE
Stand-alone CE instance without integration to FinOps.

