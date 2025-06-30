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
Exercise 1.8 [Deactivate/Activate Variant ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#deactivateactivate-variant) <br>
Exercise 1.9 [Release and Deploy the project ](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#release-and-deploy-the-project) <br>
Exercise 1.10 [Run the process](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/APAC-2025/exercises/process%20variants/readme.md#run-the-process) <br>

-  
Good luck!
  
### Save as New Project
a.	Go to Lobby link https://sap-build-day-appprocess.us10.build.cloud.sap/lobby <br>
![](images/PV_Variant_Template_Save_1.png)
b.	Locate the Process Automation type of application with name “
Variants APAC - Template” <br> <ul>
i.	Click on the arrow to Navigate <br>
ii.	Choose “Versions” tab <br>
iii.	Choose the option for Version as “Editable” <br>
iv.	Give a different project name Variants APAC– Template followed by your test user number (say for example, Variants APAC - Template01) and description if required <br>
v.	Click on “Save as New Project” <br>
vi.	A new project is saved now. </ul><br>
![](images/PV_Variant_Mgmt_Template_Save_2.png)
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
![](images/PV_APAC_Variants_3.png)
b.	Click on APAC Variants <br>
![](images/PV_Create__New_Variant_4.png)
c.	Click on “Create Variant” to create a new Process Variant <br>
![](images/PV_Create__CEO_Variant_5.png)
d.	Enter the name of the variant as “CEO Approval” and click on Create button <br>
e.	Variant with name “CEO Approval “ is created now successfully <br>

### Add Start Condition 
![](images/PV_Create_Start_Condition_6.png)
a.	Click on “Add Start Condition” and open it <br/>
![](images/PV_Create_Start_Condition_Fill_7.png)
b.	Give the condition as “projectAmount is greater than 20000” by choosing  <br><ul>
1.	projectAmount from Process input context <br>
2.	is greater than from dropdown <br>
3.	type 20000 for the actual amount to be compared <br>

              </ul>
![](images/PV_Add_Steps_Variant_8.png)
4.	Start Condition is all set now for the variant <br>

### Add Steps to Variants
![](images/PV_Choose_Steps_Variant_9.png)
a.	Click on + sign to add steps to variant <br>
b.	Choose Manager Approval Step <br>
c.	Manager Approval Step gets added <br>

![](images/PV_Chose_Proc_Step_10.png)
d.	Again press on +sign below Manager Approval Step <br>
e.	Choose “Procurement Review Subprocess” step <br>
f.	Again press on +sign below Manager Approval Step <br>
g.	Choose “CEO Approval Process” step <br>
h.	Now the “CEO Approval” Variant is created successfully <br>

### Add Step Condition 
![](images/PV_Step_Cond_11.png)
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

### Deactivate/Activate Variant
a.	Click on APAC Variants  from Overview->Artifacts <br>
b.	Click on --- at the end of “CEO Approval” Variant <br>
c.	Click on Deactivate <br>
d.	This variant becomes deactivated with status Invalid <br>
e.	Now , click on --- at the end of “CEO Approval” Variant <br>
f.	Click on Activate to activate the variant back <br>

### Release and Deploy the project 
a.	Click on Release button <br>
b.	Provide description as “Initial Version” <br>
c.	Click on Release <br>
d.	Successful project release should be shown with a “Show project version” link <br>
e.	Click on the “Show project version” link <br>
f.	Click on Deploy button <br>
g.	Choose an Environment <br>
h.	Click on Deploy <br>
i.	Created Trigger will be shown with the option to Deploy <br>
j.	Click on Deploy button again shown here <br>
k.	Project should be deployed in the Environment successfully <br>

### Run the process

## License
Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](LICENSES/Apache-2.0.txt) file.
