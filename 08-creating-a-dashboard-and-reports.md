---
layout: module
title: Module 8&#58; Creating a Dashboard and Reports
---

The Salesforce Request app you created with the App Quick Start wizard includes a Reports tab, where you can create, edit, run, and schedule reports. Start by creating a simple report that tells you how many Salesforce Requests you have and how many days open each request is.

## Create a Simple Report
In this exercise you will create a simple tabular report to show the number of Salesforce Requests and the number of days each one has been open. Tabular reports present data in simple rows and columns, much like a spreadsheet. They can be used to show column summaries, like sum, average, maximum, and minimum.

1. From the Reports tab, click **New Report**.

2. In the Quick Find box, enter `Salesforce`, and in the **Other Reports** folder, choose `Salesforce Requests`.

3. Click **Create**.

4. In the report builder, notice that the Salesforce Request Name field is already there. You only need one more field: # Days Open. From the Fields pane, Drag `# Days Open` onto the preview.

5. Let’s set a row limit for this report - so that it doesn’t get out of hand and so we can use it in a dashboard. To do that click **Add** next to filters and choose **Row Limit**.

6. Click OK to accept the default 10 row limit.

![](images/08-report-salesforce-requests-filter.png)

## Viewing only Open Request
To make sure we are only viewing open requests lets add a filter of `Request Status = Open, Working` (Be sure to click on the magnifying glass to choose your values).

1. Click on the **Dashboard Settings** button at the top.

2. Choose `Salesforce Request: Salesforce Request Name` for the **Name** field

3. Choose `# Days Open` for the **Value** field. Then click **OK**

>Steps 1, 2, & 3 are only used if a tabular report will be used in a Dashboard

4. Click Save, and give your report a meaningful name, such as `Salesforce Requests: Days open`.

5. In the Report Folder drop-down list, select  **Unfiled Public Reports**, so everyone can access it. 

>If you didn’t want this report to be accessible to everyone, you’d create a folder and give different people different levels of access to it.

6. Click **Save and Run Report**.

![](images/08-report-salesforce-requests-run.png)

You can get fancy with reports, but that’s all you need from this one. And as you’ll soon see, even this simple report gives you a lot of functionality. The following list are a few of the things you can do in the Report Wizard, and not necessarily with this report.

* Use the Summarize Information by drop-down list to summarize the report on any field on the Salesforce Request object. For example, you could summarize on Assigned Admin.

* Use the Show drop-down list specify whether you want to see just your requests, your team’s requests, or all requests.

* In the Time Frame section you can choose to run this report based on the created, modified, or last activity date, as well as choose the date range for the data you want to see.

* Click **Run Report** drop-down button, and choose to run the report now or on some future date. If you choose the latter, it takes only a few more clicks to have that report in your inbox every day--or however often you want it.

* If you’d rather see a summary than a bunch of details, click **Hide Details**.

* Click **Customize** to make changes to the report, and you’ll return to the familiar drag-and-drop interface you used to create the report.

* And finally, you can export the report as a printed document, spreadsheet, or CSV file by clicking **Export Details**.


<div class="row" style="margin-top:40px;">
<div class="col-sm-12">
<a href="07-app-on-salesforce1-moble.html" class="btn btn-default"><i class="glyphicon glyphicon-chevron-left"></i> Previous</a>
<a href="09-get-more-information-from-your-report.html" class="btn btn-default pull-right">Next <i class="glyphicon glyphicon-chevron-right"></i></a>
</div>
</div>
