---
layout: module
title: Module 3&#58; Adding Fields to the Salesforce Request Object
---

In the first exercise you created a cloud app for managing Salesforce requests. Behind the scenes, the platform created a database for the app. A database organizes and manages data so that users can work with it efficiently. Traditional relational databases use tables to manage discrete, possibly related, collections of information, organized further into datatype-specific columns (attributes) and rows (records). In Salesforce, you refer to these as objects. 

Your DE org comes with many standard objects (for example, Accounts, Products, Tasks) that support pre-built and custom apps. Any new objects you create are called custom objects. The Salesforce Request object is one such custom object. In this exercise we are going to add a variety of different fields to capture the data we need to execute the Salesforce Request and get familiar with the field types that Salesforce has to offer.

The following image is a sneak peek of the data model you will be building, which allows you to view your objects, fields, and relationships.

![](images/03-schema-builder-data-model.png)

Our Salesforce Request object will have fields that the user can populate so that the Salesforce Admin has the information they need create a new User or feature in Salesforce. You can add custom fields to list or track just about anything. In this section we will add a variety of fields to our new Salesforce Request Object.

## Add a Text Field to the Object
This field will be used to capture the User _First_ & _Last Name_ so we know who to _activate_ or _deactivate_.

1. Click **Setup** | **Create** | **Objects**.

2. Click `Salesforce Request`, scroll down to _Custom Fields and Relationships_, and click **New**.

3. The wizard helps you quickly specify everything about a new field, including its name, labels to use for app pages, help information, and visibility and security settings. Create the First & Last Name field as follows:

4. For `Data Type`, select `Text`, and click **Next**.

5. Fill in the custom field details:
  - Field Label: `User First & Last Name`
  - Length: 60

6. Leave the defaults for the remaining fields, and click **Next**.

7. Click **Next** again to accept the default field visibility and security settings.

8. Click **Save & New** to save the User First & Last Name field and return to the first step of the wizard.


## Add an Email Field to the Object
This field will be used to capture the new user’s email address so we can create the license.

1. For `Data Type`, select `Email` and click **Next**.

2. Fill in the field details:

3. Field Label: `User Email`

4. Leave the defaults for the remaining fields, and click **Next**.

5. Click **Next** again to accept the default field visibility and security settings.

6. Click **Save & New** to save the User Email field and return to the first step of the wizard.

## Add a Lookup Field to the Object
This field will be used so that the person requesting the new user can tell us what their permissions should be like- i.e. mirror this person. This is much easier than listing all the permissions they should or should not have.

1. For `Data Type`, select `Lookup Relationship` and click **Next**.

2. Select the `User Object` as the object the Salesforce Request will be related to.

3. Fill in the field details:
   - Field Label: `Mirror User`
   - Description: `This is a lookup field to the User Object`
   - Help Text: `Choose the user that this new user’s permissions should mirror`
4. Leave the defaults for the remaining fields, and click **Next**.

5. Click **Next** again to accept the default field visibility and security settings.

6. Click **Save & New** to save the Mirror User field and return to the first step of the wizard.


## Add a Rich Text Field to the Object
This field will be used by the person requesting new functionality - they add bold text, colored text, or pictures.

Create the Request Description field as follows:

1. For `Data Type`, select `Text Area (Rich)`, and click **Next**.

2. Fill in the custom field details:
  - Field Label: `Request Description`
  - Length: 32,768
  - # Visible Lines: 25
  - Field Name: `Request_Description`
  - Help Text: `Please enter as much detail- including pictures- around this request so the admin clearly knows what you are requesting`

3. Click Next.

4. Click Next again to accept the default field visibility and security settings.

5. Click Save & New to save the Request Description field and return to the first step of the wizard.

## Add a Category Picklist Field to the Object
This field will help us categorize the request. It will also make it easier for us to report on what types of request we get the most.

Create the Request Category field as follows:

1. For `Data Type`, select `Picklist`, and click **Next**.

2. Fill in the custom field details:
  - Field Label: `Request Category`
  - Enter the following values for the picklist (one per line) `User Activation`, `User Deactivation`, `General Customization`, `Reports & Dashboards`, `Duplicate Identified`, `Bug Fix`, `Change User Privileges`, `Other`

  - Leave the `Sort Values Alphabetically` - Unchecked
  - Leave the `Use first value as default value` - Unchecked

