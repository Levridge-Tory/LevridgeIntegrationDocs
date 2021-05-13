# Scale Appsettings Configuration

### Configure Appsettings Files

Configure the appsettings.json file in the following default locations:
C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Servers\LevScaleClient
C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Servers\LevScaleAPI
C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Services\AxToScaleIntegration
C:\Program Files (x86)\Levridge\LevridgeScaleHouse\Services\HardwareInterface


#### LevScaleClient

```
{
  "GeneratedDb": "C:\\LevridgeScaleHouse\\sql",
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=.\\SQLEXPRESS;Initial Catalog=LevScale;Trusted_Connection=True;MultipleActiveResultSets=true;"
  },
  "WipProcessInterval": 10000,
  "WipCleanupInterval": 86400000,
  "Logging": {
    "IncludeScopes": false,
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "ServiceBusSettings": {
    "ServiceBusConnectionString":
//Enter the endpoint for the service bus for integration from Levridge Scale to F&O
 "Endpoint=sb://integration.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=PG5SCOfZHIKQ7rmRmSdKwGe2OW27hRhxxxxxx=",
//Enter the Topic name for the service bus
    "TopicName": "scaletofo"
  },
 
  "WebAPI": {
    "Port": 80,
    "URL": "http://localhost:8080",
  },
  "Printer": {
    "DataSource": "Server=.;Initial Catalog=LevScale;Trusted_Connection=True;MultipleActiveResultSets=true;",
    "ReportPath": "./"
  },
 
  "ScaleInterface": {
    "UriString": "http://localhost:44323/",
    "TLSVersion": ""
  },
"LogLocationCleanup": {
        /// <summary>
        /// The location of the log folder.
        /// </summary>
        /// <remarks>The default value is 'C:\Temp'.</remarks>
        "LogFolder": "C:\\Temp",
        /// <summary>
        /// The time to wait (in minutes) before clearing old logs from the reporting location.
        /// </summary>
        /// <remarks>The default is 1,440 mintues (24 hours).</remarks>
        "RecheckInterval": 2880,
        /// <summary>
        /// Log files may be deleted that are older than this many mintues..
        /// </summary>
        /// <remarks>The default is 2,880 minutes (24 hours).</remarks>
        "RemoveAfter": 2880,
        /// <summary>
        /// The file filter used when clearing old report files.
        /// </summary>
        /// <remarks>The default is "*".</remarks>
        "FileFilter": "*.txt",
        /// <summary>
        /// The file search options.
        /// </summary>
        /// <remarks>The default is <see cref="SearchOption.TopDirectoryOnly"/></remarks>
        "FileSearchOptions": "TopDirectoryOnly"
    },
 
  "Log4Net": { "xml": "log4net.xml" },
"DynamicsAX": {
//Enter the connection details for F&O
    "UriString": "https://landusuat.sandbox.operations.dynamics.com/",
    "ActiveDirectoryResource": "https://landusuat.sandbox.operations.dynamics.com",
    "ActiveDirectoryTenant": "https://login.microsoftonline.com/bb671371-5d5c-4dca-9c53-9376bxxxx",
    "ActiveDirectoryClientAppId": "ef8c69c1-0d35-40eb-aec9-b393xxxx",
    "ActiveDirectoryClientAppSecret": "4ZpHiXn0k2Nx9vnsgmJq+uYbT4drRL1cJLcxxxx=",
    "TLSVersion": "",
    "ODataEntityPath": "https://landusuat.sandbox.operations.dynamics.com/data/",
    "DataAreaId": "100"
  }
 
 
}
```

#### LevScaleAPI

```
{
    "AllowedHosts": "*",  
  "GeneratedDb": "C:\\LevridgeScaleHouse\\sql",
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=.\\SQLEXPRESS;Initial Catalog=LevScale;Trusted_Connection=True;MultipleActiveResultSets=true;"
  },
  "WipProcessInterval": 10000,
  "WipCleanupInterval": 86400000,
  "Logging": {
    "IncludeScopes": false,
    "LogLevel": {
      "Default": "Warning"
    }
  },
  "ServiceBusSettings": {
    "ServiceBusConnectionString":
//Enter the endpoint for the service bus for integration from Levridge Scale to F&O
  "Endpoint=sb://integration.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=PG5SCOfZHIKQ7rmRmSdKwGe2OW27hRhxxxxxx=",
//Enter the Topic name for the service bus
    "TopicName": "scaletofo"
  },

 
  "WebAPI": {
    "Port": 80,
    "URL": "http://localhost:8080",
  },
  "Printer": {
    "DataSource": "Server=.;Initial Catalog=LevScale;Trusted_Connection=True;MultipleActiveResultSets=true;",
    "ReportPath": "./"
  },
 
  "ScaleInterface": {
    "UriString": "http://localhost:44323/",
    "TLSVersion": ""
  },
 
  "Log4Net": { "xml": "log4net.xml" }
 
 
}
```

