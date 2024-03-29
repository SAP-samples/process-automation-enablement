## Details
You work in the finance department of the company and need to regularly process incoming scanned invoices.

This is actually causing a lot of manual effort in order to extract the data out of the pdf or image, send to the approval of the manager before the data would be actually entered into the system.
This needs to be automated since we are talking about multiple invoices which are coming every single day. Also we need to define the approval flow depending on the specific criteria (in this tutorial series, company is considered as criteria).

### You will learn
  - How to create a project and the related process
  - How to add a form to trigger this process

### About this Exercise

In this exercise you create a process which houses all the project files related to an automation, including bots, workflows, decisions and forms. As part of this, you will define a set of inputs that will define the location and information of the process trigger. 

---

### Step 1: Create a Business Process Project

   The project includes all artifacts you will create during the course of these tutorials. You can share, release, rename or delete these projects.

1. Once you have entered the Lobby, choose **Create**, then select **Build an Automated Process** followed by **Business Process**.

    ![Create Business Process Project](01.png)

2. In the wizard enter the **Project Name** `Invoice Approval XX`, where XX must be replaced with **your initials**, and also a **Short Description**, then choose **Create**.

    ![Define Business Process Project](02.png)

---

### Step 2: Create a Process

   The process will describe the flow of the activities.

1. Within the newly created project **Invoice Approval**, select **Create** and then choose **Process**.

    ![Create Process](03.png)

2. Maintain the **Name** **`Get Invoice Details`** and also the **Description**. The identifier will be created automatically.

    ![Maintain Process Name](03a.png)

    The process with a start and end event is now available for you.

---

### Step 3: Configure Inputs for API Trigger

1. In the newly created process, click anywhere in the dotted background of the **Canvas** to open the **Process Details**.

    ![Canvas](API1.png)

3. Click on **Inputs** and then choose **Configure**.

    ![Inputs](API2.png)

3. In **Configure Process Inputs** window choose **Add Input** to add parameters.

    ![Add Inputs](1001.png)

4. Configure three inputs. Enter the names and choose types.

    |  **Name**    | **Type**
    |  :------------- | :-------------
    |  `fileName`       | string
    |  `folderName`     | string
    |  `employeeName`   | string

    **Apply** changes.

    ![Add Inputs](1002.png)

    Proceed to the next exercise: [2 Create Automation](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow/Build%20Process%20Automation/2%20Create%20Automation/spa-dox-create-automation.md)
