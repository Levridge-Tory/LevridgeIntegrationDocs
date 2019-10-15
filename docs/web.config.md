# Web.config File
## Overview
The web.config file only applies to Integration Framework instances that are hosted as a web application.
Typically these are hosted in Azure but can also be hosted on-premise in IIS.

Although Microsoft documentation claims that the [web.config file has been replaced](https://docs.microsoft.com/en-us/aspnet/core/migration/configuration?view=aspnetcore-2.2#setup-configuration), 
Azure App Services still use it as the means to start the application service. It should not contain any application configuration settings.

The web.config file is an XML file that contains a <configuration> element.

## Web.Config Elements

### \<configuration>\</configuration> 
This is the main element that contains the other elements

### \<location>\<\location>
This element contains the relative path for the web server

### \<system.webserver>\<\system.webserver>
Contains the handlers and aspNetCore elements

### \<handlers>\<\handlers>
Defines the element for the web server.

### \<aspNetCore\\\>
Defines the path to the web server assembly and standard output logging information. 
Set ```stdoutLogEnable``` to "true" to write standard out logging to files in the relative location pointed to by
the ```stdoutLogFile``` attribute.

To specify command-line attributes add them to the ```processPath``` attribuute on the 
```aspNetCore``` element. For example, to specify the name for the InstanceConfig node change the 
```processPath``` to look like this: ```processPath=".\Levridge.Integration.Host.exe -i=MyInstanceConfig"```

## Sample

```
    <?xml version="1.0" encoding="utf-8"?>
    <configuration>
      <location path="." inheritInChildApplications="false">
        <system.webServer>
          <handlers>
            <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
          </handlers>
          <aspNetCore processPath=".\Levridge.Integration.Host.exe" stdoutLogEnabled="false" stdoutLogFile=".\logs\stdout" />
        </system.webServer>
      </location>
    </configuration>
```