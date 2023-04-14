## Prerequisites
- Complete [2 Create Automation](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Process%20Automation/2%20Create%20Automation/spa-dox-create-automation.md) tutorial

## Details
With a Decision you can include several policies, guidelines, business rules and so on into your process flow.

### You will learn
  - How to create a decision
  - How to make use of data types and how to create them
  - How to maintain a decision table and include it in the process flow

Please note that the system flow may look slightly different due to the recent updates.

---

### Step 1: Add a decision and create a data type

You will now add a decision to the flow of your process. With this you are able to include business logic.

1. In order to add an approval step, we need to create a data type **Approver**
    - Click on **+** on the left of your screen
    - Select Create > Data Type

    ![Create new Data Type](07.png)

2. Enter the following information
    - Name: `Approver` 
    - Description: `Approvers Email Address`
    - The **Identifier** will be created automatically. 
    - Choose **Create**.

    ![Name data type](08.png)

3. Create a **New Field**.

    ![New Field](09.png)

4. Enter the **Name** **`eMail`**, leave the **Type** as **`String`**.

    ![eMail](10.png)

5. The new data type containing the email address of the approver is now created. **Save** your work.

    ![Save new data type](11.png)


6. Now we can create our decision to determine approver.
    - Navigate back to your **Get Invoice Details** process via the tab
    - Click on **+** after the automation **Extract Invoice Data**
    - Select **Decision** > **New Decision** to add a new one.

    ![add decision](01.png)

7. Enter the **Name** **`Determine Approver`** and also a **Description**, the **Identifier** will be created automatically. Choose **Create**.

    ![Decision Name](02.png)

8. The Decision **Determine Approver** is now in the process, choose the three dots and select **Open Editor**.

    ![Open Editor](03.png)

9. You see a **Decision Diagram** showing the flow of the data within the Decision. Here we need to add an input and output parameter:
    - Click on **Add Input Parameter**
    - Enter the following information for Input:
        - Name: `Determine Approver`
        - Description: `Determine approver input`
        - Type: `Invoice`
    
    - Click on **Add Output Parameter**
    - Enter the following information for Output:
        - Name: `determineApprover`
        - Description: `Determine approver output`
        - Type: `Approver` (What we created earlier in this exercise)
    
    - Your decision should look like the following

    ![Select new data type](12.png)

---

### Step 2: Create a decision table

There are many ways to express a business rule, in this case you will create a decision table to determine the approver of the invoice based on certain criteria.

1. Choose **Add Rule**.

    ![Add Decision Table](14.png)

2. Enter the following information:
    - Rule Name: `DT Determine Approver`
    - Description: `Decision table to determine the approver`
    - Click on **Next Step**

    ![Decision Table Name](15.png)

3. We need to configure the condition:
    - Click on the dropdown of input parameter `Determine Approver`
    - Select `Sender Name`

    ![Determine Approver Input](16.png)

4. Click on **Next Step**.

    ![Next Step](16bis.png)

5. Now we need to configure the output parameter:
    - Click on the dropdown of **Result Vocabulary**
    - Select the output parameter `determineApprover` 

    ![Determine Approver Output](17.png)

6. Select **eMail**.

    ![Select Email](18.png)

7. Select **Next Step** to review.

    ![Next Step](19.png)

8. Choose **Create** to create the rule.

    ![Create](20.png)

9. If you need to edit the rule, select the Pencil icon at the top

    ![Edit](21.png)

10. Now we need to define the attributes of the Determine Approver rule. 
    - Determine Approver: `EXISTSIN['ABC Communication']`
    - eMail: `'<Your SAP BTP User ID Email>'` e.g. 'john.doe@mail.com' Hint: as this is in string format, the email address needs to be in single quotes.

    Now, when an invoice contains the name "ABC Communication", the approval request will be sent to you.

    ![If Then](22.png)

11. Do the same for a company called Telecommunications
    - Select `Add Row`
    - Click on `Insert After`
    - Determine Approve: `EXISTSIN['Telecommunications']`
    - eMail: `'<Your SAP BTP User ID Email>'` e.g. John.doe@mail.com

    ![Add Row](23.png)

13. **Save** your work, your decision table is ready.

    ![Decision ready](24.png)

---

### Step 3: Maintain input and output of the decision

Though the Decision is ready, you need to connect it to the data flow of your process and define which data should be the input and output here. Also to get rid of this error marker.

1. Go back to the process and select the Decision.

    ![Error](28.png)

    > You might not see entries in the Input. This is due to a bug. As a workaround, click on the three-vertical-dot and delete the decision. Add the decision again in the process.

    > Please refer to [the Knowledge Base Article](https://launchpad.support.sap.com/#/notes/3207153) for the complete workaround.

2. Define the input, select the text field of **Document Number**.

    ![Input Decision](29.png)

3. Assign the related data from the **Process Content**, here select **Document Number**.

    ![Document Number](30.png)

4. Repeat this also for **Gross Amount** and **Sender Name**, both are part of **Invoice Details**. The input mapping is done.

    ![Invoice Details](31.png)

5. Just check the **Output**, it is **eMail**, as you have defined it in the decision itself. **Save** your work.

    ![Decision Output](32.png)


You have now defined who should approve the invoice, based on the company name. Next you will use the outcome of the business rule, the email address, as input for the approval.


Continue with the next part of the tutorial [4 Create Forms](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Process%20Automation/4%20Create%20Forms/readme.md)
