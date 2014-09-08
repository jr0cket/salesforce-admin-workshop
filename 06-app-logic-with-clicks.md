---
layout: module
title: Module 6&#58; Adding App Logic with Clicks
---

In this exercise you will go a step further by learning advanced point-and-click development to further enhance the underlying database and improve the user interface.

## Automate a Field Update using Workflow
Let’s make it easy on the Admin so they only need to add a Closed Date and have the status update automatically to Closed.

1. From Setup, click **Create** | **Workflow & Approvals** | **Workflow Rules**.

2. Optionally, read the brief introduction, click **Continue**, and then click **New Rule**.

3. Select the `Salesforce Request` object, and click **Next**.

4. For the rule name, enter `Update Status to Closed`, and for the description enter `Updates status to Closed when Closed Date field is populated`

5. For the evaluation criteria, select **created, and any time it’s edited to subsequently meet the criteria**

6. For the first rule criteria row, for the field select **Salesforce Request: Closed Date**, for the operator select **Not Equal to**, and for the value leave blank.

7. Click **Save & Next**.


Continuing on, the next step is to assign an action to the workflow rule to update the Request Status field automatically.

1. Click the drop-down list that reads **Add Workflow Action** and choose **New Field Update**.

2. In the Name field enter `Update Status to Closed`

3. In the Field to Update list, choose `Request Status`

4. Choose a `Specific value of Closed`

5. Click **Save** and then click **Done** to return to the detail page of the new workflow rule.

6. From the Workflow Rule detail page click the **Activate Button**.

## Try out the App!
Go back to the request and populate the Closed Date field. Did the status change? You can use workflows to automate other aspects of this app, too.


<div class="row" style="margin-top:40px;">
<div class="col-sm-12">
<a href="04-adding-page-layouts.html" class="btn btn-default"><i class="glyphicon glyphicon-chevron-left"></i> Previous</a>
<a href="06-app-logic-with-clicks.html" class="btn btn-default pull-right">Next <i class="glyphicon glyphicon-chevron-right"></i></a>
</div>
</div>
