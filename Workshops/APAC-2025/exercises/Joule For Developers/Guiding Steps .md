## Artificial Intelligence in SAP Build Process Automation
In this exercise we will learn how to use Joule for Developers capabilities of SAP Build in Process Automation. 
We will use following features to create a sample Purchase Requisition Approval process: 
  a)Generate Process Template 
  b)Generate Form 
  c)Generate Script 
  d)Generate Business Rules 
  e)Generate Datatype

In this process, requestor would submit purchase requisition approval form that has details like product quantity, price etc.
Assume based on supplier, approver needs to be determined. Then the form will be sent to the approver. Approver reviews the PR form, approves or rejects the request.
If the request is approved PR shall be created in SAP S/4 HANA system.

<img width="1777" height="976" alt="image" src="https://github.com/user-attachments/assets/cbfe0dda-1a25-45fc-ad5a-9deb288770b9" />


## Enable Generative AI option
Login to SAP Build Lobby 
Navigate to Control Tower and ensure "Enable Generative AI" is enabled.

<img width="1357" height="626" alt="image" src="https://github.com/user-attachments/assets/747025d6-95e1-461d-960d-07511187fbba" />

## Project Creation
1.	Login to SAP Build Lobby and Click on Process Automation
    <img width="1557" height="433" alt="image" src="https://github.com/user-attachments/assets/000de787-4632-41c9-ab75-4c2c06b1e426" />

2.	Enter project Name & Description and click Create
    <img width="1137" height="560" alt="image" src="https://github.com/user-attachments/assets/ee01e289-0395-4d30-a346-feeba1845883" />
This will create a project with given name & description.

## Process Generation
Now let us see how Purchase Requisition Approval process template can be generated .
1. Go to Overview tab and click on Generate (Alternatively, you can generate the process from process editor)

<img width="547" height="402" alt="image" src="https://github.com/user-attachments/assets/07155bf4-c469-425f-bc52-f0ce5b6af633" />


2. Now select "Process" and provide the below prompt to generate the process and click on <img width="26" height="24" alt="image" src="https://github.com/user-attachments/assets/a6443fdf-55fe-4098-b709-99398d948520" /> send icon 

"Please generate a purchase requisition approval process, including an approval form "Purchase requisition approval" to review this data by the manager to approve or reject. When form is approved create approved email activity. When form is rejected create rejected email activity . After approval email activity, create an action "create new purchase requisition" to create the new purchase requisition in SAP S/4 HANA after its approval"
3. This generates process with certain activities such as form, email and it opens up in a new tab. Please note that the process name is generated based on the prompt.
4. You can walk through the process to see how intelligently the process and activities in it are created. For example, when you open purchase requisition approval form
and you can check the "Total Amount" field. Based on prompt, a numeric input field is created to accept only numeric values

<img width="1078" height="583" alt="image" src="https://github.com/user-attachments/assets/4d686209-86fe-43b9-a4c8-3c99e3cb032c" />

5. Now we will see how the process can be enhanced such that required inputs and outputs are mapped, destinations are created, errors are fixed and process can be released and deployed.
6. We need to add an input form to so that the requestor can enter certain details about the requisition such as product quantity, supplier, price etc.

## Form Creation
1. To do this, click on "+" button after "Add a Trigger" step. From Smart Menu, select Form. 
2. Enter the  prompt to generate input form "create input form that has productname, quantity, price, supplier".
3.Once the form is generated, go to the side panel by clicking on . Fill the missing details
   a)Subject : PR Form
   b)Users : Map to "Started By"
   c)Select Variables, configure a process custom variable "totalprice" (of string type) and Save the process.
  Note:  Save work with each step just to make sure we do not lose out on any information

<img width="612" height="557" alt="image" src="https://github.com/user-attachments/assets/913ce145-1943-4993-b876-8e3b50b71d55" />


## Script Task Generation
1. Right below the PR form, click on "+" icon and select Script task.
2. Script task will be added. Open the editor to generate the script. Remove the existing sample code.
3. Click on "Generate" and provide the prompt "generate script that calculates totalprice by multiplying $.context.form_ProductForm_1.price 
 and  $.context.form_ProductForm_1.quantity and convert to string and assign to $.context.custom.totalprice"
4. This generates the java script code. Now choose to accept it.
5. Fix if there are any errors with respect to variable names. Apply to close the script task editor.
6. Save the process

<img width="1513" height="582" alt="image" src="https://github.com/user-attachments/assets/0f3370ef-c0e0-4fa8-9fec-e75f635f7c13" />

## Rules Generation
1. After script task, click on "+" to create a decision. Give the name as "Determine Approver".
2. When decision opens in new tab, create input parameter "Supplier" (string) and output parameter "approver" (string).
3. Save the decision. click Generate and provide the prompt to generate a rule "create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "adminmanager@sap.com" . If supplier is 1720, it must be approved by "procurementmanager@sap.com".
4. You can check how the rules are generated.
5. Save the decision.
6. Go back to process. In case if you do not see decision added to the process, add it from the smart menu after script task.
7. Provide 1710 as supplier value as decision input parameter.
8. Save the process.

<img width="930" height="651" alt="image" src="https://github.com/user-attachments/assets/4c10e2dc-d9f2-4439-940c-fe587bb13dda" />

## Extending the Generated Process
1. Move on to purchase requisition approval form. Go to general tab. Map subject to totalprice, Users to approver.
2. Save the process.
3. Move on to approved email activity. Map "To" to startedby and "Subject" to approved. Open the mail body editor and enter the mail body as "approved"
4. Similarly, go to rejected mail activity.  Map "To" to startedby and "Subject" to rejected. Open the mail body editor and enter the mail body as "rejected" 
5. Save the process.
6. Move on to action task "create new purchase requisition". Currently we can not either update the action task with respective action or we can not replace with valid action.
7. Hence this step shall be removed and a new action shall be selected from action library(Eg: Create Purchase Requisition).
8. After the action task is added, fill in required inputs, provide destinations, save the process.
9. Now the process shall be ready to release, deploy and execute.

## More AI features
1. As the process is generated and if you would like to explain the process to a colleague, you can go to "Generate" option in the process editor. Select "Explain this process". This will generate the process summary.
2. Similarly, a datatype can be generated from overview tab by providing prompt "Generate datatype for supplier details".
3. In addition to script generation, script editor supports removal of third party packages from script. This feature would be useful when processes are fetched from other modelling tools to SBPA. You can downgrade the script to ECMA 5.1 version.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.











