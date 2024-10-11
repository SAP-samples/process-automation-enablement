# Create Sales Order Business Process


## Create a business process project
If you are not already in the SAP Build Lobby - click [Lobby](https://sap-build-academy-eu10.eu10.build.cloud.sap/lobby) to open the entry page of SAP Build.  
&nbsp;
1. In the Lobby, please search for the project **Sales Order Management Template D-com**. Make sure that you **search in all projects** and not only in your own projects. Once you have found the project, click the **Options** button (…) and select **Save As New Project**.  
&nbsp;
![Main](assets/SPA1.png)  
&nbsp;  
&nbsp;
&nbsp;
2. On the next screen, replace **Sales Order Management Template D-com** with **Sales Orders Management AC099201UXX**.  
   **Note**: Instead of XX maintain the last 2 digits of your user number.  
&nbsp;  
&nbsp;  
3. As description you may use **Sales Orders Management Project**.  
**Save As New**.  
&nbsp;
![Main](assets/SPA2.png)  
&nbsp;  
&nbsp;
&nbsp;
4. Wait a few seconds until your project is created and click on it.  
&nbsp;  
![Main](assets/SPA2a.png)  
&nbsp;  
&nbsp;
&nbsp;
5. **Accept** the **Disclaimer** and then you should see the following screen.  
&nbsp;  
![Main](assets/SPA3.png)  
&nbsp;  
&nbsp;
&nbsp;
&nbsp;
6. Click on **Create** and select **Process**.  
&nbsp;
![Main](assets/SPA4.png)  
&nbsp;  
&nbsp;
7. In the **Create Process** dialog box, enter the following values and click **Create**.  
&nbsp;  
&nbsp;
      | **Input Field** | **Input Value**  |
      | :------------------- | :---------- | 
      | Name             | Order Processing     | 
      | Description         | A process to handle sales orders      |
&nbsp;  
&nbsp;  
8. If you see the below prompt please click **Close**.  
&nbsp;
![Main](assets/SPA6.png)  
&nbsp;  
&nbsp;  
&nbsp;  
## Create and configure API trigger
&nbsp;  
1.	You are now in **Order Processing** page, click on **Add a Trigger**  
&nbsp;  
      ![Main](assets/SPA7.png)  
&nbsp;  
&nbsp;  
2.	Click on **Call an API**
&nbsp;  
      ![Main](assets/SPA8.png)
&nbsp;  
&nbsp;  
3.	Enter the name as **Sales Order Trigger** and click **Create**
&nbsp;  
      ![Main](assets/SPA9.png)
&nbsp;  
&nbsp;  
4.	A trigger has been added to your process. Click the << icon to open the **Process Details** screen.
&nbsp;  
      ![Main](assets/SPA10.png)
&nbsp;  
&nbsp;  
5.	Click on **Variables** then choose **Configure** (under **Process Inputs**) to configure inputs.
&nbsp;  
      ![Main](assets/SPA11.png)
&nbsp;  
&nbsp;  
6.	In the **Configure Process Inputs** window, choose **Add Input** to add parameters.
Add the following parameter:
&nbsp;  
	| **Name** | **Type**  | **Required** |
	| :--------- | ---------- | :---------- | 
	| salesorderdetails             | Sales Order      | true          |
&nbsp;  
&nbsp;    

7.	Click on **Apply**.
&nbsp;  
      ![Main](assets/SPA13.png)
&nbsp;  
&nbsp;  
8.	**Save** the Process.
&nbsp;  
      ![Main](assets/SPA14.png)
&nbsp;  
&nbsp;  
&nbsp;  

## Process Conditions
&nbsp;  
Create and configure Process Condition Once the trigger is created, define which process flow should run based on if/else condition criteria.
1.	To add a condition to a process open the Process Builder. Choose (+) next to the Trigger. Select **Controls and Events**
&nbsp;  
      ![Main](assets/SPA15.png)
&nbsp;  
&nbsp;  
2.	Select **Condition**.
&nbsp;  
      ![Main](assets/SPA16.png)
&nbsp;  
&nbsp;  
3.	To configure the condition, choose **Open Condition Editor**.
&nbsp;  
      ![Main](assets/SPA17.png)
&nbsp;  
&nbsp;  
4.	Edit your branch condition:
      a.	Select **quantity** from the Process Content.
      b.	Select is **greater than**.
      c.	Enter **10** as the value.
      d.	Choose **Apply**.
&nbsp;  
      ![Main](assets/SPA18.png)
&nbsp;  
&nbsp;  
You have configured your if branch to: if **Quantity is greater than 10**.
&nbsp;  
&nbsp;  
&nbsp;  
## Create and configure Approval form
&nbsp;  
Navigate back to the Process Builder canvas to create an Approval Form.
&nbsp;  
1.	On the If branch, click on **(+) > Approval > Blank Approval**.  
&nbsp;  
      ![Main](assets/SPA19.png)
&nbsp;  
&nbsp;  
2.	Enter the name as **Approval Form** and click **Create**.  
&nbsp;  
      ![Main](assets/SPA20.png)
&nbsp;  
&nbsp;  
3.	Select **Approval Form** and click **Open Editor**.  
&nbsp;  
      ![Main](assets/SPA21.png)
&nbsp;  
&nbsp;  
4.	Design the form by dragging and dropping the corresponding form elements as shown below.  
&nbsp;  
&nbsp;  
	| **Field Settings with Label**                                                                  | **Form Fields**     | **Configuration (Read Only)** |
	|--------------------------------------------------------------------------------------------|-----------------|---------------------------|
	| Approve Sales Order                                                                        | HeadLine 1      |                           |
	| A new order has been received. Please review and confirm whether the requirements can be met or not. | Paragraph       |                           |
	| Material                                                                                   | Text            | X                         |
	| Quantity                                                                               | Number          | X                         |
	| Customer Name                                                                              | Text            | X                         |
	| Expected Delivery Date                                                                     | Date            | X                         |
	| I acknowledge that we have received your order and will process it based on the availability | Checkbox        |                           |
	| Message to Buyer                                                                           | Text Area       |                           |
&nbsp;  
&nbsp;  
      The Approval form should be the same as below
&nbsp;  
       ![Main](assets/SPA23.png)
&nbsp;  
&nbsp;  
5.	**Save** the form.
&nbsp;  
&nbsp;  
6.	Back within the process, click on the **Approval Form** and configure the **Subject** and **Recipients**.
&nbsp;  
      In the Subject section:  
&nbsp;  
      -	Enter the subject as - **Please review the**  
      -	Map the **material** from the **salesorderdetails** Process Content popup to **Subject**.  
      -	In the **Recipients/Users** section, enter your email address (i.e. ac099201u**XX**@sapexperienceacademy.com).  
                  **Note**: Replace the XX with last two digits of your user number.  
      -	You can copy and paste the text: Use **paste as plain** text to paste the text!  
&nbsp;  
       ![Main](assets/SPA24.png)
&nbsp;  
&nbsp;  
       ![Main](assets/SPA25.png)
&nbsp;  
&nbsp;  
7.	Configure the inputs of **Approval Form**. Navigate to **Inputs** and map the fields accordingly.
      See below:
&nbsp;  
       ![Main](assets/SPA26.png)
&nbsp;  
&nbsp;  
8.	**Save** your work. You should see the following: 
&nbsp;  
       ![Main](assets/SPA27.png)
&nbsp;  
&nbsp;  
&nbsp;  
## Add and Configure Order Approval Notification Form
&nbsp;  
1.	After **Approve**, click on (+)
&nbsp;  
       ![Main](assets/SPA28.png)
&nbsp;  
&nbsp;  
2.	Click on **Form** and on **Order Confirmation Form**.  
        Note: As you have experienced the  creation of Forms in the previouse steps, we have preconfigured additional Forms for you. 
 &nbsp;  
       ![Main](assets/SPA29.png)
&nbsp;  
&nbsp;  
       ![Main](assets/SPA30.png)
&nbsp;  
&nbsp;  
3.	Back in the process, click on the **Order Confirmation Form** and configure the **Subject** and **Recipients**.  
&nbsp;  
      In the Subject section:
      -	Enter **Your order has been approved for**
      -	Map **material** from the **salesorderdetails** Process Content pop-up to **subject field**
      -	Please do not copy and paste the text. Enter the text yourself!
      -	In the **Recipients/Users** section, enter your email address (i.e. ac099201u**XX**@sapexperienceacademy.com). 
                  **Note**: Replace the **XX** with last two digits of your user number.
&nbsp;  
&nbsp;  
4.	Save your work  
&nbsp;  
       ![Main](assets/SPA31.png)  
&nbsp;  
&nbsp;  
5.	Configure the inputs of **Order Confirmation Form**. Navigate to Inputs and map the fields accordingly.
            See below:  
&nbsp;  
       ![Main](assets/SPA32.png)  
&nbsp;  
&nbsp;  
6.	Click **Save**.  
&nbsp;  
&nbsp;  
&nbsp;  

## Create and configure Order Rejection Notification Form
&nbsp;  
In this step, you will send out a notification form if the order is rejected.  
1.	Click on the (**+**) after the **Reject** node.
&nbsp;  
       ![Main](assets/SPA33.png)
&nbsp;  
&nbsp;  
2.	Click on **Form** and on **Rejection Notification Form**.  
        Note: As you have experienced the creation of Forms in the previouse steps, we have preconfigured additional Forms for you.  
&nbsp;  
       ![Main](assets/SPA34.png)
&nbsp;  
&nbsp;  
3.	Go back to the process select the **Rejection Notification Form**
&nbsp;  
&nbsp;  
4.	Click **General** tab
&nbsp;  
&nbsp;  
5.	In the **Subject** field:
      -	type **Your order has been rejected for**
      -	click to map **material** from **Process Content** => salesorderdetails
      -	In the **Recipients/Users** section, enter your email address ((i.e. ac099201u**XX**@sapexperienceacademy.com). 
                  **Note**: Replace the **XX** with last two digits of your user number.
&nbsp;  
&nbsp;     
6.	**Save** your work
&nbsp;  
7.	Configure the inputs of **Rejection Notification Form**. Navigate to Inputs and map the fields accordingly.
&nbsp;  
       ![Main](assets/SPA36.png)
&nbsp;  
&nbsp;  
8.	**Save** the form.
&nbsp;  
&nbsp;  
&nbsp;  
## Add and configure Auto Approval Notification Form
&nbsp;  
In this step, you will add a notification form which would be received by supplier if the order is approved automatically without any approvals.
&nbsp;  
1.	Go to the Process Builder and add the **Auto Approval Notification** form to the **Default** node.
&nbsp;  
       ![Main](assets/SPA59.png)
&nbsp;  
&nbsp;  
3.	Click (**+**) choose Form then Auto Approval Notification
&nbsp;  
       ![Main](assets/SPA37.png)
&nbsp;  
&nbsp;  
3.	Configure the **General** section.
&nbsp;  
4.	Under Subject:
      -	Enter the text: **Your order has been approved automatically for**
      -	Map material from **Process Content => salesorderdetails**.
      -	In the **Recipients/Users** section, enter your email address ((i.e. ac099201u**XX**@sapexperienceacademy.com). 
                  **Note**: Replace the **XX** with last two digits of your user number.
&nbsp;    
5.	Save your work.
&nbsp;  
       ![Main](assets/SPA60.png)
&nbsp;  
&nbsp;  
6.	Configure the **Inputs** section.
&nbsp;  
      | **Form Input Field** | **Process Content Entry**  |
      | :------------------- | :---------- | 
      | Customer Name             | shipToParty     | 
      | Expected Delivery Date         | expectedDeliveryDate      | 
      | Material Name             | material     | 
      | Quantity        | quantity     | 
&nbsp;  
&nbsp;  
       ![Main](assets/SPA38.png)    
&nbsp;  
&nbsp;  
 7.	**Save** your work. Your final process looks as below.        
&nbsp;  
       ![Main](assets/SPA39.png)    
&nbsp;  
&nbsp;  
       This completes the process design with condition criteria that will decide what process flow is executed and whether there will be an auto-approval or a one-step approval route.
&nbsp;  
&nbsp;  
&nbsp;  
## Release business process project
&nbsp;  
To run the process you have to first release and then deploy the business process project.
&nbsp;  
Releasing a project creates a version or snapshot of the changes and deploying the project makes it available in runtime to be consumed. You can only deploy a released version of the project, and at a given time there can be multiple deployed versions of the same project.
&nbsp;  
1.	In the Process Builder, to release a project, click **Release** button on the top-right corner of the screen and provide a description in the popup dialog.
&nbsp;  
       ![Main](assets/SPA40.png)   
&nbsp;  
&nbsp;  
      If you are releasing for the first time, then the version will start with **1.0.0.** Next time you release, the version numbers will be automatically updated.
&nbsp;  
&nbsp;  
2.	Click **Release**.
&nbsp;  
       ![Main](assets/SPA41.png)   
&nbsp;  
&nbsp;  
&nbsp;  
## Deploy released project
&nbsp;  
1.	Once the project is released successfully, Click **Deploy** button on the top-right corner of the screen.
&nbsp;  
       ![Main](assets/SPA42.png)   
&nbsp;  
&nbsp;  
2.	Select the **Public** environment and click **Deploy**.
&nbsp;  
       ![Main](assets/SPA43.png)   
&nbsp;  
&nbsp;  
3.	Click **Deploy**
&nbsp;  
       ![Main](assets/SPA44.png)   
&nbsp;  
&nbsp;  
       Deployment will take a couple of seconds/minutes depending upon how big your project is and how many different artifacts it has. 
       Any errors during the deployment will be shown in the Design Console at the bottom of the screen.
&nbsp;  
&nbsp;  
4.	Once the deployment is successful, you will see a changed status.
&nbsp;  
       ![Main](assets/SPA45.png)   
&nbsp;  
      You cannot edit released or deployed projects. 
      To continue working on your project, you need to select the Editable version of your project (at the top of the page).
&nbsp;  
&nbsp;  
&nbsp;  
## Publish to the SAP Build Library
&nbsp;  
1.	After you released and deployed the process, go to SAP Build Lobby and find your project (i.e. Sales Orders Management AC099201U**XX**).
&nbsp;  
2.	Click on the 3 dots under options and **Publish to Library**.
&nbsp;  
       ![Main](assets/SPA46.png) 
&nbsp;  
&nbsp;  
 3.	Select the version (you can select the most recent version) and click on Publish.  
        Now, your process will be visible from SAP Build Apps in SAP Build Library section.
&nbsp;  
       ![Main](assets/SPA47.png) 
&nbsp;  
&nbsp;  
You have successfully released, deployed and published your process. It is time to run the process and see the results.
&nbsp;  
&nbsp;  
&nbsp;  

## Run business process
&nbsp;  
1.	Let’s test the API Trigger in the **Monitoring** tab of the SAP Build Lobby.
      - Click on the **Manage > Process and Workflows** tile.
&nbsp;  
       ![Main](assets/SPA48.png) 
&nbsp;  
&nbsp;  
2.	Search for AC099201U**XX** to display your project.
&nbsp;  
       ![Main](assets/SPA49.png) 
&nbsp;  
&nbsp;  
3.	Click on **Start New Instance**.
&nbsp;  
       ![Main](assets/SPA50.png) 
&nbsp;  
&nbsp;  
4.	Remove the example payload in the dialog. Use the following JSON in the dialog.
 ```
      {
            "salesorderdetails": 
            {
            "distributionChannel": "10",
            "expectedDeliveryDate":"2024-02-25",
            "material": "MZ-FG-S200",
            "quantity":11,
            "salesOrderType":"OR",
            "salesOrganisation":"1710",
            "shipToParty":"SAP",
            "soldToParty":"1000292"
             }
      }
 ```
 &nbsp;  
The quantity must be entered as a number (no quotes) and dates must be entered in the format above for the expected delivery date.
&nbsp;  
&nbsp;  
Click **Start New Instance and Close**.    
&nbsp;  
![Main](assets/SPA51.png) 
&nbsp;  
&nbsp;  
Don’t modify the payload when you integrate with SAP Build Apps.
&nbsp;  
You did successfully run your project. It is time to monitor the process flow and access the tasks.
&nbsp;  
&nbsp;  
&nbsp;  

## Monitoring the process flow
&nbsp;  
Monitoring business process is one of the key aspect of the automated processes. Technical monitoring is an administrator job where a process admin proactively and consistently monitors the process performance, identifies any issues in the process and takes necessary actions to ensure business process continuity.
&nbsp;  
**SAP Build** provides different applications to monitor and manage different process artifacts. These applications are available under the **Monitor** tab.
&nbsp;  
1.	Earlier, we accessed **Processes and Workflows** under the **Manage** section to see all the deployed processes.
&nbsp;  
	To monitor all the running instances of the process, you must go to **Process and Workflow Instances** under the **Monitor** section.
&nbsp;  
	 
       ![Main](assets/SPA52.png) 
&nbsp;  
&nbsp;  
       In there, you will see all the running, erroneous and suspended process instances. 
       Use the filter bar to get a more customized view of the process instances based on different statutes like running, completed, suspended, terminated and so forth.
&nbsp;  
	The best way to find your process is to search for your user number or initials, depending on how you named it.
&nbsp;  
&nbsp;  
2.	Search for the project **Sales Orders Management AC099201UXX** using the Project dropdown. All the instances of the selected project is displayed in the table below. Select the latest one as it was the one created in the previous lesson.
&nbsp;  
       ![Main](assets/SPA53.png) 
&nbsp;  
&nbsp;  
       Explore different process monitoring options. Observe the process instance information, process context which is the actual process data flowing across different activities in the process and the execution logs where you can see entire trace of how the process has been progressing with some basic runtime information of each activity.
&nbsp;  
	Since the quantity is greater 10, the process requires an approval. You can check the Logs and Context for this instance.
&nbsp;  
       ![Main](assets/SPA54.png) 	
&nbsp;  
&nbsp;  
3.	As you can see the process is waiting for the task to be completed. These tasks are generated from the forms that are added in the process and can be accessed via the **My Inbox** application. Click on the icon on the top right corner to open the **My Inbox** applicaiton.	
&nbsp;  
       ![Main](assets/SPA55.png) 	
&nbsp;  
&nbsp;  
&nbsp;  
## Accessing the tasks
&nbsp;  
1.	Tasks are the request for the users to participate in an approval or review process. These tasks appear in the **My Inbox** application shipped with **SAP Build**. Users can claim, approve and reject the task from their inbox. You can add a message to the buyer.
&nbsp;  
&nbsp;  
2.	Click **Approve**.
&nbsp;  
       ![Main](assets/SPA56.png) 
&nbsp;  
&nbsp;  
3.	Once you **Approve/Reject** the order, **refresh** the inbox again to get the notification of Order Confirmation with the created sales order in the system.
&nbsp;  
	Click on **Submit** to acknowledge the order and complete the process.
&nbsp;  	 
       ![Main](assets/SPA57.png) 
&nbsp;  
&nbsp;  
4.	Once you acknowledge the notification sent via the approval process, the process will be completed. The Logs can be seen in the **Monitor** section.
&nbsp;  	 
       ![Main](assets/SPA58.png) 
&nbsp;  
&nbsp;  
&nbsp;  
**Congratulations!**
You successfully completed this unit and are ready to create a Sales Order App using SAP Build Apps. Please go to the next tutorial: [Create a Sales Order App Using SAP Build Apps](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/DSAG%20JK%202024/exercises/ex1/README.md)
