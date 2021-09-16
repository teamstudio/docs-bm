# Project Builds

A *Project Build* specifies multiple Promotion Paths and allows them to be run in order, with a single click.

To create a project build, navigate to the *Paths|Project Builds* view.
<figure markdown="1">
  ![Project Builds View](img/projectbuild.png)
</figure
>
Click *New Project Build* to create a Project Build.
<figure markdown="1">
  ![New Project Build](img/projectbuild2.png)
</figure>

Set the *Description* field, and click *Add* to select the Promotion Paths the Project Build should include. Order the Promotion Paths in the order they should run. Optionally, select *Continue with next promotion after failure* if additional promotions should continue to run after one of the promotions fails. Save the Project Build.

To run a Project Build, select the promotion in the Project Builds view, and click *Promote*. The promotions run serially in the order specified. A log is created for the overall Project Build, and a separate log is created for each specific Promotion Path, and can be viewed in the Logs views.
<figure markdown="1">
  ![Logs view](img/projectbuild3.png)
</figure>

