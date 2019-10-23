# SFEC_TO_WFS_CPI
 SF EC integration to WFS using CPI as Middleware

## Introduction

This project will integrate SF EC to Kronos Workforce Software using the SF Odata API.

The integrations already exist, but it's up to me to fix them as there are some issues.  It was created and running in DEV, but now it has to be moved to QA and fixed to work there.

There are  3 processes that are working.

We will need to modify one of these process to retrieve the correct data but also read the data from the SF Test instance instead of the Dev.

In theory, if we execute that interface, these employees should be recreated again. But it seems not to be the case, we don’t get any error though…
 
We really need to make sure this interface is still working, before John make the adjustment and read data from SF Test.
Do you think you can have a quick look at that standard interface why nothing is being sent to WFS ?

Link to main documentation:
[Click here.](sf_ec_to_wfs_using_cpi.md)
