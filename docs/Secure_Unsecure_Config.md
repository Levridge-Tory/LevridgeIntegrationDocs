# Secure and Unsecure Configuration Record Setup in CE

## Overview

The Secure and Unsecure Configuration records are used to store configuration that are used for the CE to Finops service calls such as the credit check, generating a sales order, printing, certification check, and boundary editing (surety). The secure configuration record is used to store sensitive data that should only be available to administrators. The unsecure configuration records store less sensitive data needed for the service calls.

### Secure Configuration

![CE1](.\assets\images\CE\CE_1.png)

Fill out Report tab if you will be using the work order auto-print service.

![CE2](.\assets\images\CE\CE_2.png)

Fill out Azure Storage tab if you will be using the work order auto-print service.

![CE3](.\assets\images\CE\CE_3.png)

Fill out Service Bus tab if you will be using the work order auto-print service.

![CE4](.\assets\images\CE\CE_4.png)

### Unsecure Configuration

![CE5](.\assets\images\CE\CE_5.png)

Fill out the below section if you will be using Surety

![CE6](.\assets\images\CE\CE_6.png)

