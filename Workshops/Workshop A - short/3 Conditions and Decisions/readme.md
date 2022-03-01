## 03 - Conditions 

## Table of Contents
- [Adding Process condition](#section1)
- [Summary](#summary)

## Adding Process condition <a name="section1"></a>
**Process condition** routes the business process based on certain criteria. These conditions apply an If or Else rule and the business process responds according to the rules defined as settings in the process builder.

In this section, you will learn how to use process condition in a business process to route the process towards auto-approval and one-level approval flow based on the total order value of the sales order.

1. Click the **+** and choose **Condition** from the given options.

    ![01-001](./images/01-001.png)

    This will add the condition to the process, and the condition configuration will open.

    ![01-002](./images/01-002.png)

2. On the right **Condition** configuration page, click on **If** text box and select **#orderAmount** from the process content.
    > Process content will contain list of attributes that have been defined in previous skills. For Example: In the screenshot, you can see attributes from the trigger form and automation. You will use these process content to configure different skills during business process modelling.

    ![01-003](./images/01-003.png)

3. In the same condition configuration, select **Less Than** operator and enter **100000** as the value.

  ![01-004](./images/01-004.png)


4. **Save** the process.

   ![02-027](./images/02-027.png)


## SUMMARY <a name="summary"></a>

You have successfully created and configured the process condition, data type and decision for the business process.

  You are now able to:
  - [x] Add & configure Process Condition

## Next chapter

Now, move on with **[04 Forms](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/Workshop%20A%20-%20short/4%20Forms)**.

## How to obtain support <a name="support"></a>

Support for the content in this repository is available during the actual time of the online session for which this content has been designed. Otherwise, you may request support via the [Issues](https://github.com/SAP-samples/process-automation-enablement/issues) tab.

## License <a name="license"></a>

Copyright (c) 2022 SAP SE or an SAP affiliate company. All rights reserved. This project is licensed under the Apache Software License, version 2.0 except as noted otherwise in the [LICENSE](../LICENSES/Apache-2.0.txt) file.


