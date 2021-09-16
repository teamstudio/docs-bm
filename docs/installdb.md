# Configuration Database
If you are not using CIAO!, create the Build Manager database from the supplied template.

If you are an existing Teamstudio CIAO! User, ensure that you have upgraded to Version 30 or above and that the CIAO! and Build Manager configuration databases are the same.

Go to CIAO Config and make a copy as a backup then refresh the CIAO Config design with Build Manager template. Sign it and test usual CIAO operations work.
 
The suggested basic ACL for each instance of the Build Manager database is

| Name | Type | Access | Roles | Permissions |
|---|---|---|---|---|
| -Default- | Unspecified | No Access | None | None |
| Anonymous | Unspecified | No Access | None | None |
| BM_ADMINISTRATOR | Person Group | Manager | IDADMIN, DATABASEADMIN, ADMIN, DELETEADMIN | All |
| BM_PATHBUILDER | Person Group | Editor | DATABASEADMIN, ADMIN, DELETEADMIN | Default for editor, without delete |
| BM_PROMOTER | Person Group | Author | FilteredUser | Default for author but with create documents |
| BM_APPROVER (Optional) | Person Group | Author | FilteredUser | Default for author but with create documents |
| LocalDomainServers | Server Group | Manager | IDADMIN, DATABASEADMIN, ADMIN, DELETEADMIN | All |

Note that the names of the BM_ADMINISTRATOR, BM_PATHBUILDER, BM_PROMOTER and BM_APPROVER groups are just for illustration in the above table, and can be named as desired. All promotion IDs and Signing IDs should have at least promoter access.