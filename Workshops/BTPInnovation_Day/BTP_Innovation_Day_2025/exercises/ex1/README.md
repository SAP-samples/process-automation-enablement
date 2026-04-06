# Purchase Order Approval - Process Variants

In this exercise, we will learn how to create different Process Variants for the Purchase Order Approval Process in :<br>

1. Variant Template Editor - Template developer is usually a pro developer and creates the variant template, the default variant.<br>

2. Variant Management Editor - Variant user - usually a business configuration expert - accesses the variant management editor and creates and defines the order of the variants<br>

Process Variants capability enables a business configuration expert to configure the m different steps out of the total n steps as per the business requirements.<br>

A process developer defines all the different steps that can be part of a process in a process variant template , releases and publishes the project called as Template project.<br>

This template project is added as a business object dependency to another project named as Configuration project wherein business configuration expert can create different variants , change the priority of variants , activate a variant, deactivate a variant , delete a variant and so on.
Say, for example, in this exercise, we will let the Business configuration expert create 2 variants, one with 2 levels of approvals and another one with 3 levels of approvals out of 5 steps which are available as released by a process developer in the template project<br>

Based on start conditions defined, appropriate process variant will be started.<br>

## Create Process Variant Template 

1. Click on "Purchase Requisition Process" an open <br>
2. Click on + after "Determine Approver" and choose Variant Template 
<br>![](/exercises/ex1/images/PV_Create.png)
3. Give name as "Purchase Order Variant Template" and Save <br>
4. Click on "Open Editor"<br>
<br>![](/exercises/ex1/images/Open_Variant_Editor.png) 
5. Click on "Add Steps" and add all the available steps one by one.
<br>![](/exercises/ex1/images/Add_Steps.png) <br>
6.After adding each step,  click on the added step, go to "Inputs" tab and map all the available attributes from "Company" to "Supplier" from PR Submission Form and "Totalprice" from Custom Variables.
<br>![](/exercises/ex1/images/Map_Step_Attributes.png) <br>
Go to "Variant" and add Step Input "Approver"
<br>![](/exercises/ex1/images/StepInput.png) <br>
 
Repeat this for all steps except Send Notification step.<br>
7.Steps available in Variant Editor will look as below:
<br>![](/exercises/ex1/images/Available_Steps.png)
8.Click on "Add Default Variant" in the General tab and Create a new one with name "Default Variant" which will act as a fallback if no other variant is created or no other start condition is met
<br>![](/exercises/ex1/images/Default_Variant.png)
9.Click on + after the Process and add Variant Steps to Default Variant
<br>![](/exercises/ex1/images/Add_Default_Variant.png)
10.Add Department Approval Process step to the Default Variant
<br>![](/exercises/ex1/images/Add_Dept_Default_Variant.png)
11.Click on + after the  Department Approval Process , click on Controls and Events and add Branch called "Parallel Branch" to Default Variant
<br>![](/exercises/ex1/images/Add_Parallel_Branch.png),
<br>Parallel branches are created so that 2 or more steps can execute simlataneously. But all the parallel branches have to be completed before next step can proceed though.<br>
12.Add Steps Finance Approval Process and Legal Department Approval Process as parallel branches , if they are not visible, click on "Show All" to see all the processes that are available.
<br>![](/exercises/ex1/images/Add_Fin_Legal_Parallel_Branch.png)
13.Click on + and Add Step Procurement Approval Process. Default Variant finally will look like below:
<br>![](/exercises/ex1/images/Final_Default_Variant.png)
14.Save the Default Variant and click on Back to go back to the leading "Purchase Requisition" process <br>
15.Click on "Purchase Order Variant Template" and go to Variables tab and add attributes
<br>![](/exercises/ex1/images/Add_Variables.png)
16.Add all the attributes from the process context - Both Process Inputs and Custom variables.
<br>![](/exercises/ex1/images/Add_Attributes.png)
    1. ApprovalStatus  (From the custom variables) <br>
    2. Totalprice (From the custom variables)<br>
    3. Approver<br> (From the decision)<br>
    4. Company<br>
    5. DeliveryAddress<br>
    6. DeliveryDate<br>
    7. Department<br>
    8. PaymentTerms<br>
    9. RequestedBy<br>
    10. Supplier<br>
