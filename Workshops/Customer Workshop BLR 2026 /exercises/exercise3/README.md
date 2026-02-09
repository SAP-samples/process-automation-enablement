# Exercise 3 - Run Process

PLEASE LOGOUT and re-login in incognito mode with your user to run the process In this exercise, we use the sales order number created to start the process using API Trigger. User approves the billing block removal via an approval form and the billing block is removed in SAP S/4HANA.

## Exercise 3.1 Trigger the process using API trigger

After completing these steps you will have changed the billing block status for the Sales Order.

Note: Now the API Trigger will trigger the process that is created in SAP Build Process Automation.

You can access the API configuration under Control Tower > Environments > Select Environment > Triggers, you can call the Trigger API endpoint to create instances of the definition. However, to keep it simple we would be creating an instance from the lobby, you can follow below steps to create an instance corresponding to a definition in a project.

1. Under control tower, select environments tile
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/1.png)<br>
2. Enter the environment name in which your project is deployed in the search field to filter out your environment and click on the environment name to select the environment.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/2.png)<br>
3. Click on Processes and Workflows
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/3.png)<br>
4. Select the definition “Billing Block Removal Process” , ensure that its your project name that is displayed below the definition.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/4.png)<br>
5. Enter the start payload / Start Inputs and click then on the "start new instance". For example, below is a sample:
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/5.png)<br>
```json
{
"salesorder":"142001 ",
"salesorganization":"1010",
"overallbillingblockstatus":"c",
"division":"00",
"soldtoparty":"10100002"
}
```
## Exercise 3.2 Monitor Process

Let us check the running instance now.

1. Login to the SAP Build Lobby

3. Click on “Monitoring”.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/7.png)<br>
4. Click on “Process Workflow and Instances”
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/8.png)<br>
5. All the processes are listed in the logs. Search for your project by giving your Project Name in Project and select your Project.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/9.png)<br>
6. Click on the instance with Running status to view the details of the logs
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/10.png)<br>
7. Check that API trigger has started the process from the Context section

<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/11.png)<br>
8. Check the rest of the steps in the Logs section.

9. Details of the process are shown in the Logs. There is approval task in My Inbox. Click on My Inbox to go to the approval form.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/12.png)<br>
---

## Exercise 3.3 Approves Sales Order Update from Inbox

1. In My Inbox, the approval form shows the details for the Sales Order. Review , add comments, select the approve checkbox and click on Approve Billing Block Removal button.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/13.png)<br>
2. The process is completed successfully.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/14.png)<br>
---

## Exercise 3.4 View updated billing block in SAP S/4HANA

1. Click on Display Sales Order (VA03) from your Workspace.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/15.png)<br>
2. Enter the Sales Order number that you created and updated and click on Continue.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/16.png)<br>
3. Check that the Billing Block is now removed by the process.
<br><br>![](/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3/images/17.png)<br>

## Summary

You've now tested the end to end process and also checked the status update in the SAP S/4HANA. This marks the completion of hands-on for today's session.
