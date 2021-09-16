# Understanding CIAO Config Information

Teamstudio Build Manager is a superset of the functionality available in the Teamstudio CIAO configuration database, and can be used as a drop-in replacement for the CIAO configuration database.

Build Manager does not require CIAO to be installed for the majority of its functionality, such as promoting templates, deploying applications, and tracking release versions in a Template Registry.  However, understanding the basic concepts involved in configuring CIAO can be useful in configuring the Build Manager environment.

The source for any Promotion in Build Manager is a *Database Document*, which represents either

* A database (template) residing on a server, identified by the server and file path. This is the information that CIAO uses to identify a database under source control, and is often referred to as a *Watch Document*.
* A template version stored in a Template Registry, identified by the Stored Template Registry definition, and the Template Name of the template as defined in the Registry. The selection of the version (build) of the template to promote is defined in Promotion Paths attached to Database Documents that target Template Registry templates.

For more information about Promotion Paths and how they work with Database Documents, see [Promotion Paths](ppcreate.md).

The table below lists the fields that can be configured to control CIAO on a Database Document that specifies a database on a server. Only the Database Server, Database Path, and Project fields are relevant when using Build Manager without CIAO.

| Category | Description |
|---|---|
| Basics | Database Title, Database Server, Database Path, Project, CIAO! Watch Active, Log Server, Log Path |
| Watch | Watch Documents, Watch Template Linked Elements, CIAO! Owner in Note Comment, Mandatory Comments |
| Authority | Add, Check Out, Check In, Delete, Grab, Make Version |
| Issues | Copy Issue Settings, Issue Database Server, Issue Database Path, Issue Selection, Issue View, Issue Required |
| Versioning | Custom Version Label Settings |
| Advanced | DBID (the database ID of the watched database), Log Key |
