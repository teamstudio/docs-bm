# Database Properties

Set database properties.

## To Set Database Properties
1. Select the Build or Promotion Path that relates to the database or template that properties you want to set
2. Click the *Create* button and select *Database Properties*. The Database Properties document appears
   ![Database Properties](img/dbprops.png)
3. The Database Properties document is active by default. Leave this setting.
4. Enter a descriptive name in the *Description* field (for example, *Update DB Title on Production Server*).
5. To modify the title of the database, enter an appropriate value into the *Title* field. You can clear this property prior to running this action.
6. Enter one or more categories into the Categories field. You can clear this property prior to running this action.
7. Enter a template name from which the current database inherits, into the *Inherit From* field. The template name can also be removed using the *Clear This Property* option.
8. Enter a different template name if this is a master template.

If a field is blank and *Clear This Property* is not checked then no changes are imposed and the field keeps its original value.

Save and close the document.

The new Database Properties entry appears in the right pane, under the Build or Promotion Path to which it applies. 
<figure markdown="1">
  ![Database Properties in View](img/dbprops2.png)
</figure>