3. Help Text: `Please choose a category for your request`

4. Leave the defaults for the remaining fields, and click **Next**.

5. Click **Next** again to accept the default field visibility and security settings.

6. Click **Save & New** to save the Request Category field and return to the first step of the wizard.



## Add a Status Picklist Field to the Object
This field will help us track the status of the request. And is a reference for the requestor so they know what is going on with their request.  

_This field will have unique security around it in that only Admins can see it._

1. For `Data Type`, select `Picklist`, and click **Next**.

2. Fill in the custom field details:
  - Field Label: `Request Status`
  - Enter the following values for the picklist (one per line) `Open`, `Working`, `Closed`, `Rejected`
3. Check the `Use first value` as default value

4. Leave the defaults for the remaining fields, and click **Next**.

5. Click the **Read-Only** checkbox at the top of the column to make this field read only for all users.
6. Then **Uncheck** the box next to System Administrator, then click **Next**.

7. Click **Save & New** to save the Request Status field and return to the first step of the wizard.


## Add a Multi-Select Picklist Field to the Object
This field will help us inform management as to our resolutions for requests. And can also inform us on areas for improvement in training or management guidance.

_This field will also have unique security around it in that only Admins can see it._

1. For `Data Type`, select `Picklist (Multi-Select)` and click **Next**.
2. Fill in the field details:
  - Field Label: `Resolution`
  - Enter the following values for the picklist (one per line) `Training Issue`, `Management Guidance`, `Process Improvement`, `Data Issue`, `System Bug`

  - Leave the Sort Values Alphabetically- Unchecked
  - Leave the Use first value as default value - Unchecked
  - # Visible Lines: 4
  - Field Name: Resolution
  - Help Text: What were the solutions to this feature request?

1. Click **Next**.

1.  Leave every box unchecked in the Visible column for all profiles except the System Administrator, and click **Next**.

1. Click Save & New to save the Resolution field and return to the first step of the wizard.

## Add a Date Field to the Object
This field will help us track when the request was closed. It’s also important for us because we reference this field in the following formula field created in the next step.

1. For `Data Type`, select Date and click **Next**.

2. Fill in the field details:
  - Field Label: `Closed Date`
  - Field Name: `Closed_Date`

3. Leave the defaults for the remaining fields, and click **Next**.

4. Click the **Read-Only** checkbox at the top of the column to make this field read only for all users.

5. Then **Uncheck** the box next to System Administrator, then click **Next**.

6. Click **Save & New** to save the Closed Date field and return to the first step of the wizard.


## Add a Formula Field to the Object
This field will automatically calculate the formula fields that derives its value from other fields, expressions, or values. Formulas can help you automatically calculate the value of a field based on other fields.

1. For `Data Type`, select Formula and click **Next**.

2. Fill in the field details:
  - Field Label: `# Days open`
  - Choose `Number` as the Formula Return Type
  - Set the Decimal places at 0
  - Click **Next**

3. In the Formula Editor type the following formula:

    IF(ISBLANK(Closed_Date__c), TODAY() - DATEVALUE(CreatedDate) , Closed_Date__c - DATEVALUE(CreatedDate) )

4. Click the `Check Syntax` button to check for syntax errors. if you do find errors, fix them before proceeding.

![](images/03-formula-field.png)

5. Click **Next** and **Next** again to accept the default field visibility and security settings.

6. Click **Save** to Save your # Days open field.


## Try out the App


Click on the Salesforce Request tab at the top, then click the New button and fill out a Salesforce Request. 

![](images/03-salesforce-requests-new.png)

How easy is it to fill out a request?



<div class="row" style="margin-top:40px;">
<div class="col-sm-12">
<a href="02-tour-of-your-app.html" class="btn btn-default"><i class="glyphicon glyphicon-chevron-left"></i> Previous</a>
<a href="04-adding-page-layouts.html" class="btn btn-default pull-right">Next <i class="glyphicon glyphicon-chevron-right"></i></a>
</div>
</div>
