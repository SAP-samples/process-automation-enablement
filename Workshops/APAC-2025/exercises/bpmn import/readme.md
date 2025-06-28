## Description

This exrercise contains the material for hands-on sessions called "Create processes from BPMN models".

## Overview

You will learn how to :
- Generate a process in SBPA given the BPMN file from Signavio as input
- Do the necessary manual configuration to replave the placeholders for actual SBPA form, approval forms, subprocess
- Adjust the script task, mail task
- Save , Release and Deploy the project
- Run the project
  
## Exercises

Exercise 1.1 [Save as New Project ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/bpmn%20import/readme.md#save-as-new-project) <br>
Exercise 1.2 [Import BPMN file to generate process](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#import-bpmn-file-to-generate-process
) <br>
Exercise 1.3 [Adjust the Configurations in the process](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#adjust-the-configurations-in-the-process
) <br>
Exercise 1.4 [Replace the placeholder for “Get Procurement Approver” with SBPA subprocess](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#replace-the-placeholder-for-get-procurement-approver-with-sbpa-subprocess) <br>
Exercise 1.5 [Replace the placeholder for “Procurement Review Approval” with SBPA approval form](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#replace-the-placeholder-for-procurement-review-approval-with-sbpa-approval-form) <br>
Exercise 1.6 [Replace the placeholder for “Finance Review” with SBPA approval form](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#replace-the-placeholder-for-finance-review-with-sbpa-approval-form) <br>
Exercise 1.7 [Replace the placeholder for “CEO Approval” with SBPA approval form](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#replace-the-placeholder-for-ceo-approval-with-sbpa-approval-form) <br>
Exercise 1.8 [Adjust the Mail task  “CapEx Approval Status Mail”](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#adjust-the-mail-task--capex-approval-status-mail) <br>
Exercise 1.9 [Add a trigger](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#add-a-trigger) <br>
Exercise 1.10 [Release and Deploy the project](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#release-and-deploy-the-project) <br>
Exercise 1.11 [Run the proce](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/APAC-2025/exercises/bpmn%20import#run-the-process) <br>
  
Good luck!
  
### Save as New Project

a.	Go to [Lobby link](https://sap-build-day-appprocess.us10.build.cloud.sap/lobby) <br>
b.	Locate the Process Automation type of application with name “ BPMN Import - APAC Template” <br/>
 <ul>
   i.	Click on the arrow to Navigate <br/>
   ii.	Choose “Versions” tab <br/>
   iii.	Choose the option for Version as “Editable” <br/>
   iv.	Give a different project name BPMN Import - APAC Template followed by your test user number (say for example, BPMN    Import - APAC Template 01) and description if required <br/>
   v.	Click on “Save as New Project” <br/>
  </ul>
A new project is saved now. <br/>

### Import BPMN file to generate process
  a.	Click on your project <br/>
  b.	Click on Import->BPMN Process <br/>
  c.	Browse for the BPMN file and choose it <br/>
  d.	Click on Import <br/>
  e.	Check the warnings and choose Confirm <br/>
  f.	Message that “BPMN Process Imported Successfully” will come up <br/>
  g.	Process named “CapEx_Process” will be generated <br/>

### Adjust the Configurations in the process
a.	Click on “CapEx_Process” and open it <br/>
b.	Replace the placeholder for “Create Request” with SBPA form <br/>
<ul>
i.	Click on “Create Request” placeholder <br/>
ii.	Click on “Replace with Form” <br/>
iii.	Choose “Create Request Form” from Available Forms(Hint: You can create a form from scratch using Blank Form if there are no available forms) <br/>
iv.	Now the placeholder is replaced with actual form .You can click on “Open Editor” to check the content of the form  <br/>
v.	Click on General tab and <br/>
<ul>
1.	Click on Subject and enter “Request Form” <br/>
2.	Click on User and choose Process Metadata->Started By <br/>
</ul>
vi.	Save the project <br/>
</ul>
c.	Adjust the script task “Calculate Total Price of Items”
i.	Click on “Calculate Total Price of Items” placeholder <br/>
ii.	On the right hand side, replace the code with the below one to make it a valid script <br/>
<ul>
1.	$.context.custom.totalProcurementCost = 0; <br>
2.	var itemsList = $.context.form_createRequestForm_1.lineItemSection; <br>

3.	for (var i = 0; i < $.context.form_createRequestForm_1.lineItemSection.length; i++) { <br>

4.	    $.context.custom.totalProcurementCost += itemsList[i].cost ; <br>
5.	
6.	}<br>
7.	$.context.custom.taxAmount = $.context.custom.totalProcurementCost * 0.05; <br>

8.	$.context.custom.totalProcurementCost += $.context.custom.taxAmount; <br>

</ul>
iii.	Click on Apply  <br>
iv.	Script task is valid and ready now <br>

### Replace the placeholder for “Get Procurement Approver” with SBPA subprocess
### Replace the placeholder for “Procurement Review Approval” with SBPA approval form
### Replace the placeholder for “Finance Review” with SBPA approval form
### Replace the placeholder for “CEO Approval” with SBPA approval form
### Adjust the Mail task  “CapEx Approval Status Mail”
### Add a trigger 
### Release and Deploy the project 
### Run the process
## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
