## Table of Contents
- [Overview](#overview)
- [Definition ID from SAP Build Process Automation](#SPA)
- [Definition ID to SAP Build Apps](#build)
- [Testing the app](#Test)
- [Monitoring and approving the process](#name)

## Testing the End to End Scenario <a name="overview"></a>
Although, your application is connected to SAP Build Process Automation service, it is not connected to the process you created yet. At this stage, you will see how to connect your app and process.

## Copy Definition ID from SAP Build Process Automation <a name="SPA"></a>

1. Open the <b>SAP Build</b> lobby. Choose the <b>Monitor</b> tab.<br><br>
![](images/ss1.png)

2. Click on <b>Process and Workflow</b> under the <b>Manage </b> section.<br><br>
![](images/Processes%20and%20Workflows.png)

3. Search for your project name under <b>Project</b>. Select the project you created with the ID provided to you. For example: <b>Invoice Process AD160-XXX</b>.<br><br>
![](images/Search%20invoice.png)

4. After you find your process, copy its <b>Definition ID</b>.<br><br>
![](images/Def%20ID.png)

## Enter the Definition ID in SAP Build Apps. <a name="build"></a>

1. Go back to the **Lobby** and open your Build Project. Choose **SAP BTP Authentication** to go back to your project.<br><br>
![](images/01.png)

2. Choose **Empty page** to view your project.<br><br>
![](images/02.png)

3. Click on <b>DATA</b> tab. <br><br>
![](images/ss4.png)

4. Select the <b>SendtoSPA</b> data entity.<br><br>
![](images/ss5.png)

5. In the <b>create</b> tab, open the binding menu for <b> Request body mapper</b>.<br><br>
![](images/ss6.png)

6. Open the formula editor. Enter the following formula:

    <pre>ENCODE_JSON({  "definitionId": "<b>Your Definition ID copied from SPA</b> ",  "context":  query.record })  </pre>

    Click on <b>SAVE</b>.<br><br>
    ![](images/ss7.png)

7. Click on <b>SAVE.</b><br><br>
    ![](images/ss8.png)

8. You can test if this Data connection is working.<br>Switch to <b>TEST</b> tab and enter the below values in the following fields to test the connection:
    - filename: <i>Test1666861993010.png</i>
    - foldername: <i>Invoices</i>
    - employeemail: <i>Test</i>
    - employeename: <i>Test</i>

    Click on <b>RUN TEST</b>.

    ![](images/Test1.png)

10. Scroll down and check the Status of the Response.

    > If you are getting any error please recheck the steps 1-6, else request help from the presenters.
If you get the response as <b>Status:OK</b>, then the connection is successful.<br>

    Select **SAVE DATA RESOURCE**.

    ![](images/Test2.png)


11. Click on <b>SAVE</b> on the top right corner to save the changes.

    ![](images/ss10.png)


## Testing the App <a name="Test"></a>

1. Open the <b>Launch</b> tab.<br><br>
![](images/ss11.png)

2. Click on <b> OPEN APP PREVIEW PORTAL</b>.<br><br>
![](images/ss12.png)

3. Click on <b>Open web preview</b>.<br><br>
![](images/ss13.png)
3. Select the Build Apps project you created.<br><br>
![](images/App.png)

4. Enter the name and upload the invoice to test the process.
The invoice can be downloaded <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/DSAG%202023/exercises/1_CreateBuildAppProject/images/Invoice.png?raw=true">**HERE**</a>.

    ![](images/ss14.png)

5. After uploading the invoice, click on **Submit** button.<br><br>
![](images/Submit%20.png)

6. If the invoice is submitted successfully, you should receive a success toast message.<br><br>
![](images/Successs%20s.png)


## Monitoring and approving the Process <a name="name"></a>

1. Navigate back to the **SAP Build Lobby**, choose the **Monitor** tab, and then **Process and Workflow Instances**.

    ![Monitor](images/01_Monitor.png)

2. Choose **Get Invoice Details** instance, to check the status of the **CONTEXT** to see the details of approval request, and **EXECUTION LOG** to see the steps executed by the process.

    ![Monitor](images/BB1.png)

    > In the **EXECUTION LOG**, you can see how the process instance progresses further to the approval step in the business process.

    ![Monitor](images/BB2.png)

3. Open **My Inbox** application by selecting the button at the top right corner.

    ![Lobby](images/BB3.png)

4. After opening the **My Inbox** application, you will see on the left-hand side all the tasks listed. Select the task with the invoice number with which you triggered the process.

    ![My Inbox Actions](images/03_MyInbox_Actions.png)

5. Move on with one of the actions:
      - **Approve**, **Reject**,
      - **Show Log** (to see what has been done so far),
      - **Claim** (to reserve this task for you),
      - **Mail** (to forward this task via email).

      ![Task Actions](images/04_TaskActions.png)

10. You could also **sort**, **filter** or **group** the tasks at the bottom of the task list with these buttons:

    ![My Inbox Filter](images/05_MyInbox_Filter.png)

11. Depending on your selected actions and the information you have provided at the start of the process, the next task would be to **Approve** the invoice.

    ![Confirmation Form](images/06_ConfirmationForm.png)




## Summary

Congratulations!!! You have successfully completed the excercise, by connecting your app with process and also tested it End-to-End.

![Summary](./images/Summary.png)
