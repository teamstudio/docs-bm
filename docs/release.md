# Release Notes

Build Manager 9.1 is a feature release of Build Manager adding support for 64 bit Notes clients. On 64 bit clients, the Build Manager utility executable is now named *TeamstudioBuildManager64.exe* rather than *TeamstudioBuildManager.exe*. Build Manager will detect whether it is running on a 64 or 32 bit client and install the correct executable automatically.

From this release onwards, the LotusScript source code for Build Manager is no longer hidden. There are no changes to the licensing terms, but we hope that being able to read the code will help with making the best use of Build Manager in your environment.

## Upgrading
To upgrade the Build Manager NSF, sign the template with an ID with appropriate rights, and refresh the design of the Build Manager application. Do the same for Template Registry and Approvals workflow application, if applicable.

!!! note
    Please note that Build Manager 9.1 requires a valid version 9.1 License Number and Key to use the product.
    
## Fix List
### 9.1.0 

[186245437] Dialog for adding standard paths is empty on Notes 12.0.2+  
[186276395] Update help links to use the new help site  
[186284271] Fix "Registry Target Servers Lookup Failed" error  
[186436098] Update TeamstudioBuildManager.exe and LotusScript DLL calls to 64 bit
