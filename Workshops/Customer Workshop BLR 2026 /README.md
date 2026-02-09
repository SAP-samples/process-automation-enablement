# SAP Build Process Automation – Billing Block Hands-On Workshop

This repository contains a hands-on workshop demonstrating how to automate **Sales Order billing block removal** in **SAP S/4HANA** using **SAP Build Process Automation**.

---

## Overview

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

## Exercise 1 – Create Sales Order with Billing Block
---
## Exercise 2 – Build the Approval Process
### 2.1 Create Project and API Trigger
### 2.2 Read Sales Order Items
### 2.3 Approval Form
### 2.4 Read Sales Order Header (ETag)
### 2.5 Update Sales Order
### 2.6 Email Notifications
### 2.7 Release and Deploy
## Exercise 3 – Run and Monitor the Process

### 3.1 Trigger the Process

### 3.2 Monitor Process

### 3.3 Approve from Inbox

### 3.4 Validate in SAP S/4HANA

## Outcome

By completing this hands-on, you will learn the following:

- Created a Sales Order with Billing Block  
- Built an approval workflow in SAP Build  
- Integrated SAP S/4HANA APIs  
- Implemented approval-based automation  
- Tested an end-to-end business process  
---

SAP Build Team

