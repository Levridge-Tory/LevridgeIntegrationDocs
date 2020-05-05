# Logging Settings
This document describes how to configure logging for the Levridge Integration Framework

# Overview
The Levridge Integration Framework utilizes the standard [ASP.NET Core logging](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/logging/?view=aspnetcore-3.1) capabilities.
Our primary target for logging is [Azure Application Insights](https://docs.microsoft.com/en-us/azure/azure-monitor/app/app-insights-overview) however
we can also log to the Windows Event Log. This can be usefull if the integration framework is running as a windows service
and does not have highspeed internet access to send log data to Application Insights.

# Log Settings
In the appsettings.json file there is a "Logging" section that defines the log settings for the various
logging providers.

A typical logging section may look like this.

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
            "IncludeScopes": true,
            "LogLevel": {
                "Default": "Trace"
            }
        },
        "LogLevel": {
            "Default": "Warning"
        }
    },

Unless you are using Debug or Console logging the only setting you need to be concerned with is the
ApplicationInsights object. In a typical production environment you will want this set to "Information" or 
"Warning" rather than trace. However, to troubleshoot issues you may need to set this to "Trace".

## Valid Log Levels
Here are the valid log level settings:

| Setting | Description |
| ----------- | ----------- |
| Trace | Logs that contain the most detailed messages. These messages may contain sensitive application data. These messages are disabled by default and should never be enabled in a production environment. |
| Debug | Logs that are used for interactive investigation during development. These logs should primarily contain information useful for debugging and have no long-term value. |
| Information | Logs that track the general flow of the application. These logs should have long-term value. |
| Warning | Logs that highlight an abnormal or unexpected event in the application flow, but do not otherwise cause the application execution to stop. |
| Error | Logs that highlight when the current flow of execution is stopped due to a failure. These should indicate a failure in the current activity, not an application-wide failure. |
| Critical | Logs that describe an unrecoverable application or system crash, or a catastrophic failure that requires immediate attention. |
| None | Not used for writing log messages. Specifies that a logging category should not write any messages. |

## Application Insights Instrumentation Key
Application Insights uses an Intrumentation Key to specify the Application Insights resource to use for logging.
If the integration framework is deployed to Azure and Application Insights is enabled, the Instrumentation Key 
will be specified in the environment variables. However, if the Integration is deployed on premise an Instrumentation Key
must be specified for the Application Insights logging provider to send the log data to the correct Application Insights
resource.

    "ApplicationInsights": {
        "InstrumentationKey": "[Application Insights Instrumentation Key]"
    },

This section is at the top level and not in the Logging section. Here is an example of a partial appsettings.json file.

    "Logging": {
        "ApplicationInsights": {
            "LogLevel": {
                "Default": "Trace"
            }
        "LogLevel": {
            "Default": "Information"
        }
    },
    "AllowedHosts": "*",
    "ApplicationInsights": {
        "InstrumentationKey": "1a2b3c4d-5e6f-4b24-9308-4dff05f1cd02"
    },
