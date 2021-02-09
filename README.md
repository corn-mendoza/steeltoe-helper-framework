# Steeltoe Helper Library for .NET Framework Applications on Cloud Foundry

Steeltoe Helper Library for fast integration of Steeltoe libraries into .NET Framework applications. Adds the classes needed to load the configuration information and enable the actuators. 

## Requirements
The following are required for the library to execute corretly.

- appsettings.json file tagged to be copied when application is being published for deployemnt (see included example appsettings.json file and update as neccessary)
- web.config updated with the following code:
`  
    Insert in the <system.webserver> secction:

    <system.webServer>      
      <handlers>    
        <remove name="ExtensionlessUrlHandler-Integrated-4.0"/>      
        <remove name="OPTIONSVerbHandler"/>      
        <remove name="TRACEVerbHandler"/>      
        <add name="ExtensionlessUrlHandler-Integrated-4.0" path="*." verb="*" type="System.Web.Handlers.TransferRequestHandler"
                preCondition="integratedMode,runtimeVersionv4.0"/>      
      </handlers>    
      <validation validateIntegratedModeConfiguration="false"/>    
    </system.webServer>
`
  
