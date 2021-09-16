# Build Steps

The simplest build path consists of a configuration document, describing the source template (or database), and a Promotion Path document, describing the target template location. On top of this Build Manager provides the ability to add any or all of the following optional steps.

* [ACL Settings](acl.md) - Sets the general ACL and specific ACL entries for the promoted template.
* [Approval](approval.md) – Implements an approval workflow for any stage of the build process where a template is moved. The date and approver are logged for audit purposes.
* [Compile LotusScript](compile.md) – Allows the compilation of all LotusScript or specific LotusScript elements within a promoted template as part of the build.
* [Create Test Data](testdata.md) – Reset test environments with data stored in an external location
* [Custom Step](customstep.md) – Create custom code that can be run by Build Manager as a step, to automate specific build requirements that cannot be met by existing steps.
* [Database Copy](dbcopy.md) – Allows another copy of the source template to be made and placed in a different location.
* [Database Properties](dbprops.md) – Allows the title, categories, inherited from template name and master template name to be set, cleared or left alone. Also, version information such as the Template Version, Name and Date as well as the $TemplateBuild shared field can be edited.
* [Design Audit](audit.md) – Calls Teamstudio Analyzer and checks the design of the source template against your coding and look and feel standards.
* [Element Properties](elemprops.md) – Allows the Prohibit Design Refresh flag, Propagate Prohibition flag, Design Element Inheritance option, and Design Element Comment field to be edited.
* [Email Notification](email.md) – Can be used to send email messages to individuals and/or groups at one or more points in a promotion.
* [Enable Agents](enableagents.md) – Allows scheduled agents in the template to be enabled or disabled.
* [Make Version](version.md) – Calls Teamstudio CIAO! and makes a controlled version of the design template.
* [Modify-only](modify.md) - An advanced Build step option to run Modified-Only builds that help reduce the impact of design refreshes on production servers. 
* [Refresh/Replace Design](refresh.md) – Allows one or more target databases to have their designs refreshed or replaced with the promoted template.
* [Run Agent](runagent.md) – Allows any external agent to be run and parameters to be passed as part of a build. Commonly used to create test databases containing clean data in builds to test environments, but can be used to supplement the capabilities of Build Manager with custom functionality.
* [Run Command](runcommand.md) – Run an external program or command via shell script.
* [Search and Replace](star.md) – Calls Teamstudio Configurator allowing a search and replace to be done as part of the build. This is an excellent way to stamp user-visible elements of the design with the version number and the date of creation.
* [Send Console Command](console.md) – Send a remote console command to a Domino server.
* [Set Agent On Behalf Of](behalf.md) – Allows scheduled agents in the template to be set to run on behalf of a particular user ID.
* [Set Agent Server](agentserver.md) – Allows scheduled agents in the template to be assigned a server to run on.
* [Sign Database](signdb.md) – Allows the design (or database) to be signed by a specific or stored ID as part of the build.
* [Switch ID](switchid.md) – Switch to a different Notes ID for part of a Promotion.
