## Artificial Intelligence in SAP Build Process Automation
In this exercise we will learn how to use Joule for Developers capabilities of SAP Build in Process Automation. We will use following features to create a sample Purchase Requisition Approval process: a)Generate Process Template b)Generate Form c)Generate Script d)Generate Business Rules e)Generate Datatype

## Enable Generative AI option
Login to SAP Build Lobby Navigate to Control Tower and ensure "Enable Generative AI" is enabled.

<img width="1357" height="626" alt="image" src="https://github.com/user-attachments/assets/edd25cc4-469a-4430-a422-d15484004156" />

## Project Creation
1. Login to SAP Build Lobby and Click on Process Automation

<img width="1557" height="433" alt="image" src="https://github.com/user-attachments/assets/dae4e689-9941-40e5-9549-9d1e27335d3e" />

2. Enter project Name & Description and click Create. This will create a project with given name & description.

<img width="1137" height="560" alt="image" src="https://github.com/user-attachments/assets/ee027f05-6dc4-4e64-83c5-f2d25d521720" />

## Process Generation
3.	In this step we will generate Purchase Requisition Approval process template using Generative AI.  

a.	Click on Generate and select Process

 

b.	Enter following prompt Generate an empty process template called “Purchase Requisition” with an approval form and click on send icon   . System will create a process template and open design editor to continue designing the process.
 

4.	In this step we will generate a form using Generative AI and use it as Trigger Form to start the process.

a.	click on "+" button after "Add a Trigger" step. From Smart Menu, select Form. 

 

b.	Enter the prompt to generate input form "create input form that has product name, quantity, price, supplier".  Click on Save

 


c.	Once the form is generated, Click on Save 
 

d.	Click on Add a Trigger, select Submit a Form, choose the form which we created in the last step and Save.

 

Note:  Save work with each step just to make sure we do not lose out on any information.

e.	Click on   to open side process panel, select Variables, configure a process custom variable "totalprice" (of string type) and Save the process.

 

 

f.	Because we are using Product Information Form to Trigger the process, we will remove it from next step. Select Product Information Form, click on three dots, click on Remove and Save the process.

 
5.	In this step we will write a custom script using Generative AI to calculate total price value and assign to custom variable.

a.	Click on ‘+’ next to Trigger, select Script Task from smart menu, 

 

Click on Open Editor, select all existing content and delete it

 

b.	Click on Generate, enter the following prompt “generate script that calculates totalprice by multiplying $.context.startEvent.price and  $.context.startEvent.quantity and convert to string and assign to $.context.custom.totalprice”

System will generate script, check if script is fine, Accept it, Validate Script, Apply and Save Process.

 

6.	In this step we will create a business rule using Generative AI to dynamically determine approvers of purchase requisitions.

a.	After script task, click on "+", select Decision from smart menu, click on Blank Decision, give the name as "Determine Approver" and click on Create.
 

b.	Decision will open in a new tab, from right side panel create input parameter "Supplier" (string) , output parameter "approver" (string) and Save the Process.

 

c.	Click on Generate, select Generate Rule, and give following prompt and Save Process – 

create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "adminmanager@sap.com". If supplier is 1720, it must be approved by "procurementmanager@sap.com”

Note: Replace email ID with valid process automation user email id for testing purpose.

	 

d.	Go back to Purchase Requisition process tab, in case you do not see decision added, click on ‘+’ button after Script Task, select Decision from smart menu and select Determine Approver decision which we created in last step.

 


e.	Select Determine Approver decision in main process, on the right-hand side panel select Inputs, map it with Supplier information from coming from Trigger form and Save the process.

 

7.	In the step we will modify Approval Form and map it with input field & calculated variables.

a.	Click on three dots next to Approval Form and click on Open Editor.

 

b.	In the form editor, drag and drop from left panel four components in following sequence and Save the process.

i.	H1 - Headline 1 - Enter “Approve Purchase Requisition”
ii.	Text Field - Rename title as “Supplier” and make it required on right side configuration.
iii.	Number Field - Rename title as “Quantity” and make it required on right side configuration.
iv.	Text Field - Rename title as “Total Price” and make it required on right side configuration.

 
 
c.	Come back to main process, select Approval Form,  
i.	On the right-hand panel under General tab, enter “Approve Purchase Requisition” as subject and map approver from Determine Approver step to Recipient users, and Save the Process

 

ii.	On the right-hand panel under Inputs tab, map following fields, and Save the process.
•	Quantity – with quantity from Trigger Form
•	Supplier – with supplier from Trigger Form
•	Total Price – with total price from Custom Variable

 

8.	In this step we will check our process created so far, release the process & deploy the process to test it working.

a.	Navigate to SAP Build Lobby, click on Control Tower on left hand side menu, click on Environments, click on Create, enter name as “Procurement” and click on Create.
b.	Come to the project, click on Release on right hand side and Release the project.

 

c.	From the middle top panel select “Released” project and you will see an option to Deploy project on right-hand side. Click on Deploy, select Procurement as environment and deploy the project.

 

d.	Select Purchase Requisition process in the deployed project, 
i.	system will open up process in the new tab, click on first step Trigger, system will show 

 

ii.	Click on first step Trigger, copy the Form Link from right-hand side, paste the url in the new browser tab, it will open up new form instance, enter all information and submit the form to trigger the process.

 

e.	Navigate to SAP Build Lobby, click on Monitoring on the left-hand side menu, click on Process & Workflow Instances tile to check status of your process.

9.	This is optional extension step to learn how to use Generative AI to explain an existing project.

a.	Navigate to SAP Build Lobby, click on Store or Templates on left-hand side menu, search for Fixed Asset Transfer Approval process, click on Create from Template and click on Create. This will create a project copy in the lobby and open it up in new tab
b.	Click on main process Fixed Asset Approval artefact

 

c.	Click on Generate and select Explain this process. AI will generate the step by step summary of process to understand process details.

 





10.	Following are optional additional steps which you may like to follow using product documentation to further enhance your process.

a.	Add an Action Project to perform operations (create, read, update, delete) in any SAP or non-SAP system. For example, call an Action project to create Purchase Requisition in SAP S/4HANA system.
b.	Add notification template to send notifications to users.
c.	Add Process Visibility to your process to create dashboard for business users and stakeholders to monitor step-by-step progress of process instances.


