## Overview
In this page we are going to cover the steps on how to use Joule for developers to create a process.
Lets take "Purchase requisition Approval" as reference process.
In this process, requestor would submit purchase requisition approval form that has details like product quantity, price etc.
Assume based on supplier, approver needs to be determined. Then the form will be sent to the approver. Approver reviews the PR form, approves or rejects the request.
If the request is approved PR shall be created in SAP S/4 HANA system.

<img width="1777" height="976" alt="image" src="https://github.com/user-attachments/assets/cbfe0dda-1a25-45fc-ad5a-9deb288770b9" />

## Process Generation
Now let us see how this process can be generated with SBPA - Joule for Developers capability.
First step would be to create a project in the tenant.
Once the project is created, go to Overview tab and click on Generate. Alternatively, you can generate the process from process editor.

<img width="547" height="402" alt="image" src="https://github.com/user-attachments/assets/07155bf4-c469-425f-bc52-f0ce5b6af633" />


Now select "Process" and provide the below prompt to generate the process.
"Please generate a purchase requisition approval process, including an approval form "Purchase requisition approval" to review this data by the manager to approve or reject. When form is approved create approved email activity. When form is rejected create rejected email activity . After approval email activity, create an action "create new purchase requisition" to create the new purchase requisition in SAP S/4 HANA after its approval"
This generates process with certain activities such as form, email and it opens up in a new tab. Please note that the process name is generated based on the prompt.
You can walk through the process to see how intelligently the process and activities in it are created. For example, when you open purchase requisition approval form
and you can check the "Total Amount" field. Based on prompt, a numeric input field is created to accept only numeric values

<img width="1078" height="583" alt="image" src="https://github.com/user-attachments/assets/4d686209-86fe-43b9-a4c8-3c99e3cb032c" />

Now we will see how the process can be enhanced such that required inputs and outputs are mapped, destinations are created, errors are fixed and process can be released and deployed.
We need to add an input form to so that the requestor can enter certain details about the requisition such as product quantity, supplier, price etc.

## Form Creation
To do this, click on "+" button after "Add a Trigger" step. From Smart Menu, select Form. 
Enter the  prompt to generate input form "create input form that has productname, quantity, price, supplier".
Once the form is generated, go to the side panel. Fill the missing details
Subject : PR Form
Users : Map to "Started By"
Create process custom variable "totalprice" ( of string type)
Save the process

<img width="612" height="557" alt="image" src="https://github.com/user-attachments/assets/913ce145-1943-4993-b876-8e3b50b71d55" />


## Script Task Generation
Right below the PR form, click on "+" icon and select Script task.
Script task will be added. Open the editor to generate the script. Remove the existing sample code.
click on "Generate" and provide the prompt "generate script that calculates totalprice by multiplying $.context.form_ProductForm_1.price 
and $.context.form_ProductForm_1.quantity and convert to string and assign to $.context.custom.totalprice"
This generates the java script code. Now choose to accept it.
Fix if there are any errors with respect to variable names. Apply to close the script task editor.
Save the process

<img width="1513" height="582" alt="image" src="https://github.com/user-attachments/assets/0f3370ef-c0e0-4fa8-9fec-e75f635f7c13" />

## Rules Generation
After script task, click on "+" to create a decision. Give the name as "Determine Approver"
When decision opens in new tab, create input parameter "Supplier" (string) and output parameter "approver" (string)
Save the decision. click Generate and provide the prompt to generate a rule "create a decision table rule with name "approver determination" to determine approver based on supplier such that if the supplier is 1710, the purchase requisition must be approved by the "adminmanager@sap.com" . If supplier is 1720, it must be approved by "procurementmanager@sap.com".
You can check how the rules are generated.
Save the decision.
Go back to process. In case if you do not see decision added to the process, add it from the smart menu after script task.
Provide 1710 as supplier value as decision input parameter
Save the process

<img width="930" height="651" alt="image" src="https://github.com/user-attachments/assets/4c10e2dc-d9f2-4439-940c-fe587bb13dda" />

## Extending the Generated Process
Move on to purchase requisition approval form. Go to general tab. Map subject to totalprice, Users to approver.
Save the process.
Move on to approved email activity. Map "To" to startedby and "Subject" to approved. Open the mail body editor and enter the mail body as "approved"
Similarly, go to rejected mail activity.  Map "To" to startedby and "Subject" to rejected. Open the mail body editor and enter the mail body as "rejected" 
Save the process.

Move on to action task "create new purchase requisition". Currently we can not either update the action task with respective action or we can not replace with valid action.
Hence this step shall be removed and a new action shall be selected from action library(Eg: Create Purchase Requisition).
After the action task is added, fill in required inputs, provide destinations, save the process.
Now the process shall be ready to release, deploy and execute.

## More AI features
As the process is generated and if you would like to explain the process to a colleague, you can go to "generate" option in the process editor. Select "Explain this process"
This will generate the process summary.
Similarly, a datatype can be generated from overview tab by providing prompt "Generate datatype for supplier details".
In addition to script generation, script editor supports removal of third party packages from script. This feature would be useful when processes are fetched from other modelling tools to SBPA
You can downgrade the script to ECMA 5.1 version.

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.











