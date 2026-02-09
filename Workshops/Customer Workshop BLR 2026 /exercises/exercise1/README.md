# Exercise 1 - Create Sales Order with a billing block

In this exercise, you will create a Sales Order by referring to an existing Sales Order or you can create a new one in your system if you have the required data. This Sales Order will have a billing block. Please note down the Sales Order number generated at the end of the exercise. This is needed later for designing the process and end-to-end testing.

**Note:** The Actions project shared as part of pre-requisites should be working as expected else the exercise below would not complete successfully.

---

## Exercise

After completing these steps you will have a Sales Order number created with a billing block.

### 1. Logon
Logon to your S/4HANA system (If you do not wish to use your own S/4HANA tenant, you can use the below details)

---

### 2. Create Sales Order
Search for **va01** and click **"Create Sales Order - VA01"**

Create the sales order using your desired data and configuration, below steps and data are for reference only.

---

### 3. Enter Order Type
Enter Order Type as **“OR”** and other required details and click on **“Continue”**.

Enter the following data and click on **Continue**:

- Sales Organization: 1010  
- Distribution Channel: 10  
- Divison: 00  

---

### 4. Enter Customer Details
Enter Sold-To-Party, Ship-To-Party, Customer Reference and ensure that you select some value in the **“Billing Block”**. This means there is a billing block on the Sales Order.

- Sold-To-Party: 10100002  
- Ship-To-Party: 10100001  
- Customer Reference: reference  

Click **Save** and if you get the above warning message, see if you need to make required corrections. If you still get the same error, press **Enter** on your keyboard.

---

### 5. Save Sales Order
Click **“Save”** and note down the Sales Order number. We will use this later while designing and executing the end-to-end process.

---

## Summary

Now that you have created the Sales Order, Continue to - **Exercise 2 - Create Process**

