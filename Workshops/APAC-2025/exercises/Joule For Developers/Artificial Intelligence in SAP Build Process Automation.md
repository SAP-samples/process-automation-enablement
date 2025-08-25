## Artificial Intelligence in SAP Build Process Automation
In this exercise we will learn how to use Joule for Developers capabilities of SAP Build in Process Automation. We will use following features to create a sample Purchase Requisition Approval process: 
1. Generate Process Template 
2. Generate Form 
3. Generate Script 
4. Generate Business Rules 

## Enable Generative AI option
Login to SAP Build Lobby Navigate to Control Tower and ensure "Enable Generative AI" is enabled.
<img width="1357" height="626" alt="image" src="https://github.com/user-attachments/assets/edd25cc4-469a-4430-a422-d15484004156" />

## Project Creation
1. Login to SAP Build Lobby and Click on Process Automation
<img width="1557" height="433" alt="image" src="https://github.com/user-attachments/assets/dae4e689-9941-40e5-9549-9d1e27335d3e" />


2. Enter project Name & Description and click Create. This will create a project with given name & description.
<img width="1137" height="560" alt="image" src="https://github.com/user-attachments/assets/ee027f05-6dc4-4e64-83c5-f2d25d521720" />

## Process Generation
In this step we will generate Purchase Requisition Approval process template using Generative AI.  

1. Click on Generate and select Process
<img width="664" height="256" alt="image" src="https://github.com/user-attachments/assets/bbe42913-7662-477d-8e7d-1769bc7a02d6" />

 

2.	Enter following prompt Generate an empty process template called “Purchase Requisition” with an approval form and click on send icon <img width="26" height="24" alt="image" src="https://github.com/user-attachments/assets/8fe2f508-18af-4238-87e4-f14eadd2222d" />
System will create a process template and open design editor to continue designing the process.
 
<img width="664" height="265" alt="image" src="https://github.com/user-attachments/assets/00a893e8-5086-455a-b8cb-20e6e8003042" />

3.	In this step we will generate a form using Generative AI and use it as Trigger Form to start the process.

4.	click on "+" button after "Add a Trigger" step. From Smart Menu, select Form.
   <img width="670" height="372" alt="image" src="https://github.com/user-attachments/assets/f28b6d3d-5f91-4259-8b7d-ee656269dab1" />

6.	Enter the prompt to generate input form "create input form that has product name, quantity, price, supplier".  Click on Save

 <img width="672" height="334" alt="image" src="https://github.com/user-attachments/assets/14532531-5941-4f6c-b408-e059d9a1e621" />

7.	Once the form is generated, Click on Save 
 <img width="558" height="113" alt="image" src="https://github.com/user-attachments/assets/5874a639-af3e-4fad-b559-d54047df91cd" />


8.	Click on Add a Trigger, select Submit a Form, choose the form which we created in the last step and Save.

 <img width="672" height="328" alt="image" src="https://github.com/user-attachments/assets/ad51cb08-3b9d-4251-9523-78574fb884b3" />


Note:  Save work with each step just to make sure we do not lose out on any information.

9.	Click on <img width="29" height="23" alt="image" src="https://github.com/user-attachments/assets/93a3de6c-f048-408f-8b4b-ada78c206608" />
  to open side process panel, select Variables, configure a process custom variable "totalprice" (of string type) and Save the process.

10.	Because we are using Product Information Form to Trigger the process, we will remove it from next step. Select Product Information Form, click on three dots, click on Remove and Save the process.

## Script Generation
1.	In this step we will write a custom script using Generative AI to calculate total price value and assign to custom variable.

2.	Click on ‘+’ next to Trigger, select Script Task from smart menu, 
<img width="652" height="591" alt="image" src="https://github.com/user-attachments/assets/7159764d-95fd-4435-bc10-5e0ac5f67a38" />


3. Click on Open Editor, select all existing content and delete it
<img width="671" height="299" alt="image" src="https://github.com/user-attachments/assets/c2fe81b8-368a-4255-a062-0287863d0efc" />
 

4.	Click on Generate, enter the following prompt “generate script that calculates totalprice by multiplying $.context.startEvent.price and  $.context.startEvent.quantity and convert to string and assign to $.context.custom.totalprice”

System will generate script, check if script is fine, Accept it, Validate Script, Apply and Save Process.

 <img width="736" height="330" alt="image" src="https://github.com/user-attachments/assets/a58405ee-d17f-4598-92fc-2a7695b1ce32" />

## Rules Generation
1. In this step we will create a business rule using Generative AI to dynamically determine approvers of purchase requisitions.

2. After script task, click on "+", select Decision from smart menu, click on Blank Decision, give the name as "Determine Approver" and click on Create.
 <img width="696" height="615" alt="image" src="https://github.com/user-attachments/assets/d8582a40-efa0-4252-b27f-ee312945c0c7" />


3.	Decision will open in a new tab, from right side panel create input parameter "Supplier" (string) , output parameter "approver" (string) and Save the Process.
<img width="778" height="319" alt="image" src="https://github.com/user-attachments/assets/a1f4f33d-688d-4a31-90d8-dd7547ba7058" />


4.	Click on Generate, select Generate Rule, and give following prompt and Save Process – 

