## 02 - Automation

## Table of Contents
- [Create Automation](#section1)
- [Create Environment Variable](#section3)
- [Building Automation with Activities](#section4)
    - [Open Excel Instance](#section4-excel1)
    - [Add Excel Cloud Link](#section4-excel2)
    - [Close Excel Instance](#section4-excel3)
    - [Add Input/Output Parameters](#section4-inputOutputParams)
    - [Adding Variable](#section4-variable)
    - [Looping Operation using For Each Activity](#section4-loop)
    - [Add Condition in ForEachLoop](#section4-loopcondition)
    - [Set Variable Value using Data Management Activities](#section4-setvariable)
    - [End the loop](#Endloop)
    - [Log message](#section5)
- [Pass Output Parameters from Automation to Business Process](#section6)
- [Mapping the Automation parameters with Form Parameters](#section7)
- [Test the Automation](#section8)
- [Summary](#summary)


## Create Automation <a name="section1"></a>

>Automation is succession of steps to orchestrate multiple activities and applications on a local machine.

 In this excercise, you will automate the process to read the sales order details from an Excel and select the specific sales order details based on the input from the submitted form.

1. In the **Lobby**, Select the process **Order Processing**.
    Right click  ![00-01](./images/AddButtonProcess.png)  and select **Automation** > **New Automation**.

    ![00-01](./images/Step1.2-CreateNewAutomation.png)

2. A pop up appears to onfigure the DesktopAgent version.  
   From the dropdown, select the version of the Desktop Agent installed on your machine.
   It would be with suffix as **Registered** .
   Click on **Confirm**.

   ![00-01](./images/Step1.3-ConfigureAgentVersion.png)

3. In the pop-up, do the following:
    - Enter **Name** of the automation as **Get Order Details**.
    - Enter **Description** of your choice, if needed.
    - Click **Create**.
    > Identifier will be auto-filled.

   ![00-01](./images/Step2-AutomationName.png)

   An automation **Get Order Details** is  created successfully.

   ![00-01](./images/Step1.4-AutomationCreated.png)


## Create Environment Variable <a name="section3"></a>
>Environment variables allow you to reuse certain information for a given environment.You use environment variables to pass parameters to automations.

Create an **Environment variable** to provide an option to dynamically enter the Excel path during the automation.


1. Select **Settings > Envirnoment Variables >Create**

    ![00-01](./images/Stpe2.1-CreateEnvironmentVariables.png)

2. In the new environment variable screen, do the following:
    - Enter the **Name** of the variable as **OrderFilePath**.
    - Click the **Type** as **String**.
    - Click on **Create**.

     ![00-01](./images/Step5.1-NameofEnviornmetVar.png)

Environment variable is created successfully.

   ![00-01](./images/EnvVariableSuccess.png)

## Building Automation with Activities,Controls and Data <a name="section4"></a>

Double click on the automation **Get Order Details** which navigates to Design studio to build your automation.

### Open Excel Instance <a name="section4-excel1"></a>

Open Excel Instance is a **mandatory** activity to use when using MS Excel. It opens an instance of MS Excel. Once you open an Excel instance, you can use other MS Excel activities.

1. To open **Excel Instance**, do the following:
    - Search for **Open Excel Instance** in **Automation Details** section on the right.
    - Drag and drop the activity to the canvas.

    ![00-01](./images/Step3-OpenExcelInstance.png)

### Excel Cloud Link <a name="section4-excel2"></a>

Excel Data Mapping is done with the Excel Cloud Link activity.
Excel Data Mapping allows you to transform columns-based data from an Excel sheet into data that can be used in your automation. The data from the Excel sheet stays the same but the structure becomes a data type structure, making it possible to use throughout your project

1. To get the **Excel Cloud Link**, do the following:
    - Search for the activity **Excel Cloud Link** in **Automation Details**.
    - Drag and drop the activity to the canvas.
    - Select **Edit activity**.

     ![00-01](./images/Step4-ExcelCloudLink.png)

2.  In the **Excel File** screen that opens up, select **Browse** and choose the **SalesOrdersDetails.xlsx** file  which is saved in your machine.(Excel is available in Pre-requisites)

    > The Excel file is mapped automatically .

    ![00-01](./images/Step4.1-ExcelCloudBrowseFile.png)

 3. Enter the **Environment Variable** as **OrderFilePath** which is created above as the parameter value for **Workbook path**.

      ![00-01](./images/Step5-ExcelCloudPath.png)

 4. Select the button **From Excel Data**.
    > A pop up appears to create a data type. A **Sales Order** variable is needed to collect the data from the excel sheet columns. In this step, a variable is automatically created from the excel file columns.

 5. Enter the **Name** of the data type as **Sales Order** and click on **Create**.
    > Framework creates a data type with the columns of the Excel as the field names.

      ![00-01](./images/Step4.3-ValdiatedDataType.png)

 6. Change the variable name to **Orders** in the **Output Parameters** of the **Excel Cloud Link** Activity.

      ![00-01](./images/Step4-ExcelCloudLinkOutputParm.png)


### Close Excel Instance <a name="section4-excel3"></a>

Close Excel Instance activity closes an instance of MS Excel.

To close the opened instance of the excel file, do the following:
  - Search for the activity **Close Excel Instance** in **Automation Details**.
  - Drag and drop the activity to the canvas.

**Save** the automation.

### Add Input/Output Parameters <a name="section4-inputOutputParams"></a>
 Input and output parameters allow you to exchange data in the workflow of your automation between activities, screens, and scripts.

1. Click on the canvas and select the **Input/Output** section in **Automation Details**.

     ![00-05](./images/Step11-InputOutput.png)

2.  Add Input and Output parameters as following:

      |  Parameter Name     | Data type  | Parameter Type |Description
      |  :------------- | :-------------  | :-------------- | :--------------- |
      |  OrderNumber      | **`String`** | Input       | Receives Order number from the Order Processing Form
      |  selectedOrder        | **`SalesOrder`** |Output | Selected Order details are passed to the Process


  ![00-05](./images/Step11-InputoutputParams.png)    

### Creating Variable <a name="section4-variable"></a>

Variables that are used build your automation are data storage that has a name, a type (example: string, list of string or data type), and a value. A variable in the automation is also associated to a step represented by its number.

1. Search for the **Sales Order** Data type (created in previous step) in **Automation Details**.

    ![00-01](./images/Step6-CreateSalesOrderVaraibleV2.png)

2.  Drag and drop the **Sales Order** in the canvas.
    > A variable of the data type **Sales Order** is created.
      - Enter the value of **Output Parameters** as **selectedOrderDetails**.

     ![00-03](./images/CreateSalesOrderoutput.png)

>Now,let's check if the Order Number entered in the **Form** is present in the SalesOrderDetails Excel.

### Looping Operation using For Each Control <a name="section4-loop"></a>
Now you will loop through each **Order** from the excel sheet retrieve the Order details for order number submitted in the **Order Processing Form**.

**For Each** control allows you to go through a list of members provided as input to your automation, and execute an action for each member in that list.

This control has the following loop parameters:
 - **currentMember** - The member of the list for the current loop iteration.
 - **index** - An integer that is the index of the current loop iteration, starts at 0.

- Search for the control **For Each** in **Automation Details**.
- Drag and Drop the activity to the canvas.
- Enter the value of **Set looping List** as **Orders**.

  ![00-01](./images/Step7-ForEach.png)


### Add Condition inside For Each loop <a name="section4-loopcondition"></a>
In this condition, you will check if the Order number entered in the **Form** is available in  data read from Excel in **Step 2**.

1. Search for the activity **Condition** in Automation Details.
2. Drag and Drop the activity **inside** the **For Each** block
3. Click on ![00-01](./images/EditExpressionButton.png) -> **Edit Formula** to add the condition.

  ![00-01](./images/Step8-Condition.png)

4. A pop up window appears to enter condition expression.
   - > You can enter this expression manually or you can expand the **Variables** list and select the given variables to form the expression.

   **Step0.OrderNumber === Step5.currentMember.orderNumber**

  ![00-01](./images/Step8.1-ConditionEditExp.png)


### Set Variable Value using Data Management Activities <a name="section4-setvariable"></a>

If the Order number is found in Excel, i.e. the condition is **True**,set the variable using **Set Variable Value**

- Search for the activity **Set Variable Value** in **Automation Details**.
- Drag and Drop the activity to the canv

  ![00-01](./images/Step9-SetVariableValue.png)

- In the **Set Variable Value** configuration screen on the right, do the following:
    - Enter **selectedOrderDetails** as the **variable**
    - Enter **currentMember** as the **value**.


  ![00-05](./images/Step9.1-SetVariablevalueParamV2.png)

## End the loop <a name="Endloop"></a>

Once the order number is found in the excel, use the control **End Loop**  to stop the loop.

![00-05](./images/LoopEnd.png)

## Log message <a name="section5"></a>
Use Log message activity to print your results.
Let's use this activity to check **selectedOrderDetails** in Testing mode.

![00-05](./images/LogMessage.png)

## Pass Output Parameters from Automation to Business Process <a name="section6"></a>

  Apart from creating an output parameter, it is mandatory to pass the data
  through **End** step to expose the data outside the automation.

  - Click on **End**
  - In the **End** configuration screen on the right,
      - Enter **selectedOrderDetails** as the **Output Parameter**.


  ![00-05](./images/Step12-PassingParamEnd.png)

>Make  sure to add the steps **Condition**, **Set variable value**,**End Loop** inside the **For Each** block.

**Save** the Automation.

## Mapping the Automation parameters with Form Parameters <a name="section7"></a>

- Select **Get Order Details** automation in the process **Order Processing**.
- Map the input parameter **OrderNumber** of the automation  **Get Order Details**
  with the **Order Number** of **Order  Processing Form**.

  ![00-05](./images/Step13-MappingAutomation_Form.png)

Click on **Save** to save the **Order Processing** process.

## Test the Automation <a name="section8"></a>

- Click on  ![00-05](./images/TestButton.png) button.
- Enter the parameters to test the Automation.

|  Parameter     | Value  
|  :------------- | :-------------  |
|  Order Number      | Any order number which is available in SalesOrdersDetails Excel, e.g. **PO7918** |
|  OrderFilePath       |Path where the SalesOrderDetails Excel is stored in your local machine| Selected Order details are passed to the Process

![00-05](./images/TestResultsOrderNumberString.png)

Test Results:

1. Automation opens the SalesOrderDetails Excel.
2. Reads the Excel content.
3. Closes the Excel.
4. Loops through Excel and verifies if entered OrderNumber is available in the Excel. If the OrderNumber  is available in the Excel, it sets the Orders Details.
5.Ends the looping.
6.Prints the selected order details .

![00-05](./images/TestResults.png)


## Summary <a name="summary"></a>
You have successfully created and configured the process automation for the business process. The complete automation **Get Order Details** looks as below.  

![00-05](./images/FinalAUtomation.png)

You are now able to:
 - [x] Add Automation to business process.
 - [x] Add & configure Excel Activities.
 - [x] Create & configure ForEach loop and condition.
 - [x] Create Envirnoment Variables.
 - [x] Define Input and output parameters.

## How to obtain support <a name="support"></a>

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](../../../../issues) tab.

## License <a name="license"></a>

  Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](../LICENSES/Apache-2.0.txt) file.
