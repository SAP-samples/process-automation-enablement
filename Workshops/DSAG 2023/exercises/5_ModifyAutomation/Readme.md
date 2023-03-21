## Table of Contents
 - [Overview](#overview)
 - [Modify the Automation](#modifyAutomation)
 - [Map Automation parameters to Process parameters](#mapParameters)
 - [Summary](#summary)

### Overview <a name="overview"></a>

In this exercise you will learn:

- How to modify and add an automation as a dependency.

The pre-built automation extracts the data from the Invoice document using AI.

## Modify the Automation <a name="modifyAutomation"></a>

1. Once the dependency is completed, choose **Extract Invoice Data**, select three dots, and then **Open Editor**.

    ![05](./images/010a.png)

2. In **Automation Details**, go to **Input/Output** to modify the parameters.

- Rename **FilePath** to **fileName**.
- Select **Add new input parameter** and name it **folderName**.

    ![05](./images/016a.png)

    After the changes the parameters should look like this:

    ![05](./images/017.png)

3. Go to **Tools**, select **Automations** and drag and drop the **Download document** automation into the canvas, just before **Extract Data** activity.

    ![05](./images/018.png)

4. Select **Download document** automation.

5. You will now map the **Input Parameters**. Select **Edit Expression** next to **uploadedFileName** field.

    ![05](./images/019.png)

6. Map with variable **fileName** and select **Save Expression**.

    ![05](./images/098.png)

7. Select **Edit Expression** next to **folderFileName** field.

    ![05](./images/097.png)

8. Map with variable **folderName** and select **Save Expression**.

    ![05](./images/099.png)

9. The **outputPath** needs to be hard-coded:

    - Open the expression editor.

    ![05](./images/080.png)

    - In the Edit Expression window paste following value:

      <pre> "C:\\Users\\Public\\" + Step0.fileName </pre>

      ![05](./images/081.png)

      > To check if the Expression is correct, click on Test button. If it is highlighted in green, it means the expression is correct.

10. Choose **Save Expression**.

11. Select **Extract Data**. In Input Parameters, next to **documentPath** open the Expression Editor.

    ![05](./images/082.png)

12. Once the **Edit Expression** window opens, replace the value with:

    <pre> "C:\\Users\\Public\\" + Step0.fileName </pre>

    > To check if the Expression is correct, click on Test button. If it is highlighted in green, it means the expression is correct.

13. Choose **Save Expression**.

14. **Save** your work.

## Map Automation parameters to Process parameters <a name="mapParameters"></a>

1. Go to the process tab **Get Invoice Details**. Select **Extract Invoice Data** and map the following inputs:

- Map **fileName** with **fileName**.
- Map **folderName** with **folderName**.

    ![05](./images/024.png)

2. **Save** your work.

## Summary <a name="summary"></a>

You have now modified the project.

Continue to - [Exercise 5a - Update Decision](../5a_UpdateDecision/readme.md)