### AxToScaleIntegration

```
{
  "Logging": {
  	"ApplicationInsights": {
             "LogLevel": {
                 "Default": "Trace"
             }
         },
    "Debug": {
      "LogLevel": {
        "Default": "Trace"
      }
    },
    "Console": {
      "IncludeScopes": false,
      "LogLevel": {
        "Default": "Debug"
      }
    },
    "LogLevel": {
      "Default": "Information"
    }
  },
  "ApplicationInsights": {
    "InstrumentationKey": ""
  },
    "InstanceConfig": {
        "AzureTableConfiguration": "AzureTableConfigurationAX"
    },
    "SourceConfig": {
    "ServiceBusConfigName": "AxToScale",
    "ODataConfigName": "DynamicsAX",
    "SystemName": "DynamicsAX",
    "Direction": "Source"
  },
  "TargetConfig": {
    "ODataConfigName": "ScaleOData",
    "SystemName": "ScaleHouse",
    "Direction": "Target"
  },
 //Enter the connection details for F&O
  "DynamicsAX": {
    "UriString": "https://landusuat.sandbox.operations.dynamics.com/",
    "ActiveDirectoryResource": "https://landusuat.sandbox.operations.dynamics.com",
    "ActiveDirectoryTenant": "https://login.microsoftonline.com/bb671371-5d5c-4dca-9c53xxxxxxx",
    "ActiveDirectoryClientAppId": "ef8c69c1-0d35-40eb-aec9-b39381xxxxx",
    "ActiveDirectoryClientAppSecret": "4ZpHiXn0k2Nx9vnsgmJq+uYbT4drRL1xxxxxI=",
    "TLSVersion": "",
    "ODataEntityPath": "https://landusuat.sandbox.operations.dynamics.com/data/",
    "DataAreaId": "100"
  },
//Enter the Active Directory details for F&O. Leave the default values for UriString and ODataEntityPath
    "ScaleOData": {
        "UriString": "http://localhost:8080/odata",
    "ActiveDirectoryResource": "https://landusuat.sandbox.operations.dynamics.com",
    "ActiveDirectoryTenant": "https://login.microsoftonline.com/bb671371-5d5c-4dca-9c53-9376xxxxx",
    "ActiveDirectoryClientAppId": "ef8c69c1-0d35-40eb-aec9-b3xxxxx",
    "ActiveDirectoryClientAppSecret": "4ZpHiXn0k2Nx9vnsgmJq+uYbT4drRL1cJLcxxxxx=",
        "TLSVersion": "",
        "ODataEntityPath": "http://localhost:8080/odata"
    },
 
  "AxToScale": {
    "ConnectionString":
 //Enter the endpoint for the service bus for integration from F&O to Levridge Scale
  "Endpoint=sb://integration.servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=PG5SCOfZHIKQ7rmRmSdKwGe2OW27hRhxxxxxx=",
//Enter the Topic name for the service bus
    "TopicName": "axtoscale",
//Enter the Subscription name for the service bus
    "SubscriptionName": "000",
    "PrefetchCount": 40,
    "MaxConcurrentCount": 20
  }
 
}
```

#### HardwareInterface

```
{
    "ConnectionStrings": {
        "DefaultConnection": "Data Source=.\\SQLEXPRESS;Initial Catalog=LevScale;Trusted_Connection=True;"
    },
    "Logging": {
        "LogLevel": {
            "Default": "Warning"
        }
    },
    "AllowedHosts": "*",
    "Hardware": {
        "HubUrl": "http://localhost:80/scalehub",
        "WorkstationName" : "Ws1"
    }
}
```
