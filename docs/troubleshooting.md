# Troubleshooting

If unexpected build failures occur, there are two options that can be set to help diagnose the problem.

* Turn up logging. Click the *Build Manager* button on the toolbar and select *Settings...*. Change the *Logging Detail* from \*_Default_ to *All Function Calls*. Promote again and check the log.
* Run actions in the foreground.  Click the *Build Manager* button on the toolbar and select *Settings...*’.  Uncheck (deselect) the *Run utilities in background* option.

Three general principals apply to debugging promotion paths

* Disable all actions  Make sure this works before enabling the actions one at a time.  After enabling each action, run the promotion again.
* You can only be sure that a promotion has been defined correctly if it can be run twice.  If the ACL of the target has been set incorrectly the promotion may work the first time, but on the second time, it may be that the ACL of the target does not allow the signing ID to overwrite it during the second promotion.
* If a particular step fails, try and perform the step manually. For example, if a LotusScript recompile fails, go into Domino Designer, switch to the ID being used during the promotion (if necessary) and try *Tools|Recompile All LotusScript*.