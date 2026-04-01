# Purchase Order Approval Process 

In this exercise we will learn how to use Joule for Developers/Generative AI capabilities of SAP Build in Process Automation.<br>

Pre-requisites <br>
1.[How to Login](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#details-of-tenant-and-login)<br>
2.[Save as New Project](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#project-creation-by-save-as-new-project)


We will use following features to create a Purchase Order Approval process:

1. [Generate Process Template](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#process-generation)<br>
2. [Generate Data Type](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#data-type-generation)<br>
3. [Generate Form](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#form-generation)<br>
4. [Generate Script](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#script-generation)<br>
5. [Generate Business Rules](https://github.com/SAP-samples/teched2025-AD168/blob/main/exercises/ex0/README.md#rules-generation)<br>

Note: Save work with each step just to make sure we do not lose out on any information.

## Details of tenant and login
<ul>
<li>Lobby URL - https://ad168-skhq09xc.eu10.build.cloud.sap/lobby <br>
<li>Sign in with tdct3ched1.accounts.ondemand.com and not the Default Identity Provider <br>
  <li> User id - AD168-XXX@education.cloud.sap  <br>
  <li> Password - TechEd25onTour! <br>
<li>Replace XXX with your user number, say for example your number is given as 001, it will be AD168-001 and so on..<br>
</ul>

## Project Creation by Save as New Project

1.Locate the project "Purchase Order Approval Process" <br>
Click on Versions tab and choose Editable and click on ... and do "Save as New Project"
<br>![](/exercises/ex0/images/SaveAsNewProject.png)
2. Give the name as "Purchase Order Approval Process XXX" where XXX is your user id
<br>![](/exercises/ex0/images/SaveAsNewProject_User_name.png) <br>
3. Open the newly created project in a new tab and follow the next steps.

 ## Process Generation

In this step we will generate Purchase Order Approval process using Generative AI.

1. Click on the imported Purchase Order Approval process project<br>
2. Click on Generate and select Process<br>
<br>![](/exercises/ex0/images/GenProc.png)

3.Enter following prompt "Generate empty Process for Purchase Requisition" and click on send icon<br>
<br>![](/exercises/ex0/images/GenProcPromt.png)

 System will create a process template and open design editor to continue designing the process<br> 

## Data Type Generation
In this step we will generate Data Type for Items as a list using Generative AI.
1.  Go Back to "Overview" tab, click on Generate and select Datatype<br>
<br>![](/exercises/ex0/images/Generate_DT.png)
2. Enter the prompt to generate Items Datatype as "Generate Data Type named "Items" of type list with fields Item of type string, Description of type string, Quantity of type number, ItemPrice of type number"
<br>![](/exercises/ex0/images/DT_Prompt.png)
3. Items Data type gets generated as below
   <br>![](/exercises/ex0/images/Items_DT.png)

## Form Generation

In this step we will generate a form using Generative AI and use it as Trigger Form to start the process.

1. Go Back to "Purchase Requision Process" tab, click on "+" button after "Add a Trigger" step. From Smart Menu, select Form.<br>
<br>![](/exercises/ex0/images/Form.png)

2.	Enter the prompt to generate PR Submission Form "Create PR Submission Form with fields Company, Supplier, Delivery Address, Delivery Date, Payment Terms, Requested By and Department and a table with fields Item, Description, Quantity, ItemPrice".<br>
<br>![](/exercises/ex0/images/PRSubForm.png)

3. Once the form is generated, enter the Subject:"PR Submission Form" and map the Recipients users to "Started By" in the process Metadata  <br>![](/exercises/ex0/images/Fill_Form_Mandatory_Params.png) 
4. Click on Save.<br>
<br>![](/exercises/ex0/images/Save.png)
5. Click anywhere on the canvas and then click on ![](/exercises/ex0/images/Arrow.png) to open side process panel, select Variables and click on Configure for Process Input Variables.
   <br>![](/exercises/ex0/images/CustomVar.png)<br>
6. Click on Add Input and add the following attributes of appropriate type(String, Date, Items) and mark as required. The "Item" attribute should be mark also as list. As shown below.   
<br>![](/exercises/ex0/images/Configure_Process_Inputs.png) 
7. Click on Add a Trigger, select API Trigger, give it a name "Purchase Order Process Trigger" and click on Create.<br>
<br>![](/exercises/ex0/images/API_Trigger.png)
<br>![](/exercises/ex0/images/Create_API_Trigger.png)
   
8.  Click anywhere on the canvas and then click on ![](/exercises/ex0/images/Arrow.png) to open side process panel, select Variables, configure process custom variables "Totalprice" (of number type) , "ApprovalStatus" (of string type) click on apply and Save the process.<br>
<br>![](/exercises/ex0/images/CustomVar.png)<br>
<br>![](/exercises/ex0/images/CustomVariables_Configure.png)

9. Click on PR Submission Form and Click on Inputs tab. Map all the attributes from Process Inputs<br>
Company, Delivery Address, Delivery Date, Department, Items, Payment Terms, Requested By, Supplier<br>
<br>![](/exercises/ex0/images/MapInput_Variables.png)

   
## Script Generation

In this step we will write a custom script using Generative AI to calculate total price value and assign to custom variable.

1. Click on ‘+’ next to PR Submission Form, select Script Task from smart menu,
<br>![](/exercises/ex0/images/AddScriptTask.png)

2. Click on Open Editor
3. Select the existing script and delete it<br>
<br>![](/exercises/ex0/images/OpenEditor.png)

4. Click on Generate, enter the following prompt <br>
``` script
Generate script that calculates totalprice by looping through each element in $.context.startEvent.items
and calculates totalprice by multiplying $.context.startEvent.items.ItemPrice and $.context.startEvent.items.Quantity and assign to $.context.custom.totalprice
``` 
<br>![](/exercises/ex0/images/GenScript.png)

4. System will generate script, check if script is fine, Accept it, Validate Script, Apply and Save Process.<br>
<br>![](/exercises/ex0/images/Script.png)

 ## Rules Generation
 
 In this step we will create a business rule using Generative AI to dynamically determine approvers of purchase requisitions.

 1. After script task, click on "+", select Decision from smart menu<br>
 <br>![](/exercises/ex0/images/Decision.png)
   
 2. Click on Blank Decision<br>
 <br>![](/exercises/ex0/images/BlankDec.png) 
   
 3. Give the name as "Determine Approver" and click on Create.<BR>
 <br>![](/exercises/ex0/images/CreateDec.png)

 4. Decision will be opened in a new tab, from right side panel create input parameter "Supplier" (string) , output parameter "Approver" (string) and Save the Process.
 <br>![](/exercises/ex0/images/DeterApp.png)
 
 5. Click on Generate, select Generate Rule, enter the following prompt and Save Process:
"create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "ad168-xxx@education.cloud.sap". If supplier is 1720, it must be approved by "ad168-xxx@education.cloud.sap"<br>
<b>Note: Replace email ID with valid process automation user email id enclosed within single quotes(your user id shared in the beginning in small letters) for testing purpose.<br>
<br>![](/exercises/ex0/images/RulePrompt.png)<br>
<br>![](/exercises/ex0/images/DecisionTable.png)

6. Go to "Purchase Requisition Process" tab, click on ‘+’ button after Script Task, select Decision from smart menu and select "Determine Approver" decision which we created in last step and save.<br>
<br>![](/exercises/ex0/images/AvailableDec.png)

7. On the right-hand side panel select Inputs, map Supplier with Supplier from PR Submission Form and Save the process.
<br>![](/exercises/ex0/images/MapInput.png) 

## Summary

Now that you know how to use Generative AI capabilities to generate process, form, java script and business rules,  
Continue to learn Process Variants feature here- [Process Variants Exercise](../ex1/README.md)
