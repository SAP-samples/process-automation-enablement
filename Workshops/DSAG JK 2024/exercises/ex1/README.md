# 2. Create a Sales Order App Using SAP Build Apps  DSAG
&nbsp;
Click [Lobby](https://sap-build-academy-eu10.eu10.build.cloud.sap/lobby) to open the entry page of SAP Build Apps.
1.	In the Lobby, use the search field to look for the project named **DSAG-Buildapps-Template**.
&nbsp;
![apps1](https://github.com/user-attachments/assets/4af32add-4754-4b33-995a-fafe38123be1)
&nbsp;
2.	Once you have found the template app, click the **Navigate** symbol >; go to tab **Versions**, click on the 3 dots and select **Save As New Project**.
&nbsp;  
![apps2](https://github.com/user-attachments/assets/ab4a45ff-bb85-470e-a573-0755cb661bd3)
&nbsp;  
3.	On the next screen, enter the following (replace **XX** with the last 2 digits of your user number):
&nbsp;  
&nbsp;  
    | **Input Field**  | **Input Value**                                   |
    |--------------|--------------------------------------------------|
    | Project Name | Create Sales Order AC121055U**XX**                  |
    | Description  | SAP Build Apps Sales Order Project AC121055U**XX**   |
&nbsp;  
&nbsp;  
Now, click **Save As New**.  
&nbsp;  
![apps3](https://github.com/user-attachments/assets/c5e6d719-92a6-4255-8c74-11091f374d74)
&nbsp;  
&nbsp;  
Once your project is saved, it should open the **SAP Build Apps editor** automatically, as below.  
If the project does not open automatically, simply click your project’s name in the lobby.  
&nbsp;  
You can see the basic components of the UI are already in place:  
&nbsp;  
![apps4](https://github.com/user-attachments/assets/08526c03-ba33-4806-a22c-905c3badbbd1)
&nbsp;  
&nbsp;  
&nbsp;  
## Enable Integration Process
&nbsp;  
For this tutorial, we have already published your SAP Build Process Automation process to the SAP Build Library.
In order to trigger and consume processes from SAP Build Process Automation directly in SAP Build Apps, you need to set up the integration process.
&nbsp;  
1.	Open the **Data** tab, at the top of the page.
&nbsp;  
2.	Click **Add Integration**.
&nbsp;  
![apps5](https://github.com/user-attachments/assets/9ab13c36-ed0c-4c8d-aeaf-b6e17954bdac)
&nbsp;  
&nbsp;  
3.	Choose **SAP Build Library** from the 3 options.
&nbsp;  
![apps5a](https://github.com/user-attachments/assets/c25f26c2-e80f-43f9-b0c5-2b504f277560)
&nbsp;  
&nbsp;  
4.	You should now see a list of all published processes. You need to filter on the **Project Name** for the sales order process: **Sales Orders Management AC121055UXX**.
5.	Now click on the tile to select the process that you want to integrate.
&nbsp;    
![apps6](https://github.com/user-attachments/assets/44f524d7-df2f-42c2-966e-b508dab7de79)
&nbsp;  
&nbsp;  
6.	Choose **Enable process** to integrate the process.
&nbsp;  
![r9](https://media.github.tools.sap/user/67204/files/05121d4b-591b-4fee-b399-d8685ad0a764)
&nbsp;  
7.	Click **Exit**.
&nbsp;  
![r10](https://media.github.tools.sap/user/67204/files/43f846c2-eedf-40d4-abb3-ebcfc73b2b2d)
&nbsp;  
Now your SAP Build Process Automation process is integrated into your SAP Build Apps project, and you can see it available in the SAP Build Library:
![apps7](https://github.com/user-attachments/assets/90d4c6aa-1421-4daa-b7b9-cd5193b2cef9)


8. Click **Save**.
&nbsp;
&nbsp;
## Create page variables  
&nbsp;  
Whenever we want to trigger a workflow, we need to send some data – in this case, the sales order information. Now, we will create the page variables that will hold the information.  
We will create the page variables for the **Customer, Material, Quantity** and the **Delivery Date** input fields. Later on in this tutorial, we will bind these page variables to their respective input fields.  
&nbsp;  
1.	Back on the **UI CANVAS**, select **Variables**.  
&nbsp; 
![r12](https://media.github.tools.sap/user/67204/files/d1808453-620a-459b-8f59-39c0dad3d812)
&nbsp;  
&nbsp;  
2.	On the left side, click **Page Variables** then click **Add Page Variable**.  
&nbsp;  
![r13](https://media.github.tools.sap/user/67204/files/090c4751-959c-450e-a2ed-d39c1b630ce8)
&nbsp;  
&nbsp;  
3.	Add a page variable for **Customer** of value type **text**.  
&nbsp;  
![r14](https://media.github.tools.sap/user/67204/files/5321fbef-d856-4a5b-8d7f-1308774084e1)
&nbsp;  
&nbsp;  
4.	Now, add a page variable for **quantity** of value type **number**.  
&nbsp;  
5.	Next, add a page variable for **material** of value type **text**.  
&nbsp;  
6.	And finally, add a page variable for **date** of value type **date text (ISO 8601)** - **Note:**  Do not select **date/time text** as the data type.
&nbsp;  
7.	You have created the page variables for the Customer, Material, Quantity and the Delivery Date input fields.
&nbsp;  
![r15](https://media.github.tools.sap/user/67204/files/9f245394-c3f8-47da-9fd6-033900e76f5d)
&nbsp;  
&nbsp;  
8.	Click **Save** (upper right).
&nbsp;  
&nbsp;  
&nbsp;  
## Bind page variable to UI elements
&nbsp;  
We created page variables for the sales order data, but now we need to get the data entered by the user into the respective variable.  
We do this by binding each page variable to their respective UI elements, specifically, to the input boxes.  
Whenever someone types into the input box, the value is automatically copied into the corresponding page variable.  
&nbsp;  
1.	Go back to **View** so you can see the UI canvas.
&nbsp;  
![r16](https://media.github.tools.sap/user/67204/files/1f0da2a0-d0b5-4b4f-971a-4e47b5ee1afb)
&nbsp;  
&nbsp;  
2.	Using the **TREE** structure, click on the first input field (for **Customer**).   
In the **Properties tab**, click the **X** in the **Value** field.
&nbsp;  
![r17](https://media.github.tools.sap/user/67204/files/e2c569ba-8834-4908-9ee4-b80be9767cf6)
&nbsp;  
Select **Data and Variables > Page variable**. Then under Select page value, select **Customer** and click **Save**.  
&nbsp;  
![r18](https://media.github.tools.sap/user/67204/files/fc8751f4-a59a-4287-8f4a-194ffbeefeb4)

3.	Now, you'll do the same for **Material**: using the **TREE** structure, click on the second input field (you'll find it in container 2).  
In the **Properties** tab, click the **X** in the **Value** field, and select **Data and Variables > Page Variable > material**. And click **Save**.
 
4.	Same steps for **Quantity**: using the **TREE** structure, click on the third input field. In the **Properties** tab, click the **X** in the **Value** field, and select **Data and Variables > Page Variable > quantity**. And click **Save**.  
 
5.	Lastly, repeat the steps for **Delivery Date**: using the **TREE** structure, click on the third input field. In the **Properties** tab, click the **X** in the **Value** field, and select **Data and Variables > Page Variable > date**. And click **Save**.
&nbsp;  
6.	Click **Save** (upper right).
&nbsp;  
## Add logic to trigger workflow  
&nbsp; 
We need to set up the logic so when someone clicks the **Get Approval** button (an event), we send the sales order data to our SAP Build Process Automation workflow using the trigger process.
&nbsp; 
1.	Click on the **Get Approval** button, and open the logic canvas by clicking **Add logic to Button1** at the bottom right.  
&nbsp; 
![r19](https://media.github.tools.sap/user/67204/files/549ad0a4-9d54-454b-8082-dbb052f02fc8)
&nbsp; 
2.	Drag a **Trigger process** function onto the canvas, and connect the component tap event to it.  
&nbsp; 
![r20](https://media.github.tools.sap/user/67204/files/6706c1a4-fa87-41ac-974d-8a5e70a843a4)
&nbsp; 
3.	In the logic canvas, click on **Trigger process** and then click on **Custom Object**.  
&nbsp; 
![r21](https://media.github.tools.sap/user/67204/files/670abd2b-c535-4441-9384-3833a3a9baf6)
&nbsp; 
4.	Map the Sales Order fields to their corresponding page variable: Click on the **X >> Data and Variables >> Page variables >> Material** and **Save**.

![r22](https://media.github.tools.sap/user/67204/files/40f7e338-886a-4496-a6e7-0749313b1321)

![r23](https://media.github.tools.sap/user/67204/files/1946d595-df13-4b97-bc90-06a310a04c78)

Repeat the same steps for the other fields:

| **Sales Order Fields** | **Page Variable**  |
| :--------------------- | :----------------- | 
| material               | material           | 
| quantity               | quantity           | 
| shipToParty            | customer           |
| expectedDeliveryDate   | date               |  

5.	For the remaining Sales Order fields type in the following values as **Static text**.  
&nbsp;  
|**Sales Order fields**    | **Static Text Value** |
|-------------------------|-------------------|
| soldToParty             | 1000292           |
| salesOrderType          | OR                |
| salesOrganisation       | 1710              |
| distributionChannel     | 10                |
&nbsp;  

6.	You'll end up with a list like in the image below. Then click **Save**.
![r24](https://media.github.tools.sap/user/67204/files/66133820-0255-400e-a4f5-0649ebbbf060)
&nbsp;  
7.	Drag a **Toast** flow function onto the canvas. And connect the top output of the **Trigger** process flow function to it.
&nbsp;  
![r25](https://media.github.tools.sap/user/67204/files/72910321-c088-48d8-9fad-57cbb0618e26) 
&nbsp;    
8.	Click on the **Toast** flow function and configure it in the **Properties** pane on the right. For **Toast message**, click on the ABC symbol.  
&nbsp;  
![r26](https://media.github.tools.sap/user/67204/files/1a3c241c-ece1-40fd-867e-4ef20d4883ab)

Select **Formula > Formula**. Now, erase the quotation marks...

![r27](https://media.github.tools.sap/user/67204/files/fc748278-f1cc-4f1f-afcf-428733ec43ac)

... and enter the formula below and click **Save**.  
```
"Triggered process with ID: " + outputs["Trigger process"].newProcessInstance.id
```
&nbsp;  
&nbsp;  
![r28](https://media.github.tools.sap/user/67204/files/9940e0c6-c6a8-4c54-9a2b-857fae63384d)
&nbsp;  
9.	Now click **Save** (upper right).  
&nbsp;  
&nbsp;  
&nbsp;  
## Run app  
&nbsp;  
1.	Click the **Launch** tab, and then **Open Preview Portal >> Open Web Preview**. 
&nbsp;  
![r29](https://media.github.tools.sap/user/67204/files/ac4b037a-2264-4d2c-ae52-9a22fb812d5b)

3.	Select your project **Create Sales Order AC096525UXX**.  
&nbsp;  
![r30](https://media.github.tools.sap/user/67204/files/1a14eb59-d72d-49f7-913d-0fd1e673ac33)
&nbsp;  
4.	Enter the following values in your form:  
&nbsp;
| **Field**        | **Value**              |
|---------------|---------------------|
| Customer      | AC096525U05 Bikes   |
| Material      | MZ-FG-S200          |
| Quantity      | 1200                |
| Delivery Date | 2024-09-01          |  
&nbsp;  
&nbsp;  
5.	Click **Get Approval**.  
&nbsp;  
You process should be triggered and require approval (since the quantity figure is above 10).  
You should see the toast message indicating the workflow was triggered, and with the process instance ID.  
&nbsp;  
![r31](https://media.github.tools.sap/user/67204/files/c5a295ce-f39c-4f2a-a379-8da428435b19)


You can also see the results of the call in the [SAP Build Monitor](https://sap-build-academy-eu10.eu10.build.cloud.sap/lobby). 
&nbsp;  
&nbsp;  
6.	Go to the **Monitoring** tab, then **Process and Workflow Instances**.  
&nbsp;  
![38](https://media.github.tools.sap/user/67204/files/4313309f-9324-4144-a211-4b845dd94c2d)  
&nbsp;  
The first process listed should be the one you just triggered.  
•	You can see the new process instance.  
•	You can see the process ID is the same as in the toast message in the app.  
•	You can see the context, which is the values sent with the API (4 of them, in yellow, you entered in the input fields and the others were hardcoded in the formula for the Create record flow function).  
•	You can also see the execution log, which shows that the process stopped at the approval step (since the quantity was at least 10) and is awaiting approval. If you expand the approval step you can see more information, including who the approval request was sent to.  
&nbsp;  
![39](https://media.github.tools.sap/user/67204/files/eec27af0-acb6-465a-ad49-dcf72cc727c0)  
&nbsp;  
Congratulations!  
You successfully completed this tutorial and are ready to integrate the Sales Order App using SAP Build Work Zone.  
Please go to the next tutorial: [Integrate an SAP Build Apps application into SAP Build Work Zone, advanced edition](https://github.tools.sap/SAP-d-com-Mannheim-2024/HT006/blob/main/exercises/ex2/README.md)
