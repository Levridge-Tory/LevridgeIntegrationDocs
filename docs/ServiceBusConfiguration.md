# ServiceBusConfiguration
The ServiceBusConfiguration object is used to configure a connection to
a service bus queue or topic.

# Example
    "prodagsyncmasterdata": {
      "ConnectionString": "Endpoint=[Customer Servicebus Connection String]",
      "TopicName": "[Customer Servicebus Topic]",
      "SubscriptionName": "[Customer Servicebus Topic Subscription]",
      "MaxConcurrentCount":10
    },


# Definition

## ConnectionString
## TopicName
## SubscriptionName
## MaxConcurrentCount
The maximum number of messages that will be allowed to be processed simultaneously.
