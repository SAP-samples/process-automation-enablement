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
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/11.png)<br>
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/12.png)<br>
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/13.png)<br>
2. In the **Browse library** pop-up, select the **Reads all items of a sales order** Action and choose **Add**.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/14.png)<br>
3. Click on the Action step and then in the **General** section of the Action:

   - Change the **Step Name** to Reads Sales Order Items  
   - Enter the **Destination variable:** S4HANADestination
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/15.png)<br>
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/16.png)<br>
4. In the **Inputs** section of the Action, for SalesOrder mapping, select the **SalesOrder** from the **Process Input**.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/17.png)<br>
5. Click **Save**.

---

## Exercise 2.3 - Create and add Decision which would provide approver of the form

1. Create Decision with Name “DetermineApprover” from overview page.
2. Configure Input( SalesOrganization) and Output ( Approver) Parameters as shown in the image below.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/18.png)<br>
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/19.png)<br>
4. Click on **Rules** tab and select create rule.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/20.png)<br>
6. Configure the Rule.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/21.png)<br>
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/22.png)<br>
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/23.png)<br>
8. Click **Finish**.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/24.png)<br>  
10. Enter the values and click on **save**.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/25.png)<br>  
11. Add the Decision to the Process.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/26.png)<br>  
13. Provide step name as “Determine Approver”.
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/27.png)<br> 
15. Map SalesOrganization.
  <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/28.png)<br>  
17. Click **Save**.

---

## Exercise 2.4 - Add Approver Form with Sales Order Items Table

1. Select **Approvals > Blank Approval**. Enter name "Approval Form".
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/30.png)<br>
   
2. Choose **Save** and click **Open Editor**.
  <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/31.png)<br>
   The Form Builder opens. You will now create an approval form with a Sales Order Items Table.
3. Select the H1 for Heading 1 and drag and drop on the top section. Write Review and Approve Billing Block Changes in Sales    Order. This is the name of our approval form which the recipient receives.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/32.png)<br>
4. Afterwards, drag and drop the sections as below and type the following texts to enrich the form:
    <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/33.png)<br>
 •	Paragraph: Sales Order Billing is blocked for below sales order. Please review the details and click Approve or Reject button at the bottom of this form. If you approve, the billing block will be removed from the sales order in the backend S/4HANA system.<br>
•	Text: Sales Order Number<br>
•	Text: Sold-To-Party<br>
•	Text: Distribution Channel<br>
•	Text: Billing Block Status (C= Blocked)<br>

5. For all text **Items Details > Configuration**, check **Read Only**.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/34.png)<br>

6. Now, we will add a sales order new table underneath as below.
    <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/35.png)<br>
    •	Enter New Table: Items Details<br>
    •	Under Items Details > Configuration, check Read Only<br>
    •	Select the +<br>
    •	Select Text to add a new Text to the table<br>
     <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/36.png)<br>
7. Enter New Text: Item and add a new Text.
    
8.  Enter New Text: Material and afterwards repeat step 7 to add two other Texts: ItemDescription and RequestedQuantity.
    You should now have a table that looks like below with 4 columns:
  <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/37.png)<br>
9. Now we will add a section where the Approver leaves a comment when approving or rejecting the form.
     <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/38.png)<br>
•	Drag and drop New Paragraph, and a New Text Area as below.<br>
•	Paste the following texts into the sections created. "Please add your comment indicating your approval or rejection reasons for billing block removal:" and "Approver's Comment"<br>
•	Make the comment a required step.<br>
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/39.png)<br>
10. Save your form.
  

15. Navigate back to the Billing Block Removal Process.

16. Select the Approval Form. In the General section of the Form:<br>
  •	Under Subject, enter: Approve billing block removal: and select SalesOrder from the Process Inputs<br>
  •	Under Recipients, type in your own Email <br>
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/40.png)<br>
17. Map the following:<br>
•	Sold-To-Party to Process inputs > SoldToParty<br>
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/41.png)<br>
18. Choose **Save**.

---

## Exercise 2.5 - Add Action to Read Sales Order Header
Navigate back to the Billing Block Removal Process, select the + sign to create conditional flows as to what happens when an approval form is approved or rejected.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/42.png)<br>
You will now add an **Action** to the Process to read the sales order header.
1. In the Available Actions pop-up, select the Action named **Reads the header of a sales order** .
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/43.png)<br>
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/44.png)<br>
3. In the **General** section of the Action:<br>
•	Change the **Step Name**: Get ETAG for PATCH<br>
•	Select the **Destination variable**: S4HANADestination<br>
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/45.png)<br>
The GET Call is necessary before the Update(PATCH) call to fetch the latest etag. The etag should be updated every time you trigger a POST request that changes data.<br>
This is necessary since the etags are used for concurrency control. If you have a UI, for example, then the UI reads data and a user may trigger updates to the business data. If another user changed something in the meantime, then our first user would trigger a change based on outdate information. This is why optimistic locking is used for concurrency control.<br>

4.	Go to the **inputs** section of the Action and map **SalesOrder** to **Process Inputs > data > SalesOrder**.
   <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/46.png)<br>
6.	Choose **Save**.


---

## Exercise 2.6 - Add Action to Update Sales Order 

Now, you will add an Action to the Process to update the sales order.
1.	Like previous exercise, in the **Process Builder**, select + under the previous **Action** and choose **Actions**.
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/47.png)<br>
2.	In the Available Actions pop-up, select **Updates a sales order**.
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/48.png)<br>
3.	In the General section of the Action:<br>
•	Change the Step Name to: **Updates a sales order**<br>
•	Select the Destination variable: **S4HANADestination**<br>
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/49.png)<br>
4.	Go to the **Inputs section** of the Action and map **ifMatch** to **Get ETAG for PATCH > result > Sales Order Header > metadata > etag**.
 <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/50.png)<br>
5.	Map **SalesOrder** to **Process Inputs > data > SalesOrder**
  <br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2/images/51.png)<br>
6.	Choose **Save**.


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
