# Azure Service Bus Setup

## Overview

## Namespace Settings

### Pricing Tier
The pricing tier options are Basic, Standard, or Premium. Levridge recommends
using topics and subscriptions for the integration and that is not supported on the 
Basic tier so you must use either Standard or Premium.

The Premium tier provides more consistent high throughput and allows for larger
message sizes. Currently, Levridge has found the use of the Standard tier to be
adequate and more cost effective. We recommend using the Standard tier.

For more information on the differences between the two tiers see 
[this Microsoft document.](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-premium-messaging)

**Recommended value = Standard**

## Topics

### Partitioning
[Microsoft desribes](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-partitioning) 
partitioned queues and topics like this: 

>Service Bus partitions enable queues and topics, or messaging entities, to be 
partitioned across multiple message brokers and messaging stores. Partitioning 
means that the overall throughput of a partitioned entity is no longer limited 
by the performance of a single message broker or messaging store. In addition, 
a temporary outage of a messaging store does not render a partitioned queue or 
topic unavailable.

## Subscriptions

## Definition

### ConnectionString
### TopicName
### SubscriptionName
### MaxConcurrentCount
The maximum number of messages that will be allowed to be processed simultaneously.
