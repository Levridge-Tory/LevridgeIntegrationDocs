# Introduction
This webhost application can be run in three modes:
* As a web application (in Azure or IIS)
* As a console application
* As a service

## Run as a service
To run as a service it must be installed. To install as a service place the code 
in the folder from which you want the service to run. Deployed with the code should be
three powershell scripts:
* InstallService.ps1 - this script will install the service
* InstallEventSource.ps1 - this script will install an event source on the Application EventLog on the local machine
* RemoveService.ps1 - this script will uninstall / remove the service

### InstallService.ps1
This script installs a service and sets it to automatically run on startup. 
It accepts the following command line parameters:
- PublishPath - the path to the folder from which you want the service to run
- ServiceUser - user account under which the service will run (default = $env:computername+"\IntegrationHost")
- ServiceName - the name of the service (default = "Levridge.Integration.Host")
- ServiceDescription - the description for the service (default = "Levridge Integration Host Service")
- ServiceDisplayName - the display name for the service (default = "Levridge Integration Host")
- SourceName - the source name under which EventLog entries should be logged (default = $ServiceName)

This script will also execute the InstallEventSource.ps1 

### InstallEventSource.ps1
This script will install the specified EventLog source. It accepts the following 
command line parameter:
- SourceName - the source name under which EventLog entries should be logged (default = "Levridge.Integration.Host")

### RemoveService.ps1
This script will remove the specified service. It accepts the following command line
parameter:
- ServiceName

## Command line parameters
This application can be run with the following command line parameters:
- debug (-d) - This will cause the application to wait for a debugger to be 
  attached before it continues. This can be helpful to debug startup issues for
  services or web applications.
- service (-s) - This will cause the application to run as a service 
  (if the debugger is not attached). 
- SourceName (sn) - This will cause the application to use the specified source name 
  for the application EventLog Source Name. If no source name is specified, the default
  application source name is use.