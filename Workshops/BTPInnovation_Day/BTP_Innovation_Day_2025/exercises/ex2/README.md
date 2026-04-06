# Deploy and Run Process(Variants)
In this exercise, we will learn how to Deploy and Run the process. If process variants are modelled, depending on the start condition, one of the process variant will be triggered and if the start condition does not match any of the variants, the default variant will be triggered as fallback.

## Release and Deploy the project

After completing these steps you will have to release and deploy the project.

1. Create an Environment with name of your user id prefixed by Env (for example , if your userid is user001, then create an Environment with name Envuser001)
<br>![](/exercises/ex2/images/Env1.png)
<br>![](/exercises/ex2/images/Env2.png)
2.	Deploy the template project to your Environment that you just now created.
   <br>![](/exercises/ex2/images/Deploy_Template_Project.png)
  	Deployment succeessful message should appear<br>
4. Deploy the Variant project  to your Environment that you just now created.
   <br>![](/exercises/ex2/images/Deploy_PO_Approval_PV.png)
   Deployment succeessful message should appear<br>
  
## Run the Process 

After completing these steps you will learn how to trigger a process which triggers appropriate variant if configured.
If there are no variants configured, the process just runs all the steps configured in it.

1.	Click on Control Tower-> Environemnts tab and the Environnment you created in the previous step.
<br>![](/exercises/ex2/images/ClickEnv.png)
2. Click on More->Processes and Workflows or if you are seeing directly Processes and Workflows, click on that <br>
3. Click on Search and give "Purchase Req"<br>
4.Choose the latest version of "Purchase Requisition Process"<br>
5.Click on Start New Instance<br>
<br>![](/exercises/ex2/images/Start_New_instance.png)
6.Provide the payload , sample payload below :<br>
``` Payload
 {
        "company": "SAP",
        "supplier": "1710",
        "deliveryAddress": "SAP",
        "deliveryDate": "2025-10-06",
        "paymentTerms": "Credit",
        "requestedBy": "SAP BTP",
        "department": "BTP",
        "items": [
                {
                "Item": "Laptop",
                "Description": "Laptop",
                "Quantity": 100,
                "ItemPrice": 80
            }            
        ]
    }

``` 
7. Click on "Start New Instance and Close "<br>
8. Click on Show Instances<br>
9. Click on Running instance and you can see that a Task "PR Submission Form" is available<br>
10.This form will be available in the My Inbox, click on My Inbox icon to see this task and further tasks.
   <br>![](/exercises/ex2/images/Running_instance.png)
11.Enter the details in PR Submission Form with data given below :
   <br>![](/exercises/ex2/images/PR_Sub_Form.png)
12.As the total price is less than 10000, Two level approval process variant got triggered.
<br>![](/exercises/ex2/images/Two_level_Approval.png)
   <b>Note: If you have given totalprice to be more than 10000 and less than 50000, Three level approval variant would be triggered<br>
   If totalprice is more than 50000, Default variant would have been triggered.<br></b>
13.First step of approval will be for Department Approval.Click on "Approve"
   <br>![](/exercises/ex2/images/Dept_Approval.png)
14.Next level will be Procurement Approval.Click on "Approve"   
   <br>![](/exercises/ex2/images/Procurement_Approval_Form.png)
15. Process will be completed successfully
   <br>![](/exercises/ex2/images/Process_Completed_Successfully.png)

## Summary

You've now learnt how to model a process using Generative AI features, how to model different process variants with outcomes, parallel steps/branches etc.. and last but not the least, how to release, deploy and trigger a process(variant) in SAP Build Process Automation...

Thank you ! Do reach out to us in case of any other queries.. 
