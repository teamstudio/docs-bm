# Release Notes

Build Manager 9.1 is a feature release of Build Manager adding support for 64 bit Notes clients. On 64 bit clients, the Build Manager utility executable is now named *TeamstudioBuildManager64.exe* rather than *TeamstudioBuildManager.exe*. Build Manager will detect whether it is running on a 64 or 32 bit client and install the correct executable automatically.

From this release onwards, the LotusScript source code for Build Manager is no longer hidden. There are no changes to the licensing terms, but we hope that being able to read the code will help with making the best use of Build Manager in your environment.

Owing to complications with library dependencies, the *Test Data* step is not available on 64 bit clients. There are no other differences between the 64 and 32 bit versions.

## Upgrading
There is no need to upgrade to Build Manager 9.1 if you will be continuing to run Build Manager with a 32 bit Notes client. While future versions will be based on 9.1, Build Manager 9.0.1 remains fully supported and is currently functionally equivalent to 9.1 on 32 bit.

To upgrade the Build Manager NSF, sign the template with an ID with appropriate rights, and refresh the design of the Build Manager application. Do the same for Template Registry and Approvals workflow application, if applicable.

!!! note
    Please note that Build Manager 9.1 requires a valid version 9.1 License Number and Key to use the product.
    
## Fix List
### 9.1.3
[41] Fix 'External function not found' error when switching ID

### 9.1.2
[188260053] Signing step crashes or errors on 64 bit   
[188261244] Error displaying stored templates in Template Registry

### 9.1.1
[188122956]	Promotions from Template Registry crash on 64 bit  
[188122946]	Promotions to Template Registry may silently fail on 64 bit  
[188122936]	DB Properties step can fail with a message about missing '$TemplateBuild_Blank'  
[188152283]	Fix 'Type mismatch on external name' errors in bmconfig.ntf

### 9.1.0 

[186245437] Dialog for adding standard paths is empty on Notes 12.0.2+  
[186276395] Update help links to use the new help site  
[186284271] Fix 'Registry Target Servers Lookup Failed' error  
[186436098] Update TeamstudioBuildManager.exe and LotusScript DLL calls to 64 bit  
[186633171] Fix 'Create Switch ID' action to launch the correct form  
[187147388] Disable Test Data step on 64 bit