# Release Notes

Build Manager 9.0.1 is a fix release of Build Manager 9.0.  See the Fix Lists section below for specific details.

The Build Manager 9.0 release focuses on three specific enhancements:  a new Build Automation / Command-Line interface for running promotions, significant improvements to the Design Refresh / Design Replace steps, and a refreshed UI design.

* **Command-Line Promotions** The executable included with Build Manager, TeamstudioBuildManager.exe, can now be used to run promotions.  Promotions can be automated and triggered by external applications such as Continuous Integration servers and Deployment Management software, allowing integration with builds for related projects via technologies like ANT and Jenkins.  External programs can capture the output of the Build Manager promotion log, and determine the status of the promotion via the command's exit code.  For more information, see [Automating Promotions using the Build Manager Executable](automating.md).
* **Design Refresh Improvements** Build Manager now provides more information about the Design Refresh process, including verifying that the newly promoted template has the expected template name prior to beginning a refresh, reporting on template name conflicts, and preventing refresh/replace attempts when the template name is not set on the promoted template.  The Design Refresh option has also been updated with options to bring it more in line with the design replace the behavior of the Notes client; it can now be set to leave the new template name in the target database, and it does not mandate the deletion of the design elements in the target before the replace.
* **Updated UI Design** The look and feel of the Build Manager suite of databases has been updated, including new logos and a more modern color scheme.  Dynamic Help (F1 or Help > Dynamic Help) now links to sections of this documentation.

## Upgrading
To upgrade the Build Manager NSF, sign the template with an ID with appropriate rights, and refresh the design of the Build Manager application. Do the same for Template Registry and Approvals workflow application, if applicable.

To upgrade the Status Plugin, open the updated Build Manager NSF, and choose *Actions|2. Install Status Plugin*. Accept the prompt to allow the installation, and to restart Notes when the installation is complete. This action must be performed on each workstation used to run Build Manager promotions if the workstation is configured to use the Status Plugin.

!!! note
    If the Status Plugin displays a blank screen after restart, close the tab with the Status Plugin,
    and re-open it from Build Manager via *Actions|1. Show Status Plugin*. If the plugin has installed
    correctly, it will display the Build Manager logo in the top part of the screen.
    
More information on installing the Status Plugin can be found [here](installplugin.md).

If a promotion is attempted before the plugin has been upgraded on a workstation, Build Manager will prompt to install the new version of the plugin, and exit the promotion.

If you previously used a workaround for issue TMS-620, you can safely remove any CIAO!, Configurator, or Analyzer DLLs copied to the Notes executable directory. Installing a new version or uninstalling and reinstalling these tools will also do this.

!!! note
    Please note that Build Manager 9.0 requires a valid version 9.x License Number and Key to use the product.
    
## Fix List
### 9.0.1    
[TMS-1366] - Allow blank target file name in Promotion Paths  
[TMS-1291] - Fix error when clicking Refresh Agents button on Agent steps if the source is a Template Registry  
[TMS-1292] - Fix issue where installation check can fail and continue prompting to install  
[TMS-1293] - Shell Command step now closes the target DB handle to allow external programs to act on the new template  

### 9.0.0
[TMS-390] - Add Template Registry 'Deployment Tracking' to Standard Paths  
[TMS-417] - Create Test Data step for Domino source fails due to erroneous validation if Network Share field is blank  
[TMS-1098] - Allow use of Notes' built-in column icons (specified by number) in Custom Actions  
[TMS-1200] - Prevent the setting of DB Titles that include new-line characters, which can cause database issues  
[TMS-1240] - Hide 'Load From' option on new Stored ID documents  
[TMS-1256] - Fix issue where Template Registry Change report can contain unrelated results under certain circumstances  
[TMS-1262] - Add command-line promotion function to allow integration with build and deployment systems  
[TMS-1267] - Fix issue where pending Workflow Approvals can inadvertently authorize sibling Promotion Paths in some situations  
[TMS-1278] - Log information about other files using the same template name, when the template name cannot be set during the promotion  
[TMS-1279] - Do not allow design refresh/replace if the template name isn't set on the promoted template  
[TMS-1280] - Add options to the Design Replace step to more closely reproduce the Notes Client's Design Replace behavior  
[TMS-1282] - Fix issue with Notes 10 Action Bars displaying broken gradient overlays