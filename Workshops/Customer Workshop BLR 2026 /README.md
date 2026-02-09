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

1. Log in to SAP S/4HANA  
2. Open **VA01 – Create Sales Order**  
3. Enter:
   - Order Type: `OR`
   - Sales Organization: `1010`
   - Distribution Channel: `10`
   - Division: `00`
4. Enter:
   - Sold-To-Party
   - Ship-To-Party
   - Customer Reference
5. Select a **Billing Block**
6. Save the Sales Order and note the **Sales Order Number**

This Sales Order will be used in later exercises.

---

## Exercise 2 – Build the Approval Process

### 2.1 Create Project and API Trigger

1. Open **SAP Build Lobby**
2. Create a new **Process Automation Project**
3. Name the project:

```
Manage Billing Block in Sales Order_<username>
```

4. Create a process:
   - **Name:** Billing Block Removal Process
   - **Description:** Process to update the billing block based on approval

5. Add an **API Trigger**
   - Name: `SalesOrderAPITrigger`

#### Process Inputs

- SalesOrder
- SalesOrganization
- DistributionChannel
- OverallBillingBlockStatus
- Sold-To-Party

---

### 2.2 Read Sales Order Items

Add Action:
- **Reads all items of a sales order**

Configuration:
- Step Name: `Reads Sales Order Items`
- Destination: `S4HANADestination`
- Map `SalesOrder` from Process Inputs

---

### 2.3 Approval Form

Create an approval form containing:
- Sales Order header information (read-only)
- Sales Order Items table
- Required approver comment field
- Approve and Reject actions

Recipients: Approver email address

---

### 2.4 Read Sales Order Header (ETag)

Add Action:
- **Reads the header of a sales order**

Configuration:
- Step Name: `Get ETAG for PATCH`
- Destination: `S4HANADestination`
- Map `SalesOrder` from Process Inputs

This ensures concurrency control before update.

---

### 2.5 Update Sales Order

Add Action:
- **Updates a sales order**

Configuration:
- Step Name: `Updates a sales order`
- Destination: `S4HANADestination`
- Map:
  - `ifMatch` → ETag from previous step
  - `SalesOrder` → Process Inputs

---

### 2.6 Email Notifications

#### Approval Notification
- Subject: **Approved: Removal of Billing Blocks**
- Body includes Sales Order Number

#### Rejection Notification
- Subject: **Rejected: Removal of Billing Blocks**
- Body includes Sales Order Number

---

### 2.7 Release and Deploy

1. Validate the project
2. Click **Release**
3. Deploy to your user environment
4. Select the configured destination

---

## Exercise 3 – Run and Monitor the Process

### 3.1 Trigger the Process

Trigger the process using the **API Trigger** with the Sales Order created in Exercise 1.

---

### 3.2 Monitor Process

1. Open **SAP Build Lobby**
2. Navigate to **Monitor → Process Workflow and Instances**
3. Locate your project instance
4. Verify logs and execution steps

---

### 3.3 Approve from Inbox

1. Open **My Inbox**
2. Review Sales Order details
3. Add comments
4. Approve or Reject the request

---

### 3.4 Validate in SAP S/4HANA

1. Open **VA03 – Display Sales Order**
2. Enter the Sales Order number
3. Confirm that the **Billing Block is removed**

---

## Outcome

By completing this hands-on, you have:

- Created a Sales Order with Billing Block  
- Built an approval workflow in SAP Build  
- Integrated SAP S/4HANA APIs  
- Implemented approval-based automation  
- Tested an end-to-end business process  
---

SAP Build / Automation Workshop Team

