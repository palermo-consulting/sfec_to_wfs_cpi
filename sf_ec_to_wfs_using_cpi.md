# SF EC to WFS using CPI

## Introduction

This project will integrate SF EC to Kronos Workforce Software using the SF Odata API.

The integrations already exist, but it's up to me to fix them as there are some issues.  It was created and running in DEV, but now it has to be moved to QA and fixed to work there.

There are  3 processes that are working.

We will need to modify one of these process to retrieve the correct data but also read the data from the SF Test instance instead of the Dev.

In theory, if we execute that interface, these employees should be recreated again. But it seems not to be the case, we don’t get any error though…
 
We really need to make sure this interface is still working, before John make the adjustment and read data from SF Test.
Do you think you can have a quick look at that standard interface why nothing is being sent to WFS ?

## Documents Needed

The integration document for WFS can be found here
[SF_EC_INT_WorkForce_Software_CPI_en_Q3 2019](SF_EC_INT_WorkForce_Software_CPI_en_Q3 2019.pdf)
Documents for SF EC Odata API can be found at the SF EC Odata API repository.

## CPI Test Instance URL

The link for the CPI (test instance) for PSAC : https://e30002-tmn.hci.ca1.hana.ondemand.com/itspaces

## SF Test Instance URL

As discussed yesterday, here is the link and credential to PSAC SuccessFactors Test instance:
 
URL : https://hcm17preview.sapsf.com/sf/admin?bplte_company=publicservT1
User : adminjp
Initial Pwd: in KeePass for security reasons

Also found in KeePass

## SF OData Endpoint

The endpoint URL for Odata Service for the sales demo is : 
https://api17preview.sapsf.com/odata/v2/    

Username: adminjp@publicservT1
Password: In KeePass for security reasons.

## CPI Artifacts for this Project

* [Employee Central Cost Center to LD Workforce](./employee_central_cost_center_to_ld_workforce.md)
* Packaged Integration - SF EC to WFS
* Packaged Integration - SF EC to WFS - Custom Mapping
* Packaged Value Mapping - SF EC to WFS - TimeZones
* Packaged Value Mapping - SF EC to WFS - Employment Status

Each artifact has it's own MD file.  Click the links provided to go to the related MD file.  All MD files are in the current folder.
