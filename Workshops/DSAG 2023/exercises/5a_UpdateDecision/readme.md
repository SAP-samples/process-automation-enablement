
## Table of Contents
 - [Overview](#overview)
 - [Update Business Rule](#updateBR)
 - [Summary](#summary)

### Overview <a name="overview"></a>

In this exercise you will learn:

- How to update the business rule and related decision

## Update Business Rule <a name="updateBR"></a>


1. Select the decision **Determine Approver** and map the attribute of the Invoice Details from **Extract Invoice Data** to **Invoice Parameter**: DocumentNumber, GrossAmount and SenderName.

    ![05a](./images/001.png)
    
    
2. To open the decision editor of **Determine Approver** select **Open Editor**.

    ![05a](./images/002.png)
    
3. Select **Edit Decision**.    
    
    ![05a](./images/003.png)
    
4. On the left hand side you can see the decision diagram, including input and output parameters and also the related rule. On the right hand side select **Rules** tab and click the decision table **Determine Approver** to change the business rule now.
        
    ![05a](./images/004.png)
   
5. Based on the SenderName different approvers are available. In **Then** column **change the eMail to your eMail address** which you have used to log in to the lobby at the beginning. *Hint:* as this is in string format, the email address needs to be in single quotes.
Click **Save**.   
    
    ![05a](./images/005.png)
    
## Summary <a name="summary"></a>

Now you have adapted the decision and your final result should look like this:
    ![05a](./images/006.png)


Continue to - [Exercise 6 - Release and Deploy Process](../6_ReleaseDeployProcess/Readme.md)