create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "adminmanager@sap.com". If supplier is 1720, it must be approved by "procurementmanager@sap.com”

Note: Replace email ID with valid process automation user email id for testing purpose.

<img width="745" height="300" alt="image" src="https://github.com/user-attachments/assets/755fe11c-6573-4831-b75b-11061d3c275e" />
	 

5.	Go back to Purchase Requisition process tab, in case you do not see decision added, click on ‘+’ button after Script Task, select Decision from smart menu and select Determine Approver decision which we created in last step.

 
<img width="644" height="241" alt="image" src="https://github.com/user-attachments/assets/bb45a0e1-e287-4d59-970d-30e0c997cc43" />


6.	Select Determine Approver decision in main process, on the right-hand side panel select Inputs, map it with Supplier information from coming from Trigger form and Save the process.
<img width="738" height="283" alt="image" src="https://github.com/user-attachments/assets/fa260d19-6df9-4cae-8b75-2d4b7e34756f" />

 

7.	In the step we will modify Approval Form and map it with input field & calculated variables.

a.	Click on three dots next to Approval Form and click on Open Editor.
<img width="740" height="261" alt="image" src="https://github.com/user-attachments/assets/568c76c8-d283-4127-8704-57d3c9d3f485" />

 

b.	In the form editor, drag and drop from left panel four components in following sequence and Save the process.

i.	H1 - Headline 1 - Enter “Approve Purchase Requisition”
ii.	Text Field - Rename title as “Supplier” and make it required on right side configuration.
iii.	Number Field - Rename title as “Quantity” and make it required on right side configuration.
iv.	Text Field - Rename title as “Total Price” and make it required on right side configuration.

 <img width="675" height="303" alt="image" src="https://github.com/user-attachments/assets/83346a27-b0e4-4604-885b-bc67ded9c604" />

 
c.	Come back to main process, select Approval Form,  
i.	On the right-hand panel under General tab, enter “Approve Purchase Requisition” as subject and map approver from Determine Approver step to Recipient users, and Save the Process

 <img width="662" height="291" alt="image" src="https://github.com/user-attachments/assets/eb9120e6-8739-42cf-afb4-7124bf9b2626" />


ii.	On the right-hand panel under Inputs tab, map following fields, and Save the process.
•	Quantity – with quantity from Trigger Form
•	Supplier – with supplier from Trigger Form
•	Total Price – with total price from Custom Variable

 <img width="645" height="280" alt="image" src="https://github.com/user-attachments/assets/dcce92ce-4dc9-4e63-8d9e-d47ede371a89" />


8.	In this step we will check our process created so far, release the process & deploy the process to test it working.

a.	Navigate to SAP Build Lobby, click on Control Tower on left hand side menu, click on Environments, click on Create, enter name as “Procurement” and click on Create.
b.	Come to the project, click on Release on right hand side and Release the project.

 <img width="719" height="282" alt="image" src="https://github.com/user-attachments/assets/36b55d0f-1978-45f7-87e3-31334a426413" />


c.	From the middle top panel select “Released” project and you will see an option to Deploy project on right-hand side. Click on Deploy, select Procurement as environment and deploy the project.

 <img width="741" height="285" alt="image" src="https://github.com/user-attachments/assets/41b8c2f8-f193-4d35-ac62-cb07721d9461" />


d.	Select Purchase Requisition process in the deployed project, 
i.	system will open up process in the new tab, click on first step Trigger, system will show 
<img width="634" height="260" alt="image" src="https://github.com/user-attachments/assets/cdbb7c41-2a98-4c6d-9d8d-0e7ba95ad932" />

 

ii.	Click on first step Trigger, copy the Form Link from right-hand side, paste the url in the new browser tab, it will open up new form instance, enter all information and submit the form to trigger the process.

 <img width="699" height="357" alt="image" src="https://github.com/user-attachments/assets/6c907164-e41d-4ae7-970c-fd78180fc59f" />


e.	Navigate to SAP Build Lobby, click on Monitoring on the left-hand side menu, click on Process & Workflow Instances tile to check status of your process.

9.	This is optional extension step to learn how to use Generative AI to explain an existing project.

a.	Navigate to SAP Build Lobby, click on Store or Templates on left-hand side menu, search for Fixed Asset Transfer Approval process, click on Create from Template and click on Create. This will create a project copy in the lobby and open it up in new tab
b.	Click on main process Fixed Asset Approval artefact

 <img width="763" height="367" alt="image" src="https://github.com/user-attachments/assets/49fd6f61-7902-44d8-bc72-12fc633fc188" />


c.	Click on Generate and select Explain this process. AI will generate the step by step summary of process to understand process details.

 <img width="768" height="661" alt="image" src="https://github.com/user-attachments/assets/4e79a0d0-f0c0-48f9-a9a0-90bbd2a57c47" />


10.	Following are optional additional steps which you may like to follow using product documentation to further enhance your process.

a.	Add an Action Project to perform operations (create, read, update, delete) in any SAP or non-SAP system. For example, call an Action project to create Purchase Requisition in SAP S/4HANA system.
b.	Add notification template to send notifications to users.
c.	Add Process Visibility to your process to create dashboard for business users and stakeholders to monitor step-by-step progress of process instances.


