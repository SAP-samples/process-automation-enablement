Previous Step: <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Apps/3%20Details%20Page/3_2%20Logic%20Building%20for%20Scan%20button/Readme.md"> 3_2 Logic Building for Scan button </a>



# Logic Building for Submit button

1. Open the logic composer for Submit button. 
   select the <b>Submit</b> button and click on the grey bar to open the logic composer.
   
![Submit](Images/01.png)

2. Drag and drop a <b>Toast</b> component to the logic canvas and connect it with previous <b>Create record </b> component. <br>
Give the following input under <b>Toast message</b>
	<pre>Your invoice has been submitted successfully</pre>

![Submit](Images/02.png)	

3. Drag and drop a <b>Open Page</b> logic component to the logic canvas and connect it with the previos <b>Create record</b> component. <br>
Change the page to <b>Home Page</b>.

![Submit](Images/03.png)

4. The Final logic should look like this.
![Submit](Images/04.png)

Now you can test the application. by following next step <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Apps/3%20Details%20Page/3_4%20Run%20Application/readme.md"> Run Application</a>
