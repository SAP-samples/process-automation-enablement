Previous Step: <a href="https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow/Build%20Apps/3%20Details%20Page/3_1%20UI%20Building%20for%20Details%20page/Readme.md"> 3.1 UI Building for Details Page</a>.

# Data Connection for Details Page.

The app will have two Data Conenctions: <br>
  i) Document Management System (DMS) - to store the invoice from the application<br>
 ii) SAP Build Process Automation - to trigger the invoice processing.<br>
 
 Both the connections will be integrated through Rest API.
 <br><br>


1. Click on <b>DATA</b> tab on the top to open the Data connections tab.<br><br>
![Data](Images/01.png)

2. Select <b>AppGyver classic data entities</b> and select <b>REST API direct integration</b>.<br><br>
![Data](Images/02.png)

3. In the <b>BASE</b> tab of the API configuration enter the following values.<br><br>
<b>Resource ID</b> : Documentupload<br><br>
<b>Resource URL</b>: https://end-to-end-demo-lcnc-trial.integrationsuitetrial-apim.eu10.hana.ondemand.com/end-to-end-demo-lcnc/httpjsonv2/docrepoupload<br><br>
![Data](Images/03.png)

4. Select the <b>GET COLLECTION</b> tab and disable the <b>Method enabled</b> option to disable get collection for the API.<br><br>
![Data](Images/04.png)

5. Select <b>GET RECORD</b> tab and disable the <b>Method enabled</b> option to disable get record for the API.<br><br>
![Data](Images/05.png)

6. Now select the <b>CREATE RECORD</b> tab and enable it.<br><br>
![Data](Images/06.png)

7. Switch to <b>SCHEMA</b> tab.<br>
 Under <b>Create record (POST) request schema</b> use the drop down list and select <b>Custom schema</b>.<br><br>
 ![Data](Images/07.png)
 
8. Click on <b>ADD PROPERTY</b>.	<br>					
Rename the key in the property to “<i>base64</i>”.<br><br>
![Data](Images/08.png)

9. Add another property and rename it to “<i>fileName</i>”.<br><br>
  ![Data](Images/09.png)
  
10. Click on <b>SAVE DATA ENTITY</b>.<br><br>
![Data](Images/10.png)

11. Add another <b>REST API direct integration</b>.<br><br>
![Data](Images/11.png)

12. Add the following configuration in the BASE tab.<br><br>
<b>Resource ID</b> : sendtoSPA<br>
<b>Short description</b> : Send info to SPA<br>
<b>Resource URL</b> : https://end-to-end-demo-lcnc-trial.integrationsuitetrial-apim.eu10.hana.ondemand.com/end-to-end-demo-lcnc/lcnc<br><br>
![Data](Images/12.png)

13. Disable <b>GET COLLECTION</b> and <b>GET RECORD</b> and enable <b>CREATE RECORD</b>.<br>
Now add a HTTP header. <br><br>
![Data](Images/13.png)

14. Enter the following values in the fields under the properties of the HTTP header.<br><br>
<b>Label</b> : content-type<br>
	<b>Key</b> : Content-Type<br>
  <b>Value type</b>: Text<br>
  <b>Is static</b> : enabled <br>
  <b>Value</b> : application/json<br><br>
  Click on <b>SAVE DATA ENTITY</b><br><br>
![Data](Images/14.png)

  15. Now switch to <b>SCHEMA</b> tab and <b>Custom schema</b> under <b>Create record (POST) request schema</b>.<br><br>
![Data](Images/15.png)
  
16. Click on <b>ADD PROPERTY</b> rename the key to “<i>context</i>” and change the value type to “<i>Object</i>”.<br><br>
![Data](Images/16.png)
  
17. Select the <b>id</b> and rename it to “<i>employeename</i>”.<br><br>
![Data](Images/17.png)
  
18. Click on the <b>+</b> icon in the context tab to add more properties under context. <br><br>
![Data](Images/18.png)

19. Add two properties under context and rename the <b>key</b> values as “<i>filename</i>” and “<i>foldername</i>”.<br><br>
![Data](Images/19.png)
  
20. Now click on <b>ADD PROPERTY</b> to add another property and rename it as “<i>definitionId</i>”.<br><br>
![Data](Images/20.png)
  
21. Click on <b>SAVE DATA ENTITY</b> to save the data connection.<br><br>
![Data](Images/21.png)
  
22. Click on <b>SAVE</b> and switch to <b>UI CANVAS</b>.<br><br>
![Data](Images/22.png)  
  
  Next Step: <a href="https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow/Build%20Apps/3%20Details%20Page/3_3%20Logic%20Building%20for%20Scan%20button/Readme.md"> 3_3 Logic Building for Details Page</a>


