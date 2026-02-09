# Exercise 2 - Create Process

In this exercise, you will create a process in SAP Build Process Automation to update the billing block based on the approval.

## Table of Contents

- Exercise 2 - Create Process
  - Table of Contents
  - Overview
  - Exercise 2.1 - Add API Trigger to Process
  - Exercise 2.2 - Add Action to Read Sales Order Items
  - Exercise 2.3 - Create and add decision to Determine Approver
  - Exercise 2.4 - Add Approver Form with Sales Order Items Table
  - Exercise 2.5 - Add Action to Read Sales Order Header
  - Exercise 2.6 - Add Action to Update Sales Order
  - Exercise 2.7 - Add Approval and Rejection Emails
  - Exercise 2.8 - Release and Deploy the Process
  - Summary

---

## Overview

In this exercise you will learn:

- How to add an API trigger to a process
- How to add action to read sales order items
- How to utilise decisions to determine approver
- How to add action to update sales order
- How to add approval and rejection emails
- How to release and deploy the process

---

## Exercise 2.1 - Add API Trigger to Process

First, navigate to your SAP Build Lobby.

Lobby URL -  

User id - userXXX@example.com (say for example your number is given as 001, it will be user001@example.com and so on)

1. In the SAP Build lobby, click on **Create** button -> Process Automation:
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/1.png)<br>
2. Let's name our new project to **Manage Billing Block in Sales Order _<username>** and click **Create**. For example, if your username is 001, the project name would be Manage Billing Block in Sales Order_001.

Please use the correct naming convention and username , it will help you track your processes later during monitoring.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/2.png)<br>
3. Click **Create** in the above screen.

   Great! Your project is now created in a new tab, and you will be able to create your Process.

4. Before you proceed, please check that you are in the project created by you by validating your username. This is to ensure that you are not editing any other user’s project.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/3.png)<br>
5. Now click on **Create** in the above screen and select **Process** and enter the following details.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/4.png)<br>
   Enter **Name:** Billing Block Removal Process  
   Enter **Description:** Process to update the billing block based on the Approval

6. Choose **Create**

The Process gets added in the process builder. Now you will add an API Trigger to the Process.

API triggers are used to start a process in **SAP Build Process Automation** as a response from an API call from another application.

7. In the “Billing Block Removal Process” select **Add Trigger** and then select **API Trigger**.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/5.png)<br>
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/6.png)<br>
8. Enter Name as SalesOrderAPITrigger and click **Create**.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/7.png)<br>
The **API Trigger** is now created. Please make sure to save your work.
Now that you have the API Trigger created, click anywhere on the Process Builder canvas to open the side panel. This side panel opens the Process Inputs in the Variables tab. 
9. Click **Configure -> Add Input** and add the following input for Process Inputs and click **Apply**.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/8.png)<br>
   - SalesOrder
   - SalesOrganization
   - DistributionChannel
   - OverallBillingBlockStatus
   - Sold-To-Party
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/9.png)<br>
10. 11.	Save your work and note that the Process Inputs are updated. API Trigger inputs are defined at the Process Inputs level, and the same payload structure is sent from external applications via API calls to trigger the process.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/10.png)<br>
---

## Exercise 2.2 - Add Action to Read Sales Order Items

Next, you will add an Action to the Process that will read the sales order items.

1. In the Process Builder, select the **+** underneath the Trigger created, then choose **Action > Browse library**.

2. In the **Browse library** pop-up, select the **Reads all items of a sales order** Action and choose **Add**.

3. Click on the Action step and then in the **General** section of the Action:

   - Change the **Step Name** to Reads Sales Order Items  
   - Enter the **Destination variable:** S4HANADestination

4. In the **Inputs** section of the Action, for SalesOrder mapping, select the **SalesOrder** from the **Process Input**.

5. Click **Save**.

---

## Exercise 2.3 - Create and add Decision which would provide approver of the form

1. Create Decision with Name “DetermineApprover” from overview page.
2. Configure Input( SalesOrganization) and Output ( Approver) Parameters as shown in the image below.
3. Click on **Rules** tab and select create rule.
4. Configure the Rule.
5. Click **Finish**.
6. Enter the values and click on **save**.
7. Add the Decision to the Process.
8. Provide step name as “Determine Approver”.
9. Map SalesOrganization.
10. Click **Save**.

---

## Exercise 2.4 - Add Approver Form with Sales Order Items Table [AYUSH - completed]

1. Select **Approvals > Blank Approval**.
2. Choose **Save** and click **Open Editor**.
3. Configure the form.
4. For all text **Items Details > Configuration**, check **Read Only**.
5. Save your form.
6. Under **Subject**, enter: Approve billing block removal.
7. Under **Recipients**, type in your own **Email**.
8. Choose **Save**.

---

## Exercise 2.5 - Add Action to Read Sales Order Header

1. Select the Action named **Reads the header of a sales order**.
2. In the **General** section:

   - Change the **Step Name:** Get ETAG for PATCH  
   - Select the **Destination variable:** S4HANADestination

3. Map **SalesOrder**.
4. Choose **Save**.

---

## Exercise 2.6 - Add Action to Update Sales Order [AYUSH - completed]

1. Select **Actions**.
2. Select **Updates a sales order**.
3. In the **General** section:

   - Change the **Step Name** to: Updates a sales order  
   - Select the **Destination variable:** S4HANADestination

4. Map **ifMatch**.
5. Choose **Save**.

---

## Exercise 2.7 - Add Approval and Rejection Emails

1. Select **Email**.
2. Configure:

   - **Step Name:** Approval Notification  
   - **Recipients:** your email  
   - **Subject > Approved: Removal of Billing Blocks**

3. Open **Mail Body Editor** and add content.
4. Choose **Save**.

Create Rejection Notification:

5. Select **Email**.
6. Configure and choose **Apply**.
7. Save your work.

---

## Exercise 2.8 - Release and Deploy the Process

1. Choose the **Release** button.
2. Choose **Release**.
3. Choose **Deploy**.
4. Select the **Destination** and choose **Deploy**.

Great work! Your project is now deployed.

---

## Summary

Your project is released and deployed in SAP Build and you can head to the SAP S/4HANA system to run the process.

Continue to - Exercise 3 - Run Process