17.Create 2 Global outcomes, one for approved status and one for rejected status. Global outcomes are the overall outcome of a process variant<br>
18.Create a global outcome if overall approval status of all the steps in the variant is "Approved"  <br>
<br>![](/exercises/ex1/images/Approved_outcome.png)<br>
<br>![](/exercises/ex1/images/Approved_outcome_condition.png)<br>
19.Create another global outcome if overall approval status of all the steps in the variant is "Rejected"  <br>
<br>![](/exercises/ex1/images/Rejected_Outcome.png)<br>
<br>![](/exercises/ex1/images/Rejected_Outcome_Condition.png)<br>
20.Now,2 global outcomes depending on the approval status(Approved,Rejected) as condition are created
<br>![](/exercises/ex1/images/Global_Outcomes.png)
        
## Create Process Variant Management

1.Release "Purchase Order Approval Process" project
<br>![](/exercises/ex1/images/Release_Project.png)
2.Go to Lobby and choose the latest released version of the project "Purchase Order Approval Process.<br>
3.Do a Publish  to Library of the project so that it can be added as dependency to the Variant Management project which we will be creating now
<br>![](/exercises/ex1/images/Publish_To_Library.png)
4.Create a Process Automation project in lobby named "Purchase Order Approval - Process Variants AD168_XXX" where XXX is your user name.
<br>![](/exercises/ex1/images/Create_SBPA_Project.png)
5.Click and go inside the project.<br>
6.Add Business Process Project Dependency to "Purchase Order Approval Process" by going to Settings->Dependencies->Add a Business Process Project Dependency->Project.
<br>![](/exercises/ex1/images/Add_Dependency.png)
<br>![](/exercises/ex1/images/Add_Dependency_Project.png)
7.Create a Variant management artifact "Purchase Order Variants"
<br>![](/exercises/ex1/images/Variant_Mgmt.png)
<br>![](/exercises/ex1/images/VarMan.png)

Default Variant created in the Process Template will automatically appear here. 

<br>![](/exercises/ex1/images/DefultVar.png)
8.Now, more variants can be created by the Business user.Create a variant named "Two level approval" by clicking on Create Variant <br>
<br>![](/exercises/ex1/images/Create_Variant.png)
9.Add Start Condition by clicking on "Add Start Condition" and giving condition as "Totalprice is less than 10000"
<br>![](/exercises/ex1/images/Two_Levels_Start_Condition.png)
10.Click on + after Start condition and choose Variant Steps.<br>
  Add 2 levels of approvals, "Department Approval Process" and "Procurement Approval Process"
<br>![](/exercises/ex1/images/Add_2_levels.png)
11.Click on "Department Approval Procees" go to "Step Configuration" and map the "Approver" to the "Approver" from Process Inputs. Repete this step for "Procurement Approval Process" 
<br>![](/exercises/ex1/images/StepConf.png)

12) Go to "Purchase Order Variants" Create another variant named "Three level approvals" by clicking on Create Variant <br>
<br>![](/exercises/ex1/images/ThreeLev.png)
13) Add 3 levels of approvals, "Department Approval Process", "Finance Approval Process" and "Procurement Approval Process"
<br>![](/exercises/ex1/images/Three_Levels_Approvals.png)

14.Click on "Department Approval Procees" go to "Step Configuration" and map the "Approver" to the "Approver" from Process Inputs. Repete this step for "Procurement Approval Process" and "Finance Approval Process".

15.Add Start Condition by clicking on "Add Start Condition" and giving condition as "Totalprice is greater than 10000" and "Totalprice is less than 50000" press "Apply" and save.
<br>![](/exercises/ex1/images/Three_levels_Start_Condition.png)
16.Go to Purchase Order Variant" tab, change the order of the variants by clicking on three dots (...) at the end of variant "Two level approvals" and click on Move Down or Move to Bottom.
<br>![](/exercises/ex1/images/Change_Order_Variants.png)
17.Order/Priority is changed now. "Three levels of approvals" moves to the top.
<br>![](/exercises/ex1/images/Order_Change.png)
18.Deactivate variant by clicking on three dots (...) at the end of variant "Two level approvals" and click on Deactivate.Status of the variant becomes inactive. 
<br>![](/exercises/ex1/images/Deactivate_Variant.png)
<br>![](/exercises/ex1/images/Inactive_Variant.png)
19.Activate the variant back by clicking on three dots (...) at the end of variant "Two level approvals" and click on Activate. Status of the variant becomes valid again. 
<br>![](/exercises/ex1/images/Activate_Variant.png)
20.A variant can be deleted as well by clicking on "Delete".<br>
21.Release the variants.<br>
<br>![](/exercises/ex1/images/ReleaseVar.png)<br>
<br>![](/exercises/ex1/images/ShowProVer.png)<br>

## Summary

You've now learnt to work with Process Variants in SAP Build Process Automation

Continue to - [Deploy and Run Process(Variants)](../ex2/README.md)

