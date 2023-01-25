Previous Step: <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Apps/2%20Home%20Page/2_1%20UI%20Building/readme.md">  2_1 UI Building for Home Page</a>

# Logic Building for the Home Page

You have successfully created the UI for the home page of your application. Now, let’s build logic for your application

1. Switch to <b>VARIABLES</b> view.
<br><br>![Varview](Images/23.png)

2. By default, you will be on <b>APP VARIABLES</b> tab. Now click on <b>ADD APP VARIABLE</b>.<br>
   These app variables can be used across all the pages in your application.<br><br>![Varview](Images/24.png)

3. Change the name of the variable to “<i>FirstName</i>” in the properties tab of the variable.
<br><br>![Varview](Images/26.png)

4. Similarly, add another app variable and rename it as “<i>LastName</i>”.<br><br>
![Vlast](Images/27.png)	
  
5. Switch back to <b>Canvas</b> view.<br><br>
![Canvas](Images/25.png)

6. Now, we can save the values from the input field to the App variables that was created in last step.<br>
Select the first input field, and under the properties of the input field component click on <b>X</b> icon under <b>Value</b> to bind a value to the component.<br><br>
![Bind](Images/Screenshot%202022-09-20%20at%2021.38.35.png)

7. A binding menu will open. Select <b>Data and Variables</b>.<br><br>
![BindMenu](Images/Screenshot%202022-09-20%20at%2021.39.53.png)

8. Now select <b>App variable</b>.<br><br>
![Appvar](Images/Screenshot%202022-09-20%20at%2021.41.30.png)

9. Here, you can see the list of App variables available in your application.<br>
 Since, the current input field component is for the first name, select <b>FirstName</b> app variable and click on <b>SAVE</b> button.<br><br>
 ![Appvar2](Images/Screenshot%202022-09-20%20at%2021.52.55.png)
 
10.  Similarly, select the Input field 2 and click on click on <b>X</b> icon under <b>Value</b> to bind a value to the component.<br><br>
![Input2](Images/Screenshot%202022-09-20%20at%2021.56.17.png) 

11. A binding menu will open. Select <b>Data and Variables</b>.<br><br>
![BindMenu2](Images/2.png)

12. Now select <b>App variable</b>.<br><br>
![Appvar3](Images/3.png)

13. Select <b>LastName</b> app variable and click on <b>SAVE</b> button.<br><br>
![Lastnamebind](Images/Screenshot%202022-09-20%20at%2021.57.53.png)

14. We need to create a new page now.<br> Before that click on <b>SAVE</b> on the top right corner to
save the progress of your application.<br><br>
![Save](Images/Screenshot%202022-09-28%20at%2015.41.44.png)

15. Select <b>Home Page</b> on the top left to open the page dashboard of your application.<br><br>
![Homepage](Images/15.png)

16. Click on <b>ADD NEW PAGE</b> to add a page for your application.<br><br>
![Newpage](Images/Screenshot%202022-09-20%20at%2022.05.20.png)

17. Under the <b>Name</b>, enter "<i>Details</i>".<br>
 click on <b>OK</b> button.<br><br>
 ![Newpage2](Images/Screenshot%202022-09-20%20at%2022.10.26.png)

18. We can work on this page later, Click on <b>SAVE</b> and switch back to <b>Home Page</b>.<br><br>
![Details](Images/Screenshot%202022-09-20%20at%2022.12.10.png)

19. To switch back to Home page click on <b>Details</b> on the top left corner to open the page dashboard.<br><br>
![Pagedashboard](Images/19.png)

20. Now select the <b>Home Page</b> to open the home page.<br><br>
![Pagedashboard2](Images/20.png)

21. Select the button component and click anywhere on the grey bar on the bottom to open the logic composer.<br><br>
![Pagedashboard3](Images/21.png)

22. The logic composer for button component will pop-up now.<br> You can see the default trigger <b>Component tap</b> on the logic canvas. So, the flow will trigger when you tap on the button component.<br>
Drag and drop <b>Open page</b> logic from the logic component library to the logic canvas.<br><br>
![Openpage](Images/Screenshot%202022-09-20%20at%2022.22.39.png)

23. Connect the nodes of the two components to create a flow between these two logic components.<br><br>
![BindMenu2](Images/Screenshot%202022-09-20%20at%2022.27.12.png)

24. Now select <b>Open Page</b> component. On right-hand side you can see the properties of the logic
component. Since your app only has two pages for now, by default other page will be selected.<br><br>
![Openpage2](Images/Screenshot%202022-09-20%20at%2022.29.29.png)

25. Click on <b>SAVE</b> to save your progress.<br><br>
![Save](Images/Screenshot%202022-09-20%20at%2022.31.51.png)


#### Home Page has been created successfully. Next you will develop the details page. 

Next Step: <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Apps/3%20Details%20Page/readme.md">3 Details Page</a>
