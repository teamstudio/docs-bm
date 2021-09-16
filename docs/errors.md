# Common Error Messages

This section covers the causes of some common errors in the Build Manager promotion log.

## Your Address Book does not contain any cross certificates capable of authenticating the server
#### Sample Log
```
11/03/2006 05:06:49 PM EST: :  Calling sign utility...
11/03/2006 05:06:51 PM EST: :  Error: Your Address Book does not contain any cross certificates capable of authenticating the server.
11/03/2006 05:06:51 PM EST: :  Action Failed: actSIGN
```
#### Cause
The signing utility in Build Manager is detached to your local data directory to run. This error indicates that the ID being used by the signing utility does not have a cross certificate in your **local** name and address book for the server where the promotion was targeted. Have your administrator create a cross certificate in your local name and address book.

## Unable to find path to server
#### Sample Log
```
11/03/2006 04:22:22 PM EST: :  Calling sign utility... 
11/03/2006 04:22:29 PM EST: :  Error: Unable to find path to server
11/03/2006 04:22:29 PM EST: :  Action Failed: actSIGN
```
#### Cause
The signing utility in Build Manager is detached to your local data directory to run. This error indicates that the ID being used by the signing utility cannot find the correct connection document for the target promotion server in your **local** name and address book. This is exacerbated by the fact there could be multiple local name and address books. Have your administrator create the correct connection documents in all of your local name and address books. Or, use your standard Notes client for promotions.

## You are not authorized to promote database
#### Sample Log
```
11/03/2006 03:17:28 PM EST: :  You are not authorized to promote this database with the selected promotion path.
11/03/2006 03:17:28 PM EST: :  Promotion failed.
```
#### Cause
The ID you have used to sign onto the Notes client is not present in the promote authority field on the promotion path document in Build Manager for the database you are attempting to promote. This field is checked to see if you have rights to press the promote button for this database. This field supports groups.
Have your administrator add your name explicitly to the promotion authority field or to one of the groups (in the domino directory) that are present in the promote authority field on the stored server document for the promotion target server.

## Database properties could not be set
#### Sample Log
```
11/03/2006 03:43:42 PM EST: : Set Database inherit from to:
11/03/2006 03:43:42 PM EST: :  Database properties could not be set. Most likely cause is that the master template name was already in use. Check the log.nsf database on the destination server.
11/03/2006 03:43:42 PM EST: :  Action Failed: actDBPROP
```
#### Cause
There are two potential reasons for this issue.

First, the ID being used for changing the database properties in the database properties step does not have permissions on the target server to create master templates. If the promotion path does not switch to another ID to perform the promotion (i.e. Perform Promotion as someone else) then it is the ID you used to sign onto the Notes client. If the promotion path does switch to another ID, then it is the ID used by Build Manager.

Have your administrator add the name of the ID being used to the *Create master templates* field on the target server document in the domino directory or to one of the group documents in the Domino Directory that are already present in the *Create master templates* field on the target server document in the domino directory.

Second, the master template name the program is attempting to implement on the promoted database is already in use. This applies only for Notes 6.x.x servers and above. Investigate where the master template name is currently being used and change it or change the master template name you are currently attempting to implement.

## CIAO must be installed to use this feature
#### Sample Log
```
10/04/2006 03:22:01 PM EDT: :  Database copied to : Templates\Colonypo.ntf On JBXNU01/APPS/SRV/FPLDEV 10/04/2006 03:22:01 PM EDT: : Error: CIAO Must be installed to use this feature. on line
20 in MAKEVERSION
10/04/2006 03:22:01 PM EDT: :  Action Failed: actMAKEVERSION
```
#### Cause
Teamstudio CIAO is not installed or implemented properly on the workstation attempting the promotion.
This only happens if there is a make version action in the promotion process. 

There are multiple reasons for this, the least of which is that CIAO is not installed. If CIAO is not installed, install it or deactivate the Make Version step in the promotion process. 

If CIAO! is installed and not implemented correctly you should contact Teamstudio support.

## Failed to bump version number
#### Sample Log
```
10/20/2009 11:12:50 AM CDT: The log document does not have any version numbers. using initial values from config document
10/20/2009 11:12:50 AM CDT: WARNING: Version was successful, but failed to bump version number. (@1)
10/20/2009 11:12:50 AM CDT: Action Failed: actMAKEVERSION
```
#### Cause 
The Teamstudio CIAO Log, as defined on the Teamstudio CIAO Configuration document, does not contain any Database Version History for the database being promoted. Open the database in Teamstudio CIAO, and make a version of it.
 
## Incorrect Stored or Attached ID Being Used
#### Sample Log
```
10/04/2006 03:29:50 PM EDT: :  Found stored id: FPL Template Signer'
10/04/2006 03:29:50 PM EDT: :  Error: Type mismatch on line 65 in DETACHID
10/04/2006 03:29:50 PM EDT: :  Error: Could not detatch id file 10/04/2006 03:29:50 PM EDT: :  Action Failed: actSIGN
```
#### Cause
This typically indicates that the password entered for the stored or attached ID being used by the signing utility is incorrect.
Have your administrator check the signing step in the promotion process being used to see if it is an attached ID or a stored ID and then go to the document for the ID being used and reenter the password.

## Unchanged Documents Being Promoted
#### Sample Log
```
10/05/2006 03:41:21 PM EDT: :  Calling sign utility... 
10/05/2006 03:41:21 PM EDT: : Error: No documents have been modified since specified time.
10/05/2006 03:41:21 PM EDT: :  Action Failed: actSIGN
10/05/2006 03:41:21 PM EDT: : Promo
```
#### Cause
You are attempting to promote documents that have not changed since the last promotion.

## No ID File Attached
#### Sample Log
```
01/17/2007 10:54:06 AM EST: :  Found stored id: Test ID'
01/17/2007 10:54:06 AM EST: :  Error: Type mismatch on line 65 in DETACHID
01/17/2007 10:54:06 AM EST: :  Error: Could not detatch id file
01/17/2007 10:54:06 AM EST: :  Error: Could not switch to 'Promot As' ID. Promotion Failed.
```
#### Cause
This error is due to the fact that there is no ID file attached to the promotion path document in the *Promote As* area or, if that area is using a stored ID, there is no ID file attached to the stored ID document. This could be due to forgetting to attach the ID file, in which case simply attach the appropriate ID to the appropriate document. It could also be due to attempting to attach an ID to the appropriate document while signed in on a Notes R 6.5.4 client. The method we use to attach IDs to documents so that you cannot get to them is not supported in the
R 6.5.4 client.

## Promoting Database with Design Notes Still Checked Out in CIAO!
#### Sample Log
```
02/06/2007 03:57:23 PM EST: : Error: CIAO!: Some design notes are still checked out.  
You must check in all design notes before performing that action.
02/06/2007 03:57:24 PM EST: : Action Failed: actMAKEVERSION
02/06/2007 03:57:24 PM EST: : Promotion failed.
```
#### Cause
There are some design elements still checked out in Teamstudio CIAO. Go back to the Teamstudio CIAO UI and check all design elements in.