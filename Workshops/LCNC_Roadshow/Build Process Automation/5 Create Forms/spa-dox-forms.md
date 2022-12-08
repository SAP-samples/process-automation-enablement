## Prerequisites
- Complete the previous part of the tutorial [4 Create Decision](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow/Build%20Process%20Automation/4%20Create%20Decision/spa-dox-create-decision.md)

## Details
There are different requirements and business situations when a form is needed in a business process. You have already created a form to start the process.
Most often you probably need a form to maintain some input data or to approve or reject a request or even to send out some notifications.
The two latter ones are your focus now.


### You will learn
  - How to leverage the result of the Decision in an approval form
  - How to create an approval form
  - How to create forms to notify process participants

---

### Step 1: Create New Approval Form

1. Let's add a form as part of the decision flow. Navigate to the **Get Invoice Details** process:
    - Click on **+** at the end of the process
    - Click on `Approvals`
    - Select `New Approval Form`

    ![New Approval Form](01.png)

2. Provide the following information to the form:
    - Name: `Invoice Approval Form`
    - Description: `Form to approve the invoice`
    - The identifier is created automatically

    ![Maintain approval form name](02.png)

3. Choose the three dots on the created form's artifact and select **Open Editor** to do the same. Just ignore the red frames, you will fill them later.

    ![Open Editor](03.png)

4. Now you are in the Form's Editor, where you can define the layout and input fields. First add via drag and drop a new **Headline 1** to the canvas.   Provide this headline **`Invoice Approval`**.

    ![Add Headline](04.png)

5. Drag and drop a **Paragraph** into the canvas. Insert **`Invoice Details`** in the paragraph.

    ![Add paragraph](05.png)

6. Include a **Text** field in your form.

    ![Add text field](06.png)

7. Change the name to **`Company Name`** and select **Read Only**, as you will display here some information from the process content.

    ![Maintain text field](07.png)

8. Add some further input fields to your form. Please ensure you have selected the correct type and also maintain all of them as **Read Only**.

    |  Field Type    | Name
    |  :------------- | :-------------
    |  Text          | **`Invoice Number`**
    |  Number           | **`Gross Amount`**
    |  Text   | **`Employee Name`**

    ![Further input fields](08.png)

9. You are done with the layout and input fields of the approval form. **Save** your work.

10. Go back to your process, you will recognize some errors, e.g. inputs are missing. No need to worry, you will provide the required details in the next steps.

    ![Errors](09.png)

11. Select the **Invoice Approval Form** and in the **General** tab of the form properties, move to **Subject** and choose **Select Item**.

    ![Select Item](10.png)

12. Apply the following information:
    - Enter the text `Please approve the invoice` then select `Document Number`
    - This will combine plain text with process information and serves as an unique identifier.

    ![Add process content](11.png)
 
13. Add the following addiitonal information to the approval form:
    - Recipient > Users: `eMail`
    - This is the approve of the invoice outlined in our decision

    ![Approval user](12.png)

14. Switch to the **Inputs** tab and within **Employee Name** choose **Select Item**. The process content will be opened again.

    ![Approval Form inputs](14.png)

15. Now add the attributes from the process content to the related input fields.

    > You can only assign fields with the same type, e.g. text in the process content to text input field.
     If you cannot assign, e.g. Invoice Number from the process content to the Invoice Number in the input field, the type of the input field might be wrong. If so, please correct your form.

    |  Process Content    | Input Field
    |  :------------- | :-------------
    |  Employee Name          | Employee Name
    |  Sender Name           | Company Name
    |  Gross Amount    | Gross Amount
    |  Document Number          | Invoice Number

    ![Add Approval Form inputs](15.png)

16. As this mapping of process content and forms is quite important to ensure a proper flow of the relevant data in your process, please check them again. It should look like this.

    ![Check Approval Form inputs](16.png)

---

### Step 2: Create Approval Notification Form

1. Choose the **+** of the control flow for **Approve** coming from the **Invoice Approval Form** you have just created. In the context menu, select **Forms > New Form**.

    ![New Approval Notification Form](17.png)

2. Maintain the **Name** **`Invoice Approval Notification Form`** and also the **Description** **`Form to notify about the approved invoice`** and choose **Create**. As always, the **Identifier** has been created automatically.

    ![Maintain Notification Form](18.png)

3. In the newly created **Invoice Approval Notification Form**, choose the three dots and select **Open Editor**.

    ![Open Editor](19.png)

4. In the form, add a headline **`Invoice Approval`**, a paragraph **`Your invoice has been approved.`** and also a text field **`Invoice Number`** and select here **Read Only**. **Save** your work.

    ![Invoice Approval Notification Form](20.png)

5. Go back to the process select **Invoice Approval Notification Form** to maintain the information in **General** tab.

    ![Approval Notification General](21.png)

6. Maintain **Subject** and select for the **Users** in this case **your email, e.g. jane.doe@sap.com (without quotation marks!)**.

    ![Approval Notification General Entries](22N.png)

7. Select **Inputs** tab and assign the **Invoice Number** from the process content here.

    ![Approval Notification Input](23.png)

8. **Save** your work.

### Step 3: Create Rejection Notification Form

1. Select **+** of the **Reject** control flow from the **Invoice Approval Form**. Select **Forms > New Form**.

    ![New Rejection Notification form](24.png)

2. Maintain the **Name** **`Invoice Reject Notification Form`** and also the **Description** **`Form to inform about the rejected invoice`** and choose **Create**. As always, the **Identifier** has been created automatically.

    ![Maintain Rejection Notification form](25.png)

3. In the newly created **Invoice Reject Notification Form**, choose the three dots and select **Open Editor**.

    ![Open Editor Rejection Notification form](26.png)

4. In the form, add a headline **`Invoice Rejection`**, a paragraph **`Your invoice has been rejected.`** and again also a text field **`Invoice Number`** and select here **Read Only**. **Save** your work.

    ![Invoice Reject Notification Form](27.png)

5. Go back to the process, select **Invoice Reject Notification Form** to maintain the information in **General** tab.

    ![Reject Notification General](28.png)

6. Maintain **Subject** and hardcode for the **Users** in this case **your email, e.g. jane.doe@sap.com (without quotation marks!)**.

    ![Reject Notification General Entries](29N.png)

7. Select **Inputs** tab and assign the **Invoice Number** from the process content here.

    ![Reject Notification Input](30.png)

8. Add an end event, choose the **+** of the control flow from the **Invoice Reject Notification Form** and select **Controls > End**.

    ![End event](31.png)

9. Your process is ready to be released, deployed and executed. **Save** your work.

    ![Final process](32.png)


  Proceed to the next exercise: [6 Run Process](https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow/Build%20Process%20Automation/6%20Run%20Process/spa-dox-run-api-trigger.md)
