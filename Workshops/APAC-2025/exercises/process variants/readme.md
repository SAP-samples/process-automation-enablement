## Description

This exrercise contains the material for hands-on sessions called  "Modularize & localize processes with process variants ".

## Overview

You will learn how to :
- Create a Process Variant
- Create Start Conditions
- Create Step Conditions
- Save and Release the project
- Run the project

## Exercises
Exercise 1.1 [Save as New Project ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#save-as-new-project
) <br>
Exercise 1.2 [Create Process Variant ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#create-process-variant) <br>
Exercise 1.3 [Add Start Condition ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#add-start-condition) <br>
Exercise 1.4 [Add Steps to Variants ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#add-steps-to-variants) <br>
Exercise 1.5 [Add Step Condition ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#add-step-condition) <br>
Exercise 1.6 [Add Step Configuration](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#add-step-configuration) <br>
Exercise 1.7 [Move Priority of Variants](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#move-priority-of-variants) <br>
Exercise 1.8 [Deactivate/Activate Variant ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#deactivate-variant) <br>
Exercise 1.9 [Delete Variant](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#delete-variant) <br>
Exercise 1.10 [Release and Deploy the project ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#release-and-deploy-the-project) <br>
Exercise 1.11 [Run the process](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#run-the-process) <br>

-  
Good luck!
  
### Save as New Project
a.	Go to Lobby link https://sap-build-day-appprocess.us10.build.cloud.sap/lobby <br>
b.	Locate the Process Automation type of application with name “
Variants APAC - Template” <br> <ul>
i.	Click on the arrow to Navigate <br>
ii.	Choose “Versions” tab <br>
iii.	Choose the option for Version as “Editable” <br>
iv.	Give a different project name Variants APAC– Template followed by your test user number (say for example, Variants APAC - Template01) and description if required <br>
v.	Click on “Save as New Project” <br>
vi.	A new project is saved now. </ul><br>

c.	Locate the Process Automation type of application with name “
Variants APAC - Variant Management” <br> <ul>
i.	Click on the arrow to Navigate <br>
ii.	Choose “Versions” tab <br>
iii.	Choose the option for Version as “Editable” <br>
iv.	Give a different project name Variants APAC - Variant Management followed by your test user number (say for example, Variants APAC - Variant Management01) and description if required <br>
v.	Click on “Save as New Project” <br>
vi.	A new project is saved now. </ul><br>

### Create Process Variant 
a.	Click on your Variant Management project <br>
b.	Click on APAC Variants <br>
c.	Click on “Create Variant” to create a new Process Variant <br>
d.	Enter the name of the variant as “CEO Approval” and click on Create button <br>
e.	Variant with name “CEO Approval “ is created now successfully <br>

### Add Start Condition 
a.	Click on “Add Start Condition” and open it <br/>
b.	Give the condition as “projectAmount is greater than 20000” by choosing  <br><ul>
1.	projectAmount from Process input context <br>
2.	is greater than from dropdown <br>
3.	type 20000 for the actual amount to be compared <br>	
              </ul>

### Add Steps to Variants
a.	Click on + sign to add steps to variant <br>
b.	Choose Manager Approval Step <br>
c.	Manager Approval Step gets added <br>
d.	Again press on +sign below Manager Approval Step <br>
e.	Choose “Procurement Review Subprocess” step <br>
f.	Again press on +sign below Manager Approval Step <br>
g.	Choose “CEO Approval Process” step <br>
h.	Now the “CEO Approval” Variant is created successfully <br>

### Add Step Condition 
a.	Click on “CEO Approval Process” step <br>
b.	Click on “Step Condition” tab <br>
c.	Open Condition Editor <br>
d.	Set the step condition as “priority is equal to High” <br><ul>
i.	Choose “priority” from the Process Input Context <br>
ii.	Choose “equal to” from drop down <br>
iii.	Choose “High” from next drop down <br>
</ul> <br>
e.	Save the project

### Add Step Configuration
a.	Click on “CEO Approval Process” step <br>
b.	Click on “Step Configuration” tab <br>
c.	Click on Total Cost and choose “projectAmount” <br>
d.	Click on Project Lead and choose “projectLead” <br>
e.	Save the project <br>

### Move Priority of Variants
a.	Click on APAC Variants  from Overview->Artifacts <br>
b.	Click on --- at the end of “Procurement Approval” which has priority as 2 currently <br>
c.	Click on Move Up <br>
d.	Procurement Approval should get priority 1 now <br>
e.	Again Click on --- at the end of “Procurement Approval” which has priority as 1 currently <br>
f.	Click on Move Down<br>
g.	Procurement Approval should get priority 2 again now <br>
h.	On similar lines, you can try out Move to Top and Move to Bottom<br>

### Deactivate Variant
### Delete Variant
### Release and Deploy the project 
### Run the process

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
