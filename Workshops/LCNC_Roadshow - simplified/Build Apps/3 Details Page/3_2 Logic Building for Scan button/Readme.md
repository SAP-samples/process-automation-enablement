Previous Step: <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Apps/3%20Details%20Page/3_1%20UI%20Building%20for%20Details%20page/Readme.md"> 3.1 UI Building for Details Page</a>.


# Logic Building for Scan Button


1. Open the logic composer for the <b>Scan/Upload</b> button by click on the grey bar in the bottom.<br><br>
![Scan](Images/15N.png)

2. By default, the trigger event will be <b>Component tap</b>.<br>Now we are going to download a new component from the <b>MARKETPLACE</b>.<br>
<b>MARKETPLACE</b> contains hundreds of pre-built visual and logic components, which can be installed and used with minimum or no customisation. <br>
more information on <a href="https://docs.appgyver.com/docs/marketplace?highlight=Market%20place">MARKETPLACE</a><br><br>
![Scan](Images/01.png)

3. In the search bar, search for “<i>action sheet</i>”.<br> Now, select the <b>Action</b> Sheet component.<br><br>
![Scan](Images/02.png)

4. Click <b>Install</b> button to install this component in your library.
<br>
<b>Action Sheet</b>, will allow users to select a value from a list of <b>label-value</b> pairs. In this scenerio, we will this component to give users a list of actions,(i.e., to <b>Scan</b> or to <b>Upload</b>) and trigger the relative logic in the app based on the action selected by the user. <br><br>
![Scan](Images/03.png)

5. You can see the <b>Action sheet</b> component, now available under <b>INSTALLED</b> tab of the logic component library.
 <br>Drag and drop the <b>Action sheet component</b> to logic canvas.<br><br>
 ![Scan](Images/04.png)
 
6. Connect the nodes of <b>Component tap</b> and <b>Action sheet</b>. <br><br>
Now, select <b>Action sheet</b> and open the binding menu for the <b>Action sheet options</b> under the component’s properties on the right-hand side. <br><br>
![Scan](Images/05.png)

7. In the binding menu, select <b>List of values</b>.<br><br>
![Scan](Images/06.png)

8. Click on <b>Add a value</b>.<br><br>
![Scan](Images/07.png)

9. Under the <b>label</b> enter “<i>Scan Invoice</i>” and under <b>value</b> enter “<i>image</i>”.<br><br>
![Scan](Images/08.png)

10. Now <b>Add another value</b>. Enter “<i>Upload Invoice</i>” under <b>label</b> and “<i>upload</i>” under <b>value</b><br>
and click on <b>SAVE</b>.<br><br>
![Scan](Images/09.png)

11. We can use a <b>If Condition</b> to define a flow based on the option selected in the <b>Action sheet</b>.
 Drag and drop the <b>If condition</b> logic component which is available under <i>UTILITY</i> in the logic component library on the left-hand side.<br><br>
![Scan](Images/10.png)

12. Connect the logic nodes of <b>Action sheet</b> and <b>If condition</b>. Open the binding menu for the
Condition of the <b>If condition</b> logic component.<br><br>
![Scan](Images/11.png)

13. In the binding menu, select <b>Formula</b>.<br><br>
![Scan](Images/12.png)

14. Open the formula editor.<br> Select <b>Output of another node</b> and double click on
<b>outputs["Action sheet"].pickedAction.value</b> to use the function in your formula.
Now add, the following in the formula.<pre>==”image”</pre> 
The formula should look like.<pre>outputs["Action sheet"].pickedAction.value=="image"</pre>
Click on <b>SAVE</b> button.<br><br>
![Scan](Images/13.png)

15. The <b>If condition</b> node has two output nodes. The first node is for True case and the second node is for false case.<br>
Now drag and drop <b>Take photo</b> logic component under available under <b>DEVICE</b> in the logic component library on the left-hand side.<br>
Now connect the first output node of <b>If condition</b> to the <b>Take photo</b>.<br><br>
![Scan](Images/14.png)

16. Now open <b>Marketplace</b> and search for “<i>pick image</i>”.
Now select <b>Pick image from library</b> and  Click on <b>INSTALL</b> to use the component.<br><br>
![Scan](Images/15.png)

18. Drag and drop the <b>Pick image from library</b> under Installed tab to the logic canvas.<br>
Connect the second output node of the <b>If condition</b> logic component with the <b>Pick image
from library</b>. <br><br>
![Scan](Images/16.png)

19. From the Core tab of the component library drag and drop the two <b>Set page variable</b> components.<br><br>
![Scan](Images/17.png)

20. Connect one <b>Set page variable</b> with <b>Take photo</b> and other <b>Set page variable</b> with <b>Pick
image from library</b>.<br><br>
![Scan](Images/18.png)

21. Open the binding menu for <b>Assigned value</b> of the <b>Set page variable</b> connected with <b>Take photo</b>.<br><br>
![Scan](Images/19.png)

22. In the binding menu, select <b>Output value of another node</b>.<br><br>
![Scan](Images/20.png)

23. Select <b>Take photo</b>.<br><br>
![Scan](Images/21.png)

24. Select <b>path</b> and click on <b>SAVE</b>.<br><br>
![Scan](Images/23.png)

25. Make sure the page variable here is <b>InvoiceScan</b>.<br><br>
![Scan](Images/Screenshot%202022-09-29%20at%2002.55.58.png)

26. Now open the binding menu for <b>Set page variable</b> logic which is connected with the <b>Pick image from library</b> logic.<br><br>
![Scan](Images/24.png)

27. Select <b>Output value of another node</b>.<br><br>
![Scan](Images/25.png)

27. Select <b>Pick image from library</b> node.<br><br>
![Scan](Images/26.png)

28. Now select <b>path</b> and click on <b>SAVE</b>.<br><br>
![Scan](Images/27.png)

28. Click on <b>SAVE </b> again.<br><br>
![Scan](Images/28.png)

29. Make sure the page variable here is <b>InvoiceScan</b>. If not change it to <b>InvoiceScan</b>.<br><br>
![Scan](Images/Screenshot%202022-09-22%20at%2003.16.57.png)

30. The logic for <b>SCAN/UPLOAD</b> button should like this.<br><br>
![Scan](Images/Screenshot%202022-09-29%20at%2003.02.22.png)

  Next Step: <a href="https://github.com/SAP-samples/process-automation-enablement/blob/main/Workshops/LCNC_Roadshow%20-%20simplified/Build%20Apps/3%20Details%20Page/3_3%20Logic%20Building%20for%20Submit%20Button/readme.md"> 3_3 Logic Building for Submit Button</a>

