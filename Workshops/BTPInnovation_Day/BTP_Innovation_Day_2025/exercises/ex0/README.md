# Purchase Order Approval Process 

In this exercise we will learn how to use Joule for Developers/Generative AI capabilities of SAP Build in Process Automation. We will use following features to create a Purchase Order Approval process:

1. Generate Process Template<br>
2. Generate Form<br>
3. Generate Script<br>
4. Generate Business Rules<br>

Note: Save work with each step just to make sure we do not lose out on any information.

## Enable Generative AI option

Login to SAP Build Lobby Navigate to Control Tower and ensure "Enable Generative AI" is enabled.
<br>![](/exercises/ex0/images/GenAI.png)

## Project Creation/Import

1. Download projects Purchase Order Approval Process.mtar from projects folder to your local directory <br>
   
2. Login to SAP Build Lobby and Click on import icon<br>
<br>![](/exercises/ex0/images/Import.png)

3.Browse for the downloaded Purchase Order Approval Process project and click on Import. This will import the project.<br>
In the interest of time, project already has predefined sub-processes and approval forms to help in the Process Variants creation in the next exercise.
<br>![](/exercises/ex0/images/Browse_Project_Import.png)

## Process Generation

In this step we will generate Purchase Order Approval process using Generative AI.

1. Click on Generate and select Process<br>
<br>![](/exercises/ex0/images/GenProc.png)

2.Enter following prompt "Generate empty Process for Purchase Requisition" and click on send icon<br>
<br>![](/exercises/ex0/images/GenProcPromt.png)

 System will create a process template and open design editor to continue designing the process<br>
 <br>![](/exercises/ex0/images/ProcTemp.png)

## Form Generation

In this step we will generate a form using Generative AI and use it as Trigger Form to start the process.

1. Click on "+" button after "Add a Trigger" step. From Smart Menu, select Form.<br>
<br>![](/exercises/ex0/images/Form.png)

2.	Enter the prompt to generate PR Submission Form "Create PR Submission Form with fields Company, Supplier, Delivery Address, Delivery Date, Payment Terms, Requested By and Department and a table with fields Item, Description, Quantity, Item Price".<br>
<br>![](/exercises/ex0/images/PRSubForm.png)

3. Once the form is generated, Click on Save.<br>
<br>![](/exercises/ex0/images/Save.png)

4. Click on Add a Trigger, select Submit a Form, choose the form which we created in the last step and Save.<br>
<br>![](/exercises/ex0/images/Trigger.png)

5. Click on ![](/exercises/ex0/images/Arrow.png) to open side process panel, select Variables, configure a process custom variable "Totalprice" (of number type) , "ApprovalStatus" (of string type) and Save the process.<br>
<br>![](/exercises/ex0/images/CustomVar.png)<br>
<br>![](/exercises/ex0/images/CustomVariables_Configure.png)

7. Because we are using PR Submission Form to Trigger the process, we will remove it from next step. Select PR Submission Form, click on three dots, click on Remove and Save the process.
<br>![](/exercises/ex0/images/RemoveForm.png)
   
## Script Generation

In this step we will write a custom script using Generative AI to calculate total price value and assign to custom variable.

1. Click on ‘+’ next to Trigger, select Script Task from smart menu,
<br>![](/exercises/ex0/images/AddScriptTask.png)

2. Click on Open Editor
<br>![](/exercises/ex0/images/OpenEditor.png)

3. Select the existing script and delete it<br>
<br>![](/exercises/ex0/images/DeleteScript.png)

3. Click on Generate, enter the following prompt <br>
``` script
Generate script that calculates totalprice by looping through each element in $.context.startEvent.items
and calculates totalprice by multiplying $.context.startEvent.items.itemPrice and $.context.startEvent.items.quantity and assign to $.context.custom.totalprice
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
"create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "adminmanager@sap.com". If supplier is 1720, it must be approved by "procurementmanager@sap.com"<br>
<b>Note: Replace email ID with valid process automation user email id(your user id shared in the beginning) for testing purpose.<br>
<br>![](/exercises/ex0/images/RulePrompt.png)<br>
<br>![](/exercises/ex0/images/DecisionTable.png)

6. Go back to Purchase Requisition tab, click on ‘+’ button after Script Task, select Decision from smart menu and select Determine Approver decision which we created in last step and save.<br>
<br>![](/exercises/ex0/images/AvailableDec.png)

7. On the right-hand side panel select Inputs, map Supplier with Supplier from PR Submission Form (Trigger) and Save the process.
<br>![](/exercises/ex0/images/MapInput.png)

## Summary

Now that you know how to use Generative AI capabilities to generate process, form, java script and business rules,  
Continue to learn Process Variants feature here- [Process Variants Exercise](../ex1/README.md)
