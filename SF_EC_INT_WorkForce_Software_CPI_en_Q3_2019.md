```
INTEGRATION GUIDE | PUBLIC
Document Version: Q3 2019 – 2019-09-
```
# Integrating SAP SuccessFactors Employee Central

# with WorkForce Software (SAP Cloud Platform

# Integration)

© 2019 SAP SE or an SAP

affiliate

company. All rights reserved.

## THE BEST RUN


## Content

**2** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
```

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud

- 1 What's New in this Guide.........................................................
- 2 Overview.....................................................................
- 2.1 Integration Options...............................................................
- 2.2 Time Management Business Process with SAP Time and Attendance Management.................
- 3 Employee Data Replication.......................................................
- 3.1 Prerequisites..................................................................
   - Configurations for Employee Central Compound Employee API............................
   - Preparations by WorkForce Software...............................................
- 3.2 Data Replication Specification......................................................
   - Person....................................................................
   - Personal Information [EC hris-element-id: personInfo]...................................
   - Phone Information [EC hris-element-id: phoneInfo].....................................
   - E-Mail Information [EC hris-element-id: emailInfo].....................................
   - Address Information [EC hris-element-id: addressInfo]..................................
   - Employment Information [EC hris-element-id: employmentInfo]............................
   - Compensation Information [EC hris-element-id: compInfo]...............................
   - Job Information [EC hris-element-id: jobInfo].........................................
   - Pay Compensation Recurring [EC hris-element-id: payComponentRecurring]..................
- 3.3 Getting Access to the Solution......................................................
   - Common Configuration Steps....................................................
- 3.4 Setting Up the Standard Data Integration..............................................
   - Scheduler Settings...........................................................
   - Receiver Settings.............................................................
   - Parameters.................................................................
   - Value Mappings..............................................................
- 3.5 Extending the Standard Data Integration..............................................
- 4 Integrating the WorkForce Software UI..............................................
- 4.1 Single Sign-On.................................................................
   - Employee Central Certification for WorkForce Software..................................
   - Configuration of Employee Central Identity Provider for WorkForce Software...................
   - Configure 'Time and Attendance' Link for WorkForce Software
- 5 Time Data Replication...........................................................
- 5.1 Utility Report..................................................................
- 5.2 Absence Data..................................................................
- 5.3 Remuneration Data..............................................................
- 5.4 Getting Access to the Solutions.....................................................
      - Common Configuration Steps....................................................
      - Setting Up the Standard Data Integration............................................
- 5.5 More About Data Replication.......................................................
   - Payroll....................................................................... 5.6 Configuring the Integration between SAP Time and Attendance Management and Employee Central
      - Configuring Absence Types.....................................................
      - Configuring Remuneration Wage Types.............................................
      - Configuring Technical Communication User..........................................
      - Setting Up ALE Scenario for IDoc.................................................
- 6 Troubleshooting...............................................................
- 7 Error Handling................................................................
- 7.1 Setting Permissions for the Execution Manager Dashboard.................................
- 7.2 Using the Execution Manager Dashboard..............................................
- 7.3 Event Details Table..............................................................
- Content PUBLIC Platform Integration)


## 1 What's New in this Guide.........................................................

This document describes changes to this guide for the recent releases.

Q2 2019
The following table summarizes changes to this guide for the Q2 2019 release and later

```
What's new Description More Info
```
```
Added scenarios on how best you can
customize a standard integration
```
```
You can see specific scenarios for map­
ping source and destination fields while
customizing a standard integration.
```
```
Extending the Standard Data Integration
[page 34 ]
```
```
Added a Timeout parameter for Work­
Force Software Web Service
```
```
You can now specify the time (in millisec­
onds) that the integration takes to estab­
lish a successful connection with WFS to
push data.
```
```
WorkForce Software Web Service [page
29 ]
```
```
Added a note on error message logging in
Execution Manager due to missing HIRE
Event information
```
```
If the HIRE Event information is missing
in the Compound employee API response
then this integration will log an error
message in Execution Manager.
```
```
Time Management Business Process
with SAP Time and Attendance Manage­
ment [page 9 ]
```
### Q1 2019

The following table summarizes changes to this guide for the Q1 2019 release and later

```
What's new Description More Info
```
```
A new parameter added for Query Com­
pound Employee receiver
```
```
You can now mention the number em­
ployee records that you want to process
in one go by specifying a value to the
Page Size parameter.
```
```
Query Compound Employee [page 28 ]
```
```
Added a note on not supporting contin­
gent workers
```
```
This integration does not support contin­
gent workers
```
```
Overview [page 8 ]
```
```
Added a note on not supporting rehiring
of inactive employees with new employ­
ment
```
```
This integration does not support rehir­
ing of inactive employees with new em­
ployment
```
```
Time Management Business Process
with SAP Time and Attendance Manage­
ment [page 9 ]
Added a section on Error Handling To monitor if an integration ran success­
fully or with errors, you can check the
logs in the Execution Manager Dash­
board. The failure messages displayed on
the Execution Manager Dashboard are
quite descriptive.
```
```
Error Handling [page 69 ]
```
### Q3 2018

The following table summarizes changes to this guide for the Q3 2018 release and later

**4** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
What's New in this Guide
```

```
What's new Description More Info
```
```
Added a note on concurrent employment This integration does not support con­
current employee information.
```
```
Employee Data Replication [page 11 ]
```
### Q2 2018

The following table summarizes changes to this guide for the Q2 2018 release and later

```
What's new Description More Info
```
```
Updated Checking and Registering IDoc
Service section
```
```
Added a note on an error message that
may be displayed while checking if the
service is active
```
```
Checking and Registering IDoc Service
[page 64 ]
```
### Q1 2018

The following table summarizes changes to this guide for the Q1 2018 release and later

```
What's new Description More Info
```
```
Introduced a new parameter "Go-
live_Date", to the Parameters section
```
```
We have introduced a “Go-live_Date” pa­
rameter which ensures that the em­
ployee records in SAP SuccessFactors
Employee Central that are greater than
or equal to the "Go-live_Date" are sent to
the Workforce Software.
```
```
Parameters [page 30 ]
```
### Q3 2017

The following table summarizes changes to this guide for the Q3 2017 release and later

```
What's new Description More Info
```
```
Sections updated with SAP Time and At­
tendance Management instances
```
```
Updated EmpCenter instances with SAP
Time and Attendance Management in­
stance
```
```
Time Management Business Process
with SAP Time and Attendance Manage­
ment [page 9 ]
Employee Data Replication [page 11 ]
Data Replication Specification [page
13 ]
Setting Up the Standard Data Integration
[page 27 ]
Time Data Replication [page 41 ]
Setting Up the Standard Data Integration
[page 46 ]
Troubleshooting [page 68 ]
```
Q2 2017

```
What's New Description More Info
```
```
May 19, 2017
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**What's New in this Guide** PUBLIC **5**


```
What's New Description More Info
```
```
Updated the title of the guide. There are no changes to the guide for this
release. However, the title of the guide
has changed from Employee Central and
WorkForce Software to Integrating SAP
SuccessFactors Employee Central with
WorkForce Software.
```
```
Person [page 14 ]
Phone Information [EC hris-element-id:
phoneInfo] [page 15 ]
Personal Information [EC hris-element-
id: personInfo] [page 15 ]
E-Mail Information [EC hris-element-id:
emailInfo] [page 16 ]
Address Information [EC hris-element-id:
addressInfo] [page 17 ]
Employment Information [EC hris-ele­
ment-id: employmentInfo] [page 18 ]
Compensation Information [EC hris-ele­
ment-id: compInfo] [page 19 ]
Job Information [EC hris-element-id: jo­
bInfo] [page 20 ]
Pay Compensation Recurring [EC hris-el­
ement-id: payComponentRecurring]
[page 25 ]
Absence Data [page 42 ]
Remuneration Data [page 43 ]
```
```
March 28, 2017
```
```
Sections updated with mandatory fields Marked certain fields as mandatory in
some sections.
```
```
November 16, 2016
```
```
Added information on Time Data Replica­
tion
```
```
To include Time Data Replication Time Data Replication [page 41 ]
```
```
July 27, 2016
```
```
Updated Parameters section
Updated Receiver section
Updated extending the standard data in­
tegration section
```
```
Replaced old screenshot with new one
Added Sender and Receiver information
```
```
Parameters [page 30 ]
```
```
Extending the Standard Data Integration
[page 34 ]
```
```
May 25, 2016
```
```
Updated Parameters and Receivers sec­
tion.
```
```
Added and deleted the relevant cases. Parameters [page 51 ]
```
**6** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
What's New in this Guide
```

```
What's New Description More Info
```
```
September 28, 2015
```
```
Integrating Employee Central with Work­
Force Software SAP Time and Attend­
ance Management.
```
```
Added information on integrating Em­
ployee Central with WorkForce Software
SAP Time and Attendance Management.
```
```
Overview [page 8 ]
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**What's New in this Guide** PUBLIC **7**


## 2 Overview.....................................................................

This guide is for SAP Support or partner consultants to integrate SuccessFactors Employee Central with SAP Time
and Attendance Management.

WorkForce Software is a Solution Extension partner. Integration is through a standard integration catalog for
validated time management providers. This is an out-of-box way to integrate Employee Central with validated third-
party time management providers. No manual data mapping is needed. For more information about Employee
Central, see the Employee Central implementation guide.

 Note

```
This integration does not support contingent workers.
```
```
Integration Options [page 8 ]
Use the following process steps as a guideline to successfully integrate Employee Central with SAP Time
and Attendance Management. This is a simplified approach to a possible integration process.
Time Management Business Process with SAP Time and Attendance Management [page 9 ]
SAP Time and Attendance Management can be integrated with Employee Central using role-based
permissions.
```
## 2.1 Integration Options...............................................................

Use the following process steps as a guideline to successfully integrate Employee Central with SAP Time and
Attendance Management. This is a simplified approach to a possible integration process.

**Context**

You will need to adjust these process steps based on the customer's business requirements. Following is an
overview:

**Procedure**

1. Set up Employee Central.

```
For more information, see the Employee Central implementation guide.
```
2. Make third-party provider-specific settings, for example, SFTP server accessibility.
3. Get access to the catalog in SAP Cloud Platform Integration Spaces.

**8** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Overview
```

4. Set up the data integration.

## 2.2 Time Management Business Process with SAP Time and Attendance Management.................

SAP Time and Attendance Management can be integrated with Employee Central using role-based permissions.

**Context**

The process to integrate SAP Time and Attendance Management with Employee Central is as follows:

