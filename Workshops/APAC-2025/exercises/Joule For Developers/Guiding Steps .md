In this page we are going to cover the steps on how to use Joule for developers to create a process.
Lets take "Purchase requisition Approval" as reference process.
In this process, requestor would submit purchase requisition approval form that has details like product quantity, number of units, prices etc.
Assume based on supplier, approver needs to be determined. Then the form will be sent to the approver. Approver reviews the PR form, approves or rejects the request.
If the request is approved PR shall be created in SAP S/4 HANA system.
<img width="1777" height="976" alt="image" src="https://github.com/user-attachments/assets/cbfe0dda-1a25-45fc-ad5a-9deb288770b9" />

Now let us see how this process can be created with SBPA - Joule for developers capability.
First step would be to create a project in the tenant.
Once the project is created, go to Overview tab and click on Generate.
<img width="547" height="402" alt="image" src="https://github.com/user-attachments/assets/07155bf4-c469-425f-bc52-f0ce5b6af633" />
Now select "Process" and provide the below prompt to generate the process
"Please generate a purchase requisition approval process, including an approval form "Purchase requisition approval" to review this data by the manager to approve or reject. When form is approved create approved email activity. When form is rejected create rejected email activity . After approval email activity, create an action "create new purchase requisition" to create the new purchase requisition in SAP S/4 HANA after its approval"
This generates process with certain activities such as form, email and it opens up in a new tab. Please note that the process name is generated based on the prompt.

<img width="1078" height="583" alt="image" src="https://github.com/user-attachments/assets/4d686209-86fe-43b9-a4c8-3c99e3cb032c" />

Now we will see how the process can be enhanced further such that required inputs and outputs are mapped, destinations are created, errors are fixed.






