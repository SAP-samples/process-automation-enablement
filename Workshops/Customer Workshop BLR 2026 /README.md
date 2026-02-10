# SAP Build Process Automation – Billing Block Hands-On Workshop

This repository contains a hands-on workshop demonstrating how to automate **Sales Order billing block removal** in **SAP S/4HANA** using **SAP Build Process Automation**.

---

## Overview

Billing block is applied in Sales Order by internal sales representatives to prevent invoice being created in case of sales returns.<br>
These billing blocks need to be updated or deleted in random or on-demand fashion and is time critical activity in Order-to-Cash process.<br>
In many organizations this process is still manual where internal sales representatives get billing block change requests in form of Excel or Email attachment.<br>
Sales representatives download these attachments and then sales orders are manually updated in the S/4HANA system based on data in the excel files or attachments.<br>

**Process Flow**

```
Sales Order (Billing Blocked)
        ↓
API Trigger (SAP Build)
        ↓
Read Sales Order Items
        ↓
Approval Form
        ↓
Approved → Update Sales Order → Billing Block Removed
Rejected → Notification Sent
```

---

## Prerequisites

- SAP S/4HANA system access  
- SAP Build Process Automation tenant  
- Configured Actions project  
- S/4HANA Destination (e.g. `S4HANADestination`)  
- Email server configured in SAP Build  
- Valid customer and sales organization master data  

---

## [Exercise 1 – Create Sales Order with Billing Block](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise1)

## [Exercise 2 – Build the Approval Process](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise2)

## [Exercise 3 – Run and Monitor the Process](https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/Customer%20Workshop%20BLR%202026%20/exercises/exercise3)

## Outcome

By completing this hands-on, you will learn the following:

- Created a Sales Order with Billing Block  
- Built an approval workflow in SAP Build  
- Integrated SAP S/4HANA APIs  
- Implemented approval-based automation  
- Tested an end-to-end business process  
---

SAP Build Team