**Procedure**

1. The HR administrator enters the employee data into Employee Central (such as new hire, rehire, transfer,
    termination, or change data).
2. An API in Employee Central extracts the required employee data for replication to SAP Time and Attendance
    Management.
3. SAP Cloud Patform Integration (a mapping and integration tool) replicates the data to SAP Time and
    Attendance Management.
4. The following data is currently transferred from Employee Central to SAP Time and Attendance Management:
    ○ Employee master data (name, address, phone, email, and so on)

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Overview** PUBLIC **9**


```
○ Employment and job (hire date, manager, and so on)
○ Compensation (annual salary, total compensation)
○ Life event notification
```
```
 Note
○ This integration does not support rehiring of inactive employees with new employment. To see this
option on the UI:
```
1. Navigate through _Admin Center Manage Permission Roles_.
2. Select the permission role you want to configure.
3. On the Permission Settings page select Manage User, _do not select_ the Rehire inactive Employee
    with New Employment ('by match'in New Hire) option.
○ The HIRE event information is mandatory to replicate an employee from SAP SuccessFactors
Employee Central to WorkForce Software. For some reason if the HIRE Event information is missing in
the Compound employee API response then this integration will log an error message in Execution
Manager and will not process that employee data further.
5. From Employee Central, employees navigate to SAP Time and Attendance Management to record or manage
working times according to the business roles assigned to them in SAP Time and Attendance Management.
6. SAP Time and Attendance Management validates the times entered and sends the time data to Payroll for
processing.

**10** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Overview
```

## 3 Employee Data Replication.......................................................

This chapter describes the process of replicating employee data from Employee Central to SAP Time and
Attendance Management.

**Context**

It comprises the following steps:

**Procedure**

1. A scheduled SAP Cloud Platform Integration job extracts the employee data from Employee Central as per the
    configured scheduled time.
2. The extracted data is mapped to and conforms to a WSDL published by WorkForce Software.
3. SAP Cloud Platform Integration calls the Web service and sends the employee data to SAP Time and
    Attendance Management.
    The employee import supports the following data:
       ○ New hire
       ○ Terminations
       ○ Rehire
       ○ Employee - manager relationship assignments
4. 4. After the data is received, employee import processing is carried out in SAP Time and Attendance
    Management. The import processing includes:
       ○ Transforming the fetched data based on mapped data elements
       ○ Staging and applying business rules
       ○ Storing employee data in the SAP Time and Attendance Management database

 Note

```
These specifications apply to the version for the United States. If a customer implements a version for
another country, some adjustments may be necessary.
SAP Time and Attendance Management expects the data extraction process via SAP Cloud Platform
Integration to return all configuration data fields in a single row.
```
```
The SAP Cloud Platform Integration process does not support the global assignment feature. Any global
assignment data passed is ignored.
```
```
This integration does not support concurrent employee information.
```
```
Data Replication Specification [page 13 ]
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **11**


```
The integration between Employee Central and SAP Time and Attendance Management requires that the
fields in Employee Central be mapped to the fields used in WorkForce Software.
Getting Access to the Solution [page 25 ]
SAP Cloud Platform Integration Spaces is a Web-based application that helps you to access the integration
content available for a particular tenant in an on-demand integration infrastructure.
Setting Up the Standard Data Integration [page 27 ]
The Discover section, click the SuccessFactors Employee Central with Third Party Time Vendor-WorkForce
Software(WFS) integration process and configure the Packaged Integration - SF EC to WFS integration flow.
Extending the Standard Data Integration [page 34 ]
You can customize the current integration solution by mapping additional fields from Employee central to
WorkForce Software.
```
## 3.1 Prerequisites..................................................................

**3.1.1 Configurations for Employee Central Compound Employee**

**API**

The compound employee API for Employee Central extracts the employee data from Employee Central. It returns
the employee data in a hierarchically structured response XML (root node: employee person data).

Choose your regional API endpoint from the table below:

```
Location End Point
```
```
USA, HCM Preview https://api4preview.sapsf.com/sfapi/v1/soap
```
```
USA, Arizona https://api4.successfactors.com/sfapi/v1/soap
```
```
USA, Ashburn https://api8.successfactors.com/sfapi/v1/soap
```
Get the generic WSDL by adding ?wsdl to the above addresses. For example, https://api.successfactors.eu/
sfapi/v1/soap?wsdl

Apart from the endpoints, an XML schema is provided that describes the XML response of the compound
employee API including all substructures and elements. The XML schema is required for integration purposes. It
needs to be maintained manually as part of the development process. The new API only provides the query and
queryMore operation. All other operations such as list, describe, and describeEx are not supported.

More settings may be required for the following:

```
● Web service setup
Follow the standard process for SFAPIs to set up SFAPI operations log in, log out, and to enable the API.
● Thresholds and limits
The compound employee API has similar thresholds and limitations as the other SFAPIs. You can set this
number to a value between 1 and 800 by specifying the maxRows parameter in the query method.
● API enhancements and compatibility
```
**12** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
The API response message type can be enhanced with additional elements and attributes. Additional elements
and attributes can be supplied by SAP or SuccessFactors and by using custom fields. The external application
must be able to process the extended response successfully. The API request message type can be enhanced
by new processing and query string parameters (for example an additional parameter for selecting or filtering
data). Enhancements of request message types and parameters are always optional. The system does not
require the external application to provide optional values and parameters in the request.
```
**3.1.2 Preparations by WorkForce Software**

The customer should sync on the following points for initial setup preparations to be done by WorkForce Software:

```
● Functional preparation
For example, availability of a document such as Discovery and Requirements Gathering
● Group and time plan setup
○ Technical setup of employee file
For example, availability of documents such as Integration and Data Migration Discovery
○ SFTP server configuration
```
## 3.2 Data Replication Specification......................................................

The integration between Employee Central and SAP Time and Attendance Management requires that the fields in
Employee Central be mapped to the fields used in WorkForce Software.

If you do not use the integration pack, the mapping must be completed in Provisioning by SuccessFactors
Professional Services. Check the tables below to see which of the Employee Central entities and fields are required
to replicate data from Employee Central. The table also shows which fields you need to map manually and the
corresponding picklist IDs. You will also find descriptions of which mapping activities are necessary for different
fields.

The replication of employee master data from Employee Central to SAP Time and Attendance Management uses
the CompoundEmployee service from Employee Central.

```
For Information on Compound Employee Element Structure
... See HRIS-Element
```
```
Personal Information Personal Information [EC hris-element-id: personInfo]
```
```
Phone Information Phone Information [EC hris-element-id: phoneInfo]
```
```
Email Information E-Mail Information [EC hris-element-id: emailInfo]
```
```
Address Information Address Information [EC hris-element-id: addressInfo]
```
```
Employment Information Employment Information [EC hris-element-id: employmen­
tInfo]
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **13**


```
For Information on Compound Employee Element Structure
... See HRIS-Element
```
```
Compensation Information Compensation Information [EC hris-element-id: compInfo]
```
```
Job Information Job Information [EC hris-element-id: jobInfo]
```
```
Job Relationships
The time data entry of employees has to be approved by an au­
thorized person. Currently, we support approvals by the super­
visor assigned to the employee in Job Information. If you re­
quire time approvals to be done by someone other than the su­
pervisor, you can use job relationship information to derive the
different approver. As such, Job Information is included as part
of the data extract from the Compound Employee API.
```
```
Job Relationships [hris-element-id: jobRelationsInfo]
```
```
Pay Compensation Recurring Pay Compensation Recurring [EC hris-element-id: payCompo­
nentRecurring]
```
**3.2.1 Person**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Person_id_external Person_id_external Required No No Person/exter­
nal_hr_id
Person/user_data/
empcenter_login_id
Person_em­
ployee_data/
assignment/
eff_dated_info/
data/badge-id
Person/
user_data_authen­
tication_match_id
```
```
Date_of_birth Date of birth Optional No No Birth_date
```
```
Custom_string_1 Required No No Person/user_data/
user_role-match_id
```
 Note

```
The snapshot field "asOfDate" is mapped to:
```
**14** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
● Person/employee_data/assignment/eff_dated_info/data/effective_date
● Person/employee_data/eff_dated_info/data/effective_date
```
**3.2.2 Personal Information [EC hris-element-id: personInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
First_name Employee's first
name
```
```
Required No No first_name
```
```
Middle_name Employee's middle
name
```
```
Optional No No middle_name
```
```
Last_name Employee's last
name
```
```
Required No No last_name
```
```
Gender Employee's gender Optional No No employee_data/
eff_dated_info/
data/gender
```
```
Native preferred
language
```
```
Employee's prefer­
red language
```
```
Optional No No employee_data/
eff_dated_info/
data/ language
```
```
Last_modified_on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
last_modification_time

Using the function Max Of time stamps, this WorkForce Software field saves the timestamp of the latest modified
employee data out of all the last modified fields in Employee Central.

**3.2.3 Phone Information [EC hris-element-id: phoneInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Phone type Optional No Yes phone_numbers/
type
```
```
Phone number Optional No No phone_numbers/
phone_number
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **15**


```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Last_modified_on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
phone_numbers/type

The Employee Central field Phone type is mapped to the WorkForce Software field phone_numbers/type using the
value-mapping table Phone Types. This table is defined in the value-mapping project in SAP Cloud Platform
Integration. It must be filled by the consumer based on the picklist and WorkForce Software values. Default
mapping values are available.

last_modification_time

Using the function Max Of time stamps, this WorkForce Software field saves the timestamp of the latest modified
employee data out of all the last modified fields in Employee Central.

**3.2.4 E-Mail Information [EC hris-element-id: emailInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Email_type Employee's email
type
```
```
Optional No Yes email_addresses/
type
```
```
Email_address Employee's email
address
```
```
Optional No No email_addresses/
email_address
```
```
Last modified on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
email_addresses/type

The Employee Central field Email_type is mapped to the WorkForce Software field email_addresses/type using the
value-mapping table Email Types. This table is defined in the value-mapping project in SAP Cloud Platform
Integration. It must be filled by the consumer based on the picklist and WorkForce Software values. Default
mapping values are available.

last_modification_time

Using the function Max Of time stamps, this WorkForce Software field saves the timestamp of the latest modified
employee data out of all the last modified fields in Employee Central.

**16** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

**3.2.5 Address Information [EC hris-element-id: addressInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Address1 Employee's first ad­
dress line
```
```
Optional No No home_address/
address 1
```
```
Address2 Employee's second
address line
```
```
Optional No No home_address/
address 2
```
```
Address3 Employee's third
address line
```
```
Optional No No home_address/
address 3
```
```
City Employee's city Optional No No home_address/city
```
```
State Employee's state Optional Yes No home_address/
state_or_province
```
```
Province Employee's prov­
ince
```
```
Optional Yes No home_address/
state_or_province
```
```
Country Employee's country Optional No No home_address/
country
```
```
Zip_code Employee's ZIP
code
```
```
Optional No No home_address/
postal_code
```
```
Last modified on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
home_address/state_or_province

A function determines whether this WorkForce Software field is mapped to the state field or the province field in
Employee Central. The field that is not null is used.

last_modification_time

Using the function Max Of time stamps, this WorkForce Software field saves the timestamp of the latest modified
employee data out of all the last modified fields in Employee Central.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **17**


**3.2.6 Employment Information [EC hris-element-id:**

**employmentInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
User ID Required No No employee_data/
assignment/
assign­
ment_match_id
```
```
End date Optional No No employee_data/
eff_dated_info/
data/termina­
tion_date
employee_data/
assignment/
eff_dated_info/
data/assign­
ment_end_date
```
```
Service date Required No No employee_data/
eff_dated_info/
data/
adjusted_hire_date
employee_data/
assignment/
eff_dated_info/
data/
adjusted_be­
gin_date
```
```
Start date Required No No employee_data/
assignment/
eff_dated_info/
data/seniority_date
```
```
Seniority date Optional No No employee_data/
assignment/
eff_dated_info/
data/seniority_date
```
**18** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Original start date Required Yes No employee_data/
eff_dated_info/
data/origi­
nal_hire_date
employee_data/
assignment/
eff_dated_info/
data/origi­
nal_assign­
ment_begin_date
employee_data/
assignment/
eff_dated_info/
data/latest_assign­
ment_begin_date
```
```
Last modified on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
```
Direct reports Optional Yes (if number of
direct reports is
greater than zero,
the constant value
is set)
```
```
No Person/user_data/
manager_types/
manager_type
```
**3.2.7 Compensation Information [EC hris-element-id:**

**compInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Pay group Optional No Yes employee_data/
assignment/
eff_dated_info/
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **19**


```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Pay type Required No No employee_data/
eff_dated_info/
data/
adjusted_hire_date
employee_data/
assignment/
eff_dated_info/
data/
hourly_salary_flag
```
```
Payroll ID Required No No employee_data/
assignment/
eff_dated_info/
data/
external_payroll_id
```
```
Last modified on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
**3.2.8 Job Information [EC hris-element-id: jobInfo]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Company Optional No Yes employee_data/
assignment/
eff_dated_info/
data/
company_code
```
```
Cost center Optional No No employee_data/
assignment/
eff_dated_info/
data/
cost_center
```
**20** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Custom string 9 Optional No No employee_data/
assignment/
eff_dated_info/
data/
union_code
```
```
Department Latest date of em­
ployee data change
```
```
Optional No No employee_data/
assignment/
eff_dated_info/
data/
department_code
```
```
Division Optional No employee_data/
assignment/
eff_dated_info/
data/
division_code
```
```
Empl status Optional Yes Yes employee_data/
eff_dated_info/
data/hr_status
employee_data/
assignment/
eff_dated_info/
data/
hr_status em­
ployee_data/
assignment/
eff_dated_info/
data/
is_terminated
Person/
employee_data/
assignment/
eff_dated_info/
data/assign­
ment_end_date
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **21**


```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
FTE Optional Yes No employee_data/
eff_dated_info/
data/
fulltime_equiva­
lency_percentage
```
```
Is full time em­
ployee
```
```
Optional No Yes employee_data/
assignment/
eff_dated_info/
data/fulltime_part­
time_flag
```
```
Is primary Required No No is_primary
```
```
Job code Optional No No employee_data/
assignment/
eff_dated_info/
data/
job_code
```
```
Job title Required No No employee_data/
assignment/
eff_dated_info/
data/
job_title
Person/
employee_data/
assignment/
eff_dated_info/
data/assign­
ment_description
```
**22** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Location Optional No No employee_data/
assignment/
eff_dated_info/
data/
district_code
employee_data/
assignment/
eff_dated_info/
data/
region_code
employee_data/
assignment/
eff_dated_info/
data/
location_code
```
```
Manager ID Optional No No employee_data/
assignment/
eff_dated_info/
data/manager_ids/
manager_id/
manager_id
```
```
Pay grade Optional No No employee_data/
assignment/
eff_dated_info/
data/pay_grade
```
```
Position Optional No No employee_data/
assignment/
eff_dated_info/
data/
job_level
```
```
Last modified on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
```
Timezone Required No Yes Person/
employee_data/
assignment/
eff_dated_info/
data/time_zone
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **23**


```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Regular_temp Optional No Yes Person/
employee_data/
assignment/
eff_dated_info/
data/employ­
ment_type
```
```
Event Required Yes No Person/
employee_data/
assignment/
eff_dated_info/
data/latest_assign­
ment_begin_date
```
```
Flsa_status Optional No No Person/
employee_data/
assignment/
eff_dated_info/
data/flsa_status
```
```
Standard_hours This value is div­
ided by working­
DaysPerWeek to
obtain WorkForce
Software stand­
ard_daily_hours
```
```
Optional Yes No Person/
employee_data/
assignment/
eff_dated_info/
data/stand­
ard_daily_hours
```
```
workingdaysPer­
Week
```
```
This value divides
Employee Central
Standard_hours to
obtain WorkForce
Software stand­
ard_daily_hours
```
```
Optional Yes No Person/
employee_data/
assignment/
eff_dated_info/
data/stand­
ard_daily_hours
```
employee_data/assignment/eff_dated_info/data/is_terminated

This field is chosen through a value-mapping lookup ECWF-EC EMPL STATUS TO HR STATUS from the Employee
Central empl status.

employee_data/eff_dated_info/data/fulltime_equivalency_percentage

This field is mapped from the Employee Central FTE through the mapped function math multiply.

employee_data/assignment/eff_dated_info/data/fulltime_parttime_flag

This field is mapped through a value-mapping lookup ECWF-EC FULLTIME_PARTTIME to "is full time employee" of
Employee Central.

**24** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

**3.2.9 Pay Compensation Recurring [EC hris-element-id:**

**payComponentRecurring]**

```
Employee Central
Field Label Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired?
```
```
WorkForce Soft­
ware Field
```
```
Currency code Optional No Yes phone_numbers/
type
```
```
Pay com value Optional No No phone_numbers/
phone_number
```
```
Last_modified_on Latest date of em­
ployee data change
```
```
Required Yes No last_modifica-
tion_time
```
```
Frequency Optional No No Person/
employee_data/
assignment/
eff_dated_info/
data/pay_rate/
frequency
```
```
Pay_compo­
nent_type
```
```
Optional No No employee_data/
assignment/
eff_dated_info/
data/pay_rates/
pay_rate/type
```
## 3.3 Getting Access to the Solution......................................................

SAP Cloud Platform Integration Spaces is a Web-based application that helps you to access the integration content
available for a particular tenant in an on-demand integration infrastructure.

In SAP Cloud Platform Integration Spaces, you can access integration packages with artifacts such as value
mappings, integration flows, and files. For more information, see Viewing Integration Flow Configurations in the
Developer's Guide for Managing Integration Content.

You can edit and configure a package as follows:

1. On the _Discover_ tab, click the integration package to be configured.
2. Choose _Copy_ (as shown in the following figure).
    On the _Design_ tab, you should now find the copied package.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **25**


3. To configure and edit the package, follow Editing Integration Flow Configurations in the SAP Cloud Platform
    documentation.

**3.3.1 Common Configuration Steps**

**3.3.1.1 SAP Credential Deployment**

To deploy the following artifacts, see Deploying and Editing a User Credentials Artifact in the Operations Guide for
SAP Cloud Platform Integration.

```
Artifact Description
```
```
SuccessFactors EC SFAPI Credentials These credentials are used to connect to the Employee Central
API servers with relevant API access enabled.
```
```
WorkForce SFTP Server Credentials These credentials are used to connect to the WorkForce Soft­
ware SFTP server.
```
For more information about SFTP-based communication, see the _SAP Cloud Platform Integration for Process
Integration_.

**3.3.1.2 Value Mapping Maintenance**

A set of value-mapping projects are delivered along with the standard process in this integration. It must be
deployed in the customer landscape so that the iFlows can refer to the value mappings. For information about using
and editing value mappings, see the _Developer’s Guide for Managing Integration Content_. For more information,
refer to section _Value Mappings_.

**26** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

## 3.4 Setting Up the Standard Data Integration..............................................

The Discover section, click the SuccessFactors Employee Central with Third Party Time Vendor-WorkForce
Software(WFS) integration process and configure the Packaged Integration - SF EC to WFS integration flow.

**3.4.1 Scheduler Settings**

You can configure the schedule for executing the integration based on business needs. Three options are available
as shown in the following figure.

```
 Tip
When testing the integration, we recommend choosing Run Once rather than scheduling it to run.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **27**


**3.4.2 Receiver Settings**

**3.4.2.1 Query Compound Employee**

This receiver helps you to connect to Employee Central.

```
Field Description
```
```
Address Employee Central URL, for example, https://api.successfac­
tors.com
```
```
Credential Name Name of artifact that was deployed in Common Configuration
Steps for SFAPI user credentials
```
```
Page Size The number employee records that you want to process in one
go. By default, the batch size is 200 which is configurable. The
maximum configurable batch size is 800. This configuration
will allow seamless processing of records without displaying
any Out of Memory errors.
```
```
Timeout (in min) The duration (in minutes) in which the query is sent to Suc­
cessFactors Employee Central and response is fetched back.
By default, the session time out value is 5 minutes and the
same is configurable.
```
**28** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

**3.4.2.2 WorkForce Software Web Service**

This receiver helps you to connect to SAP Time and Attendance Management.

```
Field Description
```
```
Address Employee Central URL, for example, https://test.successfac­
tors.com
```
```
Credential Name Deployed credential name that has the user name and pass­
word for the WorkForce Software system
```
```
Timeout (in ms) The amount of time (in milliseconds) that the integration takes
to establish a successful connection with WorkForce Software
to push data. By default, the Timeout value is set to 60000 ms.
```
**3.4.2.3 Mapping Extension**

This receiver helps you to connect to the custom Iflow.

```
Field Description
```
```
Address The URL captured after the custom Iflow is deployed.
```
```
Credential Name The credential that was used while deploying the custom Iflow.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **29**


**3.4.3 Parameters**

This page contains, Type 1, all set of parameters and Type 2, parameters that qualify for the Content Modifier. The
parameters listed in both Type1 and Type 2 can be customized. To configure the parameters, you can override the
default values.

```
Parameter Name Description
```
```
business_unit Include the foundation object externalCode if you want to in­
clude only employees associated with that foundation object.
```
```
Company Comma-delimited list filter (no blank spaces before/after
comma) for specifying the companies to include in the extract.
```
**30** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
Parameter Name Description
```
```
company_territory_code (Country) Enter a single company_territory_code (ISO-3). This field does
not accept multiple values.
```
```
CustomFieldMapping Specifies if you need to invoke the custom Iflow. You can pro­
vide true for invoking and false for not invoking the custom
Iflow.)
```
```
CustomFilters Comma-delimited custom filters for the Compound Employee
document in format "person/national_id_card/coun­
try=USA,GRE;person/person_id=117", etc.
```
```
division Include the foundation object externalCode if you want to in­
clude only employees associated with that foundation object.
```
```
ECWF_LAST_MODIFIED_ON In this dynamic process property, provide a timestamp value in
the format yyyy-mm-ddThh:mm:ss.sssZ (for example,
2015-01-01T00:00:00.000Z) for the first ever execution of the
process. The process then fetches the changes in the Em­
ployee Central system as of the provided timestamp value.
```
```
employee_class Comma-delimited list filter (no blank spaces before/after
comma) for specifying the employee classes to include in the
extract.
```
```
first_load_filter_terminated_employees When first_load_filter_terminated_employees filter is set to 1, it
does not send the list of terminated employees during the first
load or the first run of the process. When set to 0 it sends the
list of terminated employees during the first load.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **31**


```
Parameter Name Description
```
```
Go-live_Date This parameter specifies the Go-live_Date of the integration
between SAP SuccessFactors Employee Central and Workforce
Software.
```
 Note

```
The value for the Go-live_Date must be entered in the for­
mat yyyy-MM-dd. Only those records that are effective on
or after the Go-live_Date will be sent for all employees.
Once you provide a value for the Go-live_Date and execute
the integration, you must not make any more changes to
the value of this field.
Changes made to the Go-live_Date could create some in­
consistencies between SuccessFactors Employee Central
and Workforce Software, which will not be handled by this
integration.
```
```
Before providing a value to the Go-live_Date parameter, ensure
that you go through the following prerequisites.
Prerequisites
If an employee is already existing and is active in SAP Success­
Factors Employee Central before the Go-live_Date then it is
mandatory that you create a new record in SAP SuccessFac­
tors Employee Central for any one of the following SAP Suc­
cessFactors Employee Central entities having the Start Date of
the record equal to the Go-live_Date.
● Job Information
● Compensation Information
● Personal Information
● Address Information
This results in effective employee records being replicated in
Workforce Software starting from the Go-live_Date.
If you do not maintain the Go-live_Date, then this integration
behaves as before where all employee records from SAP Suc­
cessFactors Employee Central are sent to Workforce Software.
Consider the scenarios listed in the following table if you are
providing a value to the Go-live_Date.
```
**32** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
Parameter Name Description
```
```
Scenarios to consider before providing a value to the Go-
live_Date field
```
```
If an em­
ployee is... And... Then...
```
```
Which re­
sults in...
```
```
Active as of
the Go-
live_Date and
already repli­
cated to
Workforce
Software,
later, for the
same record,
if you termi­
nate the em­
ployee with a
date which is
before the
Go-live_Date
```
```
You execute
this integra­
tion
```
```
This termi­
nated record
will not be
sent to Work­
force Soft­
ware which
will lead to in­
consistencies
```
```
Making that
employee re­
cord invalid in
Workforce
Software
```
```
Who is termi­
nated in SAP
SuccessFac­
tors Em­
ployee Cen­
tral before the
Go-live_Date,
and there ex­
ists another
record of the
same em­
ployee that is
effective on/
beyond the
Go-live_Date
```
```
You execute
this integra­
tion
```
```
Such record
(s) (on/
beyond the
Go-live_Date)
will be sent to
Workforce
Software
```
```
Creating the
same records
for the em­
ployee in
Workforce
Software
```
```
Terminated
on the Go-
live_Date
```
```
You execute
this integra­
tion for the
first time
```
```
The respec­
tive termi­
nated em­
ployee record
will be sent to
Workforce
Software
```
```
A valid termi­
nated em­
ployee record
created in
Workforce
software
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **33**


```
Parameter Name Description
```
```
ignore_modified_date Set to 1 if you want to run a full load. The default is to run the
process in delta mode. After the run, reset to 0 to ensure that
only delta changes are processed.
```
```
Location Include the foundation object externalCode if you want to in­
clude only employees associated with that foundation object.
```
```
pay_group Include the foundation object externalCode if you want to in­
clude only employees associated with that foundation object.
```
```
person_id_external Comma-delimited list filter (no blank spaces before/after
comma) for specifying the person_id_externals to include in
the extract.
```
```
 Note
Generic field values are transferred to workforce only when a generic field name is provided.
```
**3.4.4 Value Mappings**

Value mappings are translation tables between the Employee Central picklist entries and the WorkForce Software
values.

The following fields have been mapped through a value-mapping project in SAP Cloud Platform Integration:

```
● Address Type
● Email Address Type
● Employment Status
● FullTime PartTime
● Leave Type
● Phone Types
● TimeZones
```
You can modify the entries in this project to suit your needs.

In the Developer’s Guide for Managing Integration Content, see Developing Value Mappings for general information
about value mappings, and Editing the Value Mapping Project for information about editing value mappings.

## 3.5 Extending the Standard Data Integration..............................................

You can customize the current integration solution by mapping additional fields from Employee central to
WorkForce Software.

To make changes, you must be familiar with the following topics:

**34** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

```
● SAP Cloud Platform Integration process development
SAP Cloud Platform Integration provides integration tools on the web to model integration flows, configure
attributes of the integration flows, and deploy them to the run-time. For more information, see the Developer’s
Guide for Managing Integration Content.
● Source and Target Datamodels
```
 Example

```
You want to enhance the current process to add additional field mappings in the target destination. Once
the source and target fields are identified, you can then accordingly map these fields from Employee
Central to WorkForce. To ensure the mapping works correctly or as per expectation, ensure that you
provide context to the field mapping.
Let's see a scenario for mapping the originalStartDate field from source to destination:
```
```
Source Field :
/ns0:Messages/ns0:Message2/CompoundEmployee/person/snapshot/
employment_information/originalStartDate
```
```
Destination Field : /ns0:Messages/ns0:Message1/ns3:E2G_importEmployees/ns3:payload/
ns2:data/ns2:person/ns2:employee_data/ns2:eff_dated_info/
ns2:data/ns2:generic_fields/ns2:generic_field3/ns2:fieldValue
```
```
FIELD to FIELD mapping
```
```
This is a direct mapping from the source field to the destination field as shown in the image below.
```
```
Context to entire Generic Fields set mapping
```
```
If you want ns2:genericFields to appear only once per ns2:eff_dated_info/ns2:data , then you
need to map ns2:genericFields with /ns0:Messages/ns0:Message2/CompoundEmployee/
person/snapshot/asOfDate. The asOfDate is a mandatory field for a snapshot and it would appear
only once for each snapshot.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Employee Data Replication** PUBLIC **35**


```
Context to specific Generic Field set mapping
In this scenario we map the specific generic field to the context source field. The destination field
mentioned above is mapped from the source field which is under employment_information in
Compound Employee. Therefore, we map the parent of the source to the parent of the destination field. In
this case, we obtain ONE employment_information and therefore, with this mapping we would then
obtain ONE generic_field3 at the destination output as shown in the image below.
```
```
 Caution
We recommend not enhancing the standard process because any enhancement makes the process
custom and decouples it from receiving any further enhancement updates to the standard content, and
also because support is provided only for standard integrations.
```
To deploy and run the Main Integration Process, ensure that the Custom Mapping Extension is already deployed.
Follow the deployment steps as stated:

1. Design and Configure both Custom Mapping Extension and Main Integration Process.
2. Deploy the Custom Mapping Extension.

**36** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Employee Data Replication
```

## 4 Integrating the WorkForce Software UI..............................................

You can enable single sign-on (SSO) from the Employee Central UI as part of the integration with WorkForce
Software.

## 4.1 Single Sign-On.................................................................

This section describes how you can configure a single sign-on (SSO) connection to SAP Time and Attendance
Management.

**Prerequisites**

A Provisioning user for a respective SuccessFactors tenant is needed to maintain the SSO configuration.

**4.1.1 Employee Central Certification for WorkForce Software**

Contact WorkForce Software for SSO information. WorkForce Software needs the following information from
SuccessFactors. This information may be packaged in a metadata file.

**Context**

If you send the metadata file to WorkForce Software, be sure to replace the entity ID in that file with the correct
issuer ID. WorkForce Software uses this information to setup SSO on their side.

```
● Issuer ID
Steps to Be Performed: In the below link, replace the values in square brackets with the SuccessFactors data
center and the company ID and provide it to WorkForce Software for SSO setup.
https://[SuccessFactors data center server name]/sf/idp-init/sso/company/[company ID]
● SAML Metadata and Signing Certificate
This is the signing X509Certificate for SSO communication and can be taken from the X509Certificate tag of
SAML metadata file.
Steps to Be Performed: In the below link, replace the values in square brackets with the SuccessFactors data
center server name and the company ID and execute the link in a browser.
https://[SuccessFactors data center server name]/idp/samlmetadata?company=[company ID] )
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Integrating the WorkForce Software UI** PUBLIC **37**


**Procedure**

1. Download and save the file on a local disk. (Executing the above link will download the file.)
2. Open the file in Notepad and remove all data except the information in the X509Certificate tag. (Remove the
    xml text in red.)
3. Using the Save As feature, save the file with a .cer extension and choose Unicode as the encoding.

```
This provides a .cer file that can be opened directly in Microsoft Windows Explorer.
```
4. To save the certificate in different formats, go to the Details tab in the certificate and choose Copy to File.
    This starts a wizard where you can select the file format before exporting.
5. Save as DER format by selecting _DER encoded binary X.509(.CER)_ in the _Certificate Export Wizard_.
6. Repeat the steps and save as _Base64 encoded X.509(.CER)_ format in the _Certificate Export Wizard_.

```
At the end of this step, you will have two certificate files.
```
```
User-Identifying Attributes: The user ID is in the name ID element of the SAML subject, and the company ID is
in the companyid attribute in the attribute statement, as shown in the following example. Note that the values
root and HRTech1 are example values and must be replaced with the correct data.
```
```
 Note
Send the above information (issuer ID, SAML metadata and signing certificate, and user-identifying
attributes) to WorkForce Software to setup SSO on their side.
```
**38** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Integrating the WorkForce Software UI
```

**4.1.2 Configuration of Employee Central Identity Provider for**

**WorkForce Software**

**Prerequisites**

Employee Central needs the following information from WorkForce Software:

```
● Assertion consumer service
● Audience (optional)
● Relay state value (optional)
```
**Context**

Set up the SSO connection as follows:

**Procedure**

1. In Provisioning, select the company and choose Authorized SP Assertion Consumer Service Settings.
2. Enter the assertion consumer service URL and audience string that you received from WorkForce Software.
3. Enter _wfs_ as the mapping key.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Integrating the WorkForce Software UI** PUBLIC **39**


**4.1.3 Configure 'Time and Attendance' Link for WorkForce**

**Software**

**Context**

Activate and configure the link to WorkForce Software as follows:

**Procedure**

1. In Provisioning, navigate to _Company Settings Employee Central_ and select the _Enable Employee Central_
    _V2 timesheets_ link checkbox.
2. Enter the target URL:

```
https://[SuccessFactors data center server name]/sf/idp-init/sso/wfs?
saml2=true&RelayState=[RelayStateValue]
```
```
 Note
The values in square brackets are placeholders and must be replaced by the correct data.
```
**40** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Integrating the WorkForce Software UI
```

## 5 Time Data Replication...........................................................

This chapter describes how to export time data from SAP Time and Attendance Management to Employee Central
Payroll.

It includes the following major steps:

1. Time data is extracted from SAP Time and Attendance Management to an XML file and saved in an SFTP
    location.
2. SAP Cloud Platform Integration accesses this SFTP location and transmits the time data to Employee Central
    Payroll through a web service call.
3. When the XML file arrives in Employee Central Payroll, it is automatically converted to an IDoc and can be seen
    in the IDoc queue.
4. Report RBDAPP01 posts records from the IDoc to the following SAP interface tables: PTEX2000 (Absences),
    PTEX2010 (Remuneration Wage Types).
5. Report RPTEXTPT moves the data from the interface tables to the respective infotype tables PA2001 (Absence
    Data) and PA2010 (Wage Types).

 Note

```
The specifications apply to the version for the country United States. If a customer implements a version for
another country, some adjustments may be necessary.
```
```
For more information on configuring time management in Employee Central Payroll, see Personnel Time
Management (PT) on SAP Help Portal.
```
## 5.1 Utility Report..................................................................

From May 2014 release onwards, the utility report to clear previous imports is delivered as standard in add-on
SFIECPEP 100. We recommend using this standard utility report instead of the custom solution delivered in SAP
Note 1915630.

Report RPDELPTINT Delete Time Data from Interface Tables for External Providers

Transaction PT_DEL_INT

**Prerequisites**

The following add-on is a prerequisite for using the standard utility report:

SFIECPEP 100 SuccessFactors Employee Central Payroll Third-Party Data Integration Tool

Following are some of the features of the utility program and how you can use it to clean up your system and make
it ready to import the re-export from the third-party time and labor management (TLM) system.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **41**


```
● A given batch of time data has a unique identifier. This unique identifier is stored in field CUSTOMER_FIELD of
the IDoc segment. For any errors while importing time data, note down this CUSTOMER_FIELD. You need to
specify this CUSTOMER_FIELD when executing the undo/delete utility report.
● If the batch inserted time data into employee master data, the utility will delete it. If the batch deleted time data
from employee master data, the utility will restore the deleted data.
● The utility report will also delete the segments from the staging area of PTEX2010, PTEX2000, and PTEXDIR.
● You can execute the utility report in test run mode. In this mode, the system simulates the actual execution and
displays the result. You can also select a set of employees for simulation.
● In a live run (the Test Run checkbox is not selected), you must process the delete report for the complete
batch. You do this by executing the report with a given batch number in the selection parameter. Part delete is
not allowed.
● The utility report has built-in safety mechanisms to ensure system consistency. However, there is also a force
delete mode to ignore such safety. This mode is useful if the system is in an inconsistent state and you want to
delete a batch forcefully.
```
## 5.2 Absence Data..................................................................

```
SAP Time and At­
tendance Manage­
ment Field Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired? EC Payroll Field
```
```
EXTSYSTEM* Partner system As configured in
"Receiver logical
system of third-
party time manage­
ment system", e.g.
"WORKFORCE"
```
```
yes No EXTDOCUMENTNO
```
```
EXTAPPLICATION* External application "EXT", as defined in
"Checking External
Application Key"
```
```
yes No EXTAPPLICATION*
```
```
EXTDOCUMENTNO Unique IDoc Docu­
ment number
```
```
Required yes No EXTDOCUMENTNO
```
```
REVERSED Reversal Indicator -
required for cancel­
lation
```
```
Optional yes No REVERSED
```
### EMPLOYEENUM­

### BER

```
Employee Payroll ID
as in EC Payroll
(PERNR)
```
```
Required yes No EMPLOYEENUM­
BER
```
**42** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
SAP Time and At­
tendance Manage­
ment Field Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired? EC Payroll Field
```
```
FROM_DATE Start date of ab­
sence (and also
end date, as only
one day absences
are allowed)
```
```
Required No No TO_DATE
```
```
FROM_DATE Start date of ab­
sence (and also
end date, as only
one day absences
are allowed)
```
```
Required Yes No FROM_DATE
```
```
ABS_ATT_TYPE Absence/ attend­
ance code
```
```
Required Yes No ABS_ATT_TYPE
```
```
START_TIME Start time of ab­
sence
```
```
Optional Yes No START_TIME
```
```
END_TIME End time of ab­
sence
```
```
Optional Yes No END_TIME
```
```
ABS_ATT_HOURS Absence/ attend­
ance hours
```
```
Optional Yes No ABS_ATT_HOURS
```
```
COSTCENTER Cost Center (for
overriding default
cost center assign­
ment)
```
```
Optional Yes No COSTCENTER
```
```
COMP_CODE Company Code Optional Yes No COMP_CODE
```
```
CUSTOMER_FIELD Unique Batch ID for
a given batch of ex­
ported
time data
```
```
Required Yes No CUSTOMER_FIELD
```
* These fields must be set using the process parameter in the middleware.

## 5.3 Remuneration Data..............................................................

The following fields are considered during the replication:

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **43**


```
SAP Time and At­
tendance Manage­
ment Field Description Required/Optional
```
```
Code Mapping Re­
quired?
```
```
Value Mapping Re­
quired? EC Payroll Field
```
```
EXTSYSTEM* Partner system As configured in
"Receiver logical
system of third-
party time manage­
ment system", e.g.
"WORKFORCE"
```
```
yes No EXTDOCUMENTNO
```
```
EXTAPPLICATION* External application "EXT", as defined in
"Checking External
Application Key"
```
```
yes No EXTAPPLICATION*
```
```
EXTDOCUMENTNO Unique IDoc Docu­
ment number
```
```
Required yes No EXTDOCUMENTNO
```
```
REVERSED Reversal Indicator -
required for cancel­
lation
```
```
Optional yes No REVERSED
```
### EMPLOYEENUM­

### BER

```
Employee Payroll ID
as in EC Payroll
(PERNR)
```
```
Required yes No EMPLOYEENUM­
BER
```
```
VALIDITYDATE Date to which time
data belongs
```
```
Required No No VALIDITYDATE
```
```
WAGETYPE Wage type code as
in EC Payroll
```
```
Required Yes No WAGETYPE
```
```
NO_OF_HOURS Number of hours Optional Yes No NO_OF_HOURS
```
```
NUMBER Rate Optional Yes No NUMBER
```
```
AMOUNT Amount Optional Yes No AMOUNT
```
```
CURRENCY Absence/ attend­
ance hours
```
```
Optional Yes No CURRENCY
```
```
COSTCENTER Cost Center (for
overriding default
cost center assign­
ment)
```
```
Optional Yes No COSTCENTER
```
```
COMP_CODE Company Code Optional Yes No COMP_CODE
```
```
CUSTOMER_FIELD Unique Batch ID for
a given batch of ex­
ported time data
```
```
Required Yes No CUSTOMER_FIELD
```
* These fields must be set using the process parameter in the middleware.

**44** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

## 5.4 Getting Access to the Solutions.....................................................

SAP Cloud Platform Integration Spaces is a Web-based application that helps you to access the integration content
available for a particular tenant on an on-demand integration infrastructure.

In SAP Cloud Platform Integration Spaces, you can access integration packages with artifacts such as value
mappings, integration flows, and files. For more information, see Viewing Integration Flow Configurations in the
_Developer's Guide for Managing Integration Content_.

You can edit and configure a package as follows:

1. On the Discover tab, click the integration package to be configured.
2. Choose _Copy_.
    On the Design tab, you should now find the copied package.

To configure and edit the package, follow Editing Integration Flow Configurations in the SAP HANA Cloud
documentation.

**5.4.1 Common Configuration Steps**

**5.4.1.1 SAP Credential Deployment**

To deploy the following artifacts, see Deploying and Editing a User Credentials Artifact in the Operations Guide for
SAP Cloud Platform Integration.

```
Artifact Description
```
```
SuccessFactors EC Credentials These credentials are used to connect to the SuccessFactors
Employee Central system
```
```
SuccessFactors EC Payroll Credentials These credentials are used to connect to the SuccessFactors
Employee Central Payroll system
```
```
SAP SFTP Server Credentials These credentials are used to connect to the SuccessFactors
Employee Central Payroll system
```
```
WorkForce SFTP Server Credentials These credentials are used to connect to the WorkForce SFTP
server
```
**5.4.1.2 Value Mapping Maintenance**

A value mapping project is delivered along with the iFlows in this integration. It must be deployed in the customer
landscape so that the iFlows can refer to the value mappings.

For information about using and editing value mappings, see the _Developer’s Guide for Managing Integration
Content_.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **45**


**5.4.2 Setting Up the Standard Data Integration**

In the Discover section, click the _SuccessFactors Employee Central with Third Party Time Vendor-WorkForce
Software(WFS)_ integration process and configure the _Packaged Integration - WFS to SF EC Payroll_ integration flow.

**5.4.2.1 Sender Settings**

```
Field Description
```
```
Source
```
```
Directory Directory path on the SFTP server where the input file is
stored, for example, /input
```
```
File Name Name of the input file along with the extension, for example,
payroll-export.txt
```
```
Address SFTP server host URL, for example, test.sftp.com
```
**46** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
Field Description
```
```
Authentication Required to authorize a file while accessing it. For Key based
authorization select Public key and for certificate based select
Username/Password
```
```
User Name SFTP user name for the above connection
```
```
Processing
```
```
Post-Processing Delete File - To delete a input file from the mentioned path
Keep File and Mark as Processed in Idempotent Repository - To
maintain the mentioned input file and not process it the next
time
Keep File and Process Again - To maintain the input file and
process it every time
Move File -To move the input file to the specified archive direc­
tory path
```
```
Schedule
```
```
Run Once
Schedule on Day
Schedule to Recur
```
```
 Tip
When testing the integration, we recommend choosing
Run Once rather than scheduling it to run.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **47**


**5.4.2.2 Receiver Settings**

**5.4.2.2.1 EC_Payroll**

This receiver helps you to connect to the SuccessFactors Employee Central Payroll system.

```
Field Description
```
```
Address Employee Central Payroll connection URL
```
```
Credential Name Name of the artifact that was deployed in Common Configura-
tion Steps
```
**5.4.2.2.2 System_Values_Missing_Mail**

This receiver helps you to send the resulting file of the process to a directory at the SFTP location.

**48** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
Field Description
```
```
Address This is the SMTP server address
```
```
From This is the SMTP server address
```
```
To This is the address of the recipient of the mail generated by the
process
```
**5.4.2.2.3 Success_Notification_Mail**

This receiver helps you to log the failing employees from the payload and send the relevant information to a
directory at the SFTP location.

```
Field Description
```
```
Address This is the SMTP server address
```
```
From This is the From address of the SMTP server
```
```
To This is the address of the recipient of the mail generated by the
process
```
```
Subject This is the subject of the Success_Notification_Mail
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **49**


```
Field Description
```
```
Mail Body This is the description of the Success_Notification_Mail
```
**5.4.2.2.4 Exception_Mail**

This receiver helps you to capture the records where mandatory fields are missing from the payload, and to send
the relevant information to a directory at the SFTP location.

```
Field Description
```
```
Credential Name Name of artifact that was deployed in SAP Credential Deploy­
ment [page 45 ].
```
```
Address This is the Mail Server address followed by the port number.
```
```
 Example
smtp.postmarkapp.com:587 where 587 is the port number
for SMTP. This port number will be different for all other
Mail Servers.
```
```
From This is the From address of the SMTP server
```
**50** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
Field Description
```
```
To This is the address of the recipient of the mail generated by the
process
```
```
Subject This is the subject of the Exception_Mail
```
```
Mail Body This is the description of the Exception_Mail
```
**5.4.2.2.5 Parameters**

```
Parameter Name Description
```
```
Partner Number of Sender Logical system of the sender system configured in transaction
BD64
```
```
Client Number of Receiver In transaction SM30, display table T000. Enter the client num­
ber that you want to use, for example, 502
```
```
Partner Type of Receiver Partner type of the receiver system configured in the SAP ERP
system
```
```
Partner Type of Sender Partner type of the sender system configured in the SAP ERP
system
```
```
Port Number of Receiver Port number of the receiver logical system
```
```
Is_Mail_Req Boolean type 1 allows you to send the mail to the configured
email and Boolean value 0 does not allow
```
```
Port Number of Sender Port number of the sender logical system
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **51**


```
Parameter Name Description
```
```
Partner Number of Receiver Logical system of the receiver system configured in transaction
BD64
```
## 5.5 More About Data Replication.......................................................

**General**

```
● SAP Time and Attendance Management will be the system of record for quotas/banks to facilitate accrual and
usage calculations
● The Inbound data from SAP Time and Attendance Management to Employee Central Payroll can contain cost
center related information. Providing cost center in the inbound allows you to make use of cost override feature
on Employee Central Payroll. However, there is no standard cost center information inbound available for SAP
Time and Attendance Management. It is assumed that customer takes care of this himself, if he wants to make
use of Cost override features.
```
**Absence Data**

```
● Absence quota payouts will be determined by the administrator in the time system (including accrual payouts
at termination).
● If you use integration with Infotype 2001, be aware that regardless of the absence hours that are sent from the
WorkForce Software, those hours are calculated again in SAP ERP Time Management based on the absence
type configuration and the employee's work schedule in Infotype 0007. This will not be the case, when you use
integration with Infotype 2010 for absence hours. You need to decide which infotype to use depending on your
business needs and requirements.
● If correct absence hours are relevant for Employee Central Payroll and cannot be handled using the
remuneration infotype, then information on planned working time and public holidays must be held in sync with
the planned working time in WorkForce Software. You must configure the absence type calculation according to
the customer's business requirements. Absences records must not be longer than a day. If they are longer,
they need to split up into multiple absences, each only one a day long. For example, if there is a 4-days
absence, it needs to be split into four records where each absence lasts only one day.
● Absence codes sent to Employee Central Payroll may trigger business logic checks. We recommend that you
select absence codes that have minimum or no business checks in Employee Central Payroll (for example,
general absence with no collision checks and input checks). Absence codes which trigger business checks may
require extensive configuration in Employee Central Payroll.
```
**52** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

**Remuneration Data**

```
● Wage types are always expected to contain the number of hours and rate of pay. You can skip the rate if you
want SAP to calculate the rate.
● FLSA rates are calculated, by default, at the SAP Time and Attendance Management. Customers need to use
the custom fields for bonus data in SuccessFactors and this data need to be transmitted to SAP Time and
Attendance Management so that it calculates FLSA rates accurately. If customers want to use the FLSA rate
calculated by Employee Central Payroll, they need to switch off the FLSA rate calculation in SAP Time and
Attendance Management and instead have to configure the FLSA rate calculation in Employee Central Payroll.
For more information, see the UTR0 subschema documentation in the Employee Central Payroll Handbook.
● Wages are added to either the bonus pay component or the basic pay component based on the configuration in
Employee Central Payroll. This influences subsequent payroll calculations.
● For premium pay, there are two scenarios possible:
○ WorkForce Software sends wage types with the final rate of payment.
In this case, you must change the configuration of wage types in Employee Central Payroll such that there
is no further premium applied on the rate supplied by WorkForce Software.
○ WorkForce Software is configured to send the regular rate.
In this case, the Employee Central Payroll configuration can contain premium rates.
● When an amendment is made, it results in two records sent from WorkForce Software to Employee Central
Payroll. These are:
○ A new record which replaces the old record.
○ The record that needs to be cancelled. The cancellation record must contain all details that were previously
sent (for example, amount and rate).
● We recommend supplying cost center information only for override. If supplied in every case, it is assumed that
the third-party provider takes care of sending amendments to Employee Central Payroll even if only the cost
center changed for employees (for example, the cost center of an employee changed for the last period, but
the time data did not change).
● For cost center overrides, only information for cost center and company code fields is exposed from Employee
Central Payroll.
● SAP Time and Attendance Management needs to know the cost center/company codes that are valid in
Employee Central Payroll. This needs to be achieved by a custom integration. There is no standard integration
available for this purpose.
```
**Functions Supported by the Payroll Export**

```
● Cancellation / deletion of absences previously exported to SAP Payroll
● Cancellation / deletion of wage types previously exported to SAP Payroll
● Import of wage types into Employee Central Payroll = Infotype 2010 with valid date and amount of hours
● Import of Absences into Employee Central Payroll = Infotype 2001 with valid date and hours
● In case of terminated employees, the time data after the termination date is not processed. These cases must
be handled directly in Employee Central Payroll.
● Absence quota payments will have to be determined by the administrator in the time system (including accrual
payouts at termination).
● In case of errors during the import of a particular batch of time data, the administrator needs to delete the
complete batch. To achieve this, the batch number must be entered as a selection parameter when the Delete
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **53**


```
report is executed. Partial deletion is not allowed. For details about the Delete report, see the Troubleshooting
section.
● Time substitutions are out of scope.
```
**5.6 Configuring the Integration between SAP Time and**

**Attendance Management and Employee Central Payroll**

To enable the integration between SAP Time and Attendance Management and Employee Central Payroll, you have
to perform the following steps:

```
● Configure Absence Types
● Configure Remuneration Wage Types
● Set up the ALE Scenario for IDoc
```
**5.6.1 Configuring Absence Types**

**Context**

```
 Note
If you don't use Time Management in SAP ERP, ensure that time-specific checks such as Input Checks or Quota
Deduction Assignments are deactivated.
```
For more information, see _Personnel Time Management (PT)_ on SAP Help Portal.

**Procedure**

1. In Customizing for _Time Management_ , choose _Time Data Recording and Administration AbsencesAbsence_
    _CatalogDefine Absence Types_.
2. Create only absence types that are relevant for payroll. For more information, see the documentation for the
    Customizing activity.
3. In SM31, enter T554S and click _Maintain_. Double-click each payroll-relevant entry in the table and make the
    following settings for each:
       ○ In the _Input Checks_ section, ensure the fields are either blank or unchecked. For _minimum duration_ , enter
          001 and for _maximum duration_ , enter 999.
       ○ In the _Counting and Quota Deduction_ section, uncheck everything except _Grpg att./abs. for counting (01)_.
          Enter a counting rule.

**54** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
○ In the Payment Data section, enter an Absence Valuation Rule and Abs./Att cat. for Payroll as required by
payroll calculation depending on the business demands of the absence valuation in payroll.
```
```
 Example
Example SAP absence types are listed in the following table. As mentioned above, you can select absence types
that have no checks. If you plan to select the other absence types, make sure that you deactivate time-specific
checks during configuration.
```
```
Absence Code Description
```
```
Screens Used
(and Subsequent
Business Logic
Applied) Collision Checks Input Checks Unit of Measure
```
```
0100 Paid Leave Quota Deduction Yes None Calendar Days
```
```
0140 Paid Absence General absence None End Date is re­
quired. Error if
start and end date
is an off day; or if
the entire period is
an off period.
```
```
Calendar Days
```
```
0150 Unpaid Absence General absence None None Calendar Days
```
```
0200 Illness Work Incapacity None Error - if absence
is on a holiday
```
```
Calendar Days
```
```
0201 Short Term Disa­
bility
```
```
Work Incapacity None None Calendar Days
```
```
0202 Long Term Disabil­
ity
```
```
General absence None None Calendar Days
```
```
0215 Comp Time for
Overtime
```
```
Quota Deduction Yes End Date is re­
quired
```
```
Calendar Days
```
```
0220 Floating Holiday Quota Deduction Yes End Date is re­
quired
```
```
Calendar Days
```
```
0230 Personal time General absence None End Date is re­
quired. Error if
start and end date
is an off day; or if
the entire period is
an off period.
```
```
Calendar Days
```
```
0250 Occ. Inj/Worker's
Comp
```
```
General absence None None Calendar Days
```
```
0500 Maternity protec­
tion
```
```
Maternity Protec­
tion
```
```
Yes None Calendar Days
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **55**


```
Absence Code Description
```
```
Screens Used
(and Subsequent
Business Logic
Applied) Collision Checks Input Checks Unit of Measure
```
```
0510 Family care leave Maternity Protec­
tion
```
```
Yes None Calendar Days
```
```
0520 Jury Duty-Quota General absence None None Calendar Days
```
```
0530 Bereavement
Leave
```
```
General absence None None Calendar Days
```
```
0650 Military/non-
mil.service
```
```
Military Service Yes None Calendar Days
```
```
0700 Strike/Lockout General absence Yes None Calendar Days
```
**5.6.2 Configuring Remuneration Wage Types**

**Context**

**Procedure**

1. In Customizing for _Personnel Management_ , choose _Personnel Administration Payroll Data Employee_
    _Remuneration Information Wage Types Check Wage Type Characteristics_.
2. If a wage type already exists that fulfills the customer's requirements, use it.

```
If not, do the following:
```
1. Select _Personnel Management_ , choose _Personnel Administration Payroll Data Employee_
    _Remuneration Information Wage Types Check Wage Type Catalog_.
2. Select copy and enter a country.
3. Select wage type and click _Copy_.
3. Adapt the wage type, if necessary, so that it exactly matches to the wage types that exist in WorkForce
Software. In the field Input combination, enter _X_ for both _Amount_ and _Number/unit_. In Number/unit section,
choose a relevant entry for _Time unit/mass_ , for example, _Hours_.

```
For other sections, see the field documentation for more information.
```
**56** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

4. In SM31, enter V_512W_O and click _Maintain_. Choose the country grouping. Double-click the wage type and
    maintain the table according to the payroll requirements of the customer.

 Example

```
Example SAP remuneration wage types are listed in the following table.
```
```
M800 Regular working time - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M801 Lump sum period hours - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M802 On Call/Standby - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M803 Training - internal - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M804 Training - external - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M805 Overtime paid 1.0 - Either amount or number/unit
```
- Unit of measure: Hours
- For basic overtime hours
- Add to total

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **57**


```
M806 Overtime paid 1.5 - Either amount or number/unit
```
- Unit of measure: Hours
- For for basic overtime hours
- multiplied by 150%
- Add to total

```
M807 Overtime paid 2.0 - Either amount or number/unit
```
- Unit of measure: Hours
- For basic overtime hours
- multiplied by 200%
- Add to total

```
M810 Sunday premium - Either amount or number/unit
```
- Unit of measure: Hours
- multiplied by 25%
- Bonus wage type
- Add to total

```
M811 Holiday premium - Either amount or number/unit
```
- Unit of measure: Hours
- multiplied by 15%
- Bonus wage type
- Add to total

```
M812 Evening Shift premium - Either amount or number/unit
```
- Unit of measure: Hours
- multiplied by 5%
- Bonus wage type
- Add to total

```
M813 Night Shift premium - Either amount or number/unit
```
- Unit of measure: Hours
- multiplied by 10%
- Bonus wage type
- Add to total

**58** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
M814 Weekend Shift premium - Either amount or number/unit
```
- Unit of measure: Hours
- multiplied by 20%
- Bonus wage type
- Add to total

```
M815 Call In pay - Either amount or number/unit
```
- Unit of measure: Hours
- Bonus wage type
- Add to total

```
M850 Holiday Pay - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M851 Vacation Pay - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M852 Sick pay - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M853 Comp time taken - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M854 Jury duty - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **59**


```
M855 Bereavement leave - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M858 Family Medical Leave - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M859 Maternity leave - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M860 Short term disability - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
M864 Other Paid Absence - Either amount or number/unit
```
- Unit of measure: Hours
- For basic hours
- Add to total

```
ML01 Piecework time - Either amount or number/unit
```
- Unit of measure: Pieces
- For basic hours
- Add to total

```
TD00 Direct tip - Amount essential, no number/unit
```
- For bonus
- Add to total

```
TGS0 Gross sales - Amount essential, no number/unit
```
- For bonus
- Add to total

**60** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
TI00 Indirect tip - Amount essential, no number/unit
```
- For bonus
- Add to total

```
TO01 Overtime hours - tips - No amount, number/unit essential
```
- For bonus
- Add to total

```
TO02 Overtime hours - tips - No amount, number/unit essential
```
- For bonus
- Add to total

```
TR01 Regular hours - tips - No amount, number/unit essential
```
- For bonus
- Add to total

```
TR02 Regular hours - tips - No amount, number/unit essential
```
- For bonus
- Add to total

**5.6.3 Configuring Technical Communication User**

To customize integration, a system user (type B user) with required permissions must be created allowing inbound
communication in the relevant Employee Central Payroll client. This allows the middleware to successfully
communicate with the payroll system. For your convenience, we have created a template role you can assign to this
user: SAP_HR_PA_EC_EE_REPL. It is strongly recommend that you create the user using the template role.

Also you have to make sure to mark this user as 'customer' user by assigning the user group “customer” to the
user via SU01 – else the user will be deleted automatically.

```
 Caution
If the customer has already been using this template role since b1302 (February 2013 release), the customer
must copy this template again and assign it to the user to ensure that Date Specifications, which are new to
b1308 (August 2013 release), are replicated as well.
```
```
For more information on creating users see Creating a Technical User in the SAP Library.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **61**


**5.6.4 Setting Up ALE Scenario for IDoc**

**5.6.4.1 Defining a Logical System**

You must create a logical system that represents the third-party time management system. This will send the
absence and remuneration data to the SAP system.

**Context**

```
 Note
Logical systems are defined as cross-client systems. You must maintain the logical system in a client in which
cross-client customizations are allowed.
```
```
For more information, see Customizing for SAP NetWeaver Application Server  IDoc Interface /
Application Link Enabling (ALE) Basic Settings Define Logical System Logical Systems.
```
**Procedure**

1. In transaction BD54, choose _Edit New Entries_.
2. Create a logical system that identifies the third-party time management system, as shown in the following
    table:

```
Field Entry
```
```
Logical System Enter the logical system name of the third-party time man­
agement system, for example, WORKFORCE.
```
```
Description Enter a descriptive name.
```
**5.6.4.2 Identifying the SAP System**

**Procedure**

1. In transaction SM30, display table T000.
2. Double-click the client you want to display (for example, 850).
3. Note the logical system specified here (example: XXXCLNT850) since this will be the system that receives the
    IDoc.

**62** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

**5.6.4.3 Maintain Distribution Model**

You must define a distribution model for each system that receives data from SAP ERP. Distribution models
describe the Application Link Enabling (ALE) message flows between logical systems.

**Context**

The distribution model consists of separate model views in which all the associated, cross-system message flows in
your organization can be defined. These views must be distributed to the receiving systems. In the individual
message flows, you can define filters to determine which data is transferred to which receiving system. The
distribution model controls this distribution.

For more information, see Customizing for _SAP NetWeaver Application Server IDoc Interface / Application_

_Link Enabling (ALE) Modelling and Implementing Business Processes Maintain Distribution Model and_

_Distribute Views_.

**Procedure**

1. In transaction BD64, switch to edit mode.
2. Choose _Create Model View_.
3. Create a model view as shown in the following table:

```
Field Value
```
```
Short text For example, Employee Central Payroll – Third-Party Time
Management System
```
```
Technical Name For example, CP_WF_INT
Maximum 10 characters
```
```
Start Date <current date>
```
```
End Data 31.12.9999
```
4. From the Distribution Model list, select the model you just created and choose _Add Message Type_.

```
Fields and Values for hrsm_d
```
```
Field Value Example
```
```
Sender Logical system of SAP ERP
<system ID>CLNT<client number>
```
### XXXCLNT850

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **63**


```
Field Value Example
```
```
Receiver Receiver logical system of third-party
time management system.
Enter system from the Logical System
step.
```
### WORKFORCE

```
Message Type hrsm_d
```
5. Select _Add BAPI_.
6. For the following BAPIs, enter sender / receiver port as above:

```
○ Choose PTMgrExtAttAbs and then choose Method: InsertWithCostAssignment
○ Choose PTMgrExtRemunSpec and then choose Method: InsertWithCostAssignment
```
7. Save your entries.

**5.6.4.4 Checking and Registering IDoc Service**

**Context**

**Procedure**

1. To check if the service /sap/bc/srt/idoc (Inbound SOAP for IDoc) is active, proceed as follows:
    1. In transaction SICF, enter /sap/bc/srt/idoc in the _Service Path_ field. [Right-click IDoc, click test service,
       Web browser opens, the URL shown is the URL needed for the xml end point.]

```
 Note
This step is required just to capture the URL endpoint. In case an error message is displayed in your
browser, you can ignore the error and just copy the URL for your configuration later.
```
2. Choose _Execute_.
If the service is displayed in gray, it is inactive. To activate the service, right-click the service name and, from
the context menu, choose _Activate Service_.
2. To register the service, proceed as follows::
1. In transaction SRTIDOC, select the _Register Service_ checkbox.
2. In the _Service Attributes_ section, enter the parameters:

**64** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

```
Parameter Value
```
```
URI SOAP Application urn:sap-com:soap:runtime:application:idoc
```
```
Name of Web Service Definition GENERIC
```
```
Call Address (ICF Path) /sap/bc/srt/idoc
```
```
Number of Virtual Host Leave empty
```
3. Choose _Execute_.

**5.6.4.5 Maintain Partner Profile - Logical System (LS)**

This section describes how to configure partner profiles so that data is sent immediately.

**Context**

For more information, see _Customizing for SAP NetWeaver Application Server IDoc Interface / Application_

_Link Enabling (ALE) Modelling and Implementing Business Processes Partner Profiles_.

**Procedure**

1. In transaction WE20, select _Partner Type LS_ and select _Create_.
2. Create a partner profile, as shown in the following table:

```
Field Value Example
```
```
Partner No. Enter the logical system name
```
```
Partner Type LS (Logical System)
```
```
Type Organizational Unit or User (O or US)
```
```
Agent Enter the job (person or group of per­
sons) to be notified in case of error
```
### 50010120

```
Language EN
```
3. Save your entries.
4. Click the _Add Row_ icon to define the inbound parameters for the message type HRSM_D.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **65**


```
Inbound Options tab for Message Type HRSM_D
```
```
Field Value
```
```
Message Type HRSM_D
```
```
Process Code HRSM_D
```
```
Processing By Function Module Trigger Immediately
```
5. Verify that the _Cancel Processing After Syntax_ checkbox is selected.

**5.6.4.6 Checking External Application Key**

**Context**

The following procedure helps you in checking the external application key.

**Procedure**

1. In SM31, enter the table _tptextapp_ and click _Maintain_.
2. Verify that there is a corresponding entry in the table for the external application field in the XML. If it is
    missing, add entry for external application for key EXT.

**5.6.4.7 Defining Background Jobs**

You must plan several reports to run so the data can be moved from the IDoc to the correct infotype in the system.

**Context**

**Procedure**

1. In transaction SM36, click _Job Wizard_.

**66** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Time Data Replication
```

2. Enter job name. Click _Next_.
3. Choose ABAP Program Step. Click _Next_.
4. Enter report RBDAPP01 as ABAP program name. Click _Next_.
5. Click Start immediately. Click _Next_.
6. Select periodical jobs. Click _Next_.
7. Choose the interval period for how often the report should run, for example, every five minutes.
8. Repeat the job wizard for report RPTEXTPT. The report should not use the option "Transfer/Delete". This is to
    make sure that the staging area data is retained. This data is required for the Error correction report.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Time Data Replication** PUBLIC **67**


## 6 Troubleshooting...............................................................

In exceptional cases, problems can occur with the data that is imported to Employee Central Payroll, for example, if
an incorrect wage type code is attached to time entries.

When errors occur, the export report fails and the administrator is notified. The batch needs to be re-exported from
SAP Time and Attendance Management and replicated in Employee Central Payroll. The administrator needs to
access the SAP Time and Attendance Management and provide the unique batch ID for which the re-export of the
time data is required. This unique batch ID is available in the IDoc field CUSTOMER_FIELD.

Before the re-export is started, the previously imported data must be removed from the system. A cleanup is
needed for both employee master data and the time data staging tables. From the May 2014 release onwards, we
recommend using the standard utility report delivered in add-on SFIECPEP 100 to clean up the previous imports
instead of the custom solution delivered through SAP Note _1915630_. For lower releases, SAP Note _1915630_
describes a utility report that cleans up this data. Please implement this SAP note in the customer's Employee
Central Payroll system. Follow the instructions in the SAP note carefully to execute the report correctly.

**68** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Troubleshooting
```

## 7 Error Handling................................................................

The prepackaged integration uses EC Execution Manager (XM) monitoring tool to show the errors that may occur
during replication. We also recommend using the CPI Monitor for the monitoring of integration.

During the integration if there are any employee records that fail to be processed then this integration captures the
specific person id external field with the appropriate error message in Execution Manager.

## 7.1 Setting Permissions for the Execution Manager Dashboard.................................

Execution Manager (XM) is an admin opt-in tool that does not require provisioning to be enabled. To set up role
based permissions for your permission group to have access, follow these steps:

**Procedure**

1. Go to _Admin Center Manage Permission Roles_ that directs you to the _Permission Role List_ page.
2. Select the _Permission Role_ group you want to edit that directs you to the _Permission Role Detail_ page.
3. Select _Permission_ button that opens up the _Permission Settings_ box.
4. Go to _Administrator Permissions Admin Center Permissions_ and select these two options:
    ○ _Read Execution Manager Events_
    ○ _Read Execution Manager Event Payload_
5. Select _Done_ to save, which direct you back to the _Permission Role Details_ page.
6. Select _Save Changes_ to finish.

## 7.2 Using the Execution Manager Dashboard..............................................

The _Execution Manager Dashboard_ can be accessed either from _oneAdmin_ or from _NextGen_ UI.

**How to Access Execution Manager Dashboard**

For _oneAdmin_ users, you can access it by entering in _Execution Manager Dashboard_ in the _Tool Search_ box.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Error Handling** PUBLIC **69**


For _NextGen_ users, you can access it by clicking on the _See More_ link available on the tiles that correspond to
_Scheduled Jobs_ and _Integration Center_. The _NextGen_ Admin page also displays _Scheduled Jobs_ and _Integration
Center_ tiles with data of the last 7 days.

```
Integration Center and Scheduled Jobs featured
```
**Execution Manager Dashboard**

The _Execution Manager Dashboard_ supports three tabs:

```
● Scheduled Jobs
● Integration Center
● Middleware Integrations
```
Each section has its own set of graphs and a table that displays the data on the graph. The graph shows jobs that
fail or been successful. For all integrations using SAP Hana Cloud Integration tool is captured by the _Middleware
Integrations_ tab.

**Using Filters**

This dashboard has two filters to narrow down your search results:

1. Timeframe: _Last 24 hours_ , _Last 7 days_ , _Last 30 days_ , and _Custom Date Range_.
2. _All_ , _Error_.

**Viewing Error Details**

Below the _Middleware Integrations_ graph, there is a table that displays all processes that match your search criteria.
You can see the detailed view of your event by selecting the empty space before the _Process Identifier_.

**70** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Error Handling
```

We have the following Process States:

```
● Completed_Successfully
● Completed_With_Errors
● Completed_With_Warnings
● FAILED
```
See screenshot below for more information.

When you select the process you want to view, it directs you to the _Event Details_ page.

## 7.3 Event Details Table..............................................................

The Event Details is where you can view specifics on your integration event. If your event has any payload, you can
download as a text file.

Event Details

```
Column Header Name Description
```
```
Event Name The event name is listed here with the date and time stamp
when it ran.
```
```
Event Description Description of the event. You can hover over the linked text with
your mouse to read the entire description. If you select the
linked text, a box opens up with more information about your
event.
```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Error Handling** PUBLIC **71**


```
Column Header Name Description
```
```
Event Type If your process does not have errors, this label appears:
● INFO
If your process has errors, these labels appear:
● ERROR: event was not successful.
● WARNING: this is a warning.
● INFO
You can select the Event Description for more information
about that label.
```
```
Created Date Date that this event was logged.
```
**Example listing error,warning and info on the Event Details Table**

```
Event Name Event Description Event Type Created Date
Integration Execution Status
Messages
```
```
Some employee records are
invalid
```
```
Error Thu Feb 7 2019
```
```
Integration Execution Status
Messages
```
```
Some employees contain
warnings
```
```
Warning Thu Feb 7 2019
```
```
Send Employee records valid
as of Go-live Date ...
```
```
Details of employee record(s)
not produced effective as of
and beyond the Go-live Date
```
```
Info Thu Feb 7 2019
```
```
When the Event Description is ... Then it means that ...
Some employee records are invalid Some employee records exist without first name/last name/
person id external.
Some employees contain warnings Some employee records contain corrupt data.
Details of employee record(s) not produced effective as of and
beyond the Go-live Date
```
```
The employee record does not have any effective dated
snapshots on or after the Go-live Date and hence this
employee is ignored and not sent to Workforce Software.
```
When you click an Event Description you will get an option to download the payload information. The payload gives
you more insight in understanding the error/warning/info in detail.

**72** PUBLIC

```
Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
Error Handling
```

## Important Disclaimers and Legal Information

**Hyperlinks**

Some links are classified by an icon and/or a mouseover text. These links provide additional information.
About the icons:

```
● Links with the icon : You are entering a Web site that is not hosted by SAP. By using such links, you agree (unless expressly stated otherwise in your agreements
with SAP) to this:
● The content of the linked-to site is not SAP documentation. You may not infer any product claims against SAP based on this information.
● SAP does not agree or disagree with the content on the linked-to site, nor does SAP warrant the availability and correctness. SAP shall not be liable for any
damages caused by the use of such content unless damages have been caused by SAP's gross negligence or willful misconduct.
● Links with the icon : You are leaving the documentation for that particular SAP product or service and are entering a SAP-hosted Web site. By using such links, you
agree that (unless expressly stated otherwise in your agreements with SAP) you may not infer any product claims against SAP based on this information.
```
**Beta and Other Experimental Features**

Experimental features are not part of the officially delivered scope that SAP guarantees for future releases. This means that experimental features may be changed by SAP at
any time for any reason without notice. Experimental features are not for productive use. You may not demonstrate, test, examine, evaluate or otherwise use the
experimental features in a live operating environment or with data that has not been sufficiently backed up.
The purpose of experimental features is to get feedback early on, allowing customers and partners to influence the future product accordingly. By providing your feedback
(e.g. in the SAP Community), you accept that intellectual property rights of the contributions or derivative works shall remain the exclusive property of SAP.

**Example Code**

Any software coding and/or code snippets are examples. They are not for productive use. The example code is only intended to better explain and visualize the syntax and
phrasing rules. SAP does not warrant the correctness and completeness of the example code. SAP shall not be liable for errors or damages caused by the use of example
code unless damages have been caused by SAP's gross negligence or willful misconduct.

**Gender-Related Language**

We try not to use gender-specific word forms and formulations. As appropriate for context and readability, SAP may use masculine word forms to refer to all genders.

Integrating SAP SuccessFactors Employee Central with WorkForce Software (SAP Cloud
Platform Integration)
**Important Disclaimers and Legal Information** PUBLIC **73**


[http://www.sap.com/contactsap](http://www.sap.com/contactsap)

© 2019 SAP SE or an SAP affiliate company. All rights reserved.
No part of this publication may be reproduced or transmitted in any form
or for any purpose without the express permission of SAP SE or an SAP
affiliate company. The information contained herein may be changed
without prior notice.
Some software products marketed by SAP SE and its distributors
contain proprietary software components of other software vendors.
National product specifications may vary.
These materials are provided by SAP SE or an SAP affiliate company for
informational purposes only, without representation or warranty of any
kind, and SAP or its affiliated companies shall not be liable for errors or
omissions with respect to the materials. The only warranties for SAP or
SAP affiliate company products and services are those that are set forth
in the express warranty statements accompanying such products and
services, if any. Nothing herein should be construed as constituting an
additional warranty.
SAP and other SAP products and services mentioned herein as well as
their respective logos are trademarks or registered trademarks of SAP
SE (or an SAP affiliate company) in Germany and other countries. All
other product and service names mentioned are the trademarks of their
respective companies.
Please see https://www.sap.com/about/legal/trademark.html for
additional trademark information and notices.

**THE BEST RUN**


