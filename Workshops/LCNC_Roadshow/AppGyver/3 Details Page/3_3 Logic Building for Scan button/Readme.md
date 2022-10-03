Previous Step: <a href="https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow/AppGyver/3%20Details%20Page/3_2%20Data%20Connection/Readme.md"> 3_2 Data Connection for Details Page</a>


# Logic Building for Scan Button


1. Open the logic composer for the <b>Scan/Upload</b> button by click on the grey bar in the bottom

![Scan](Images/15N.png)

2. By default, the trigger event will be <b>Component tap</b>.<br>
Now we are going to download a new component from the <b>MARKETPLACE</b>.

![Scan](Images/01.png)

3. In the search bar, search for “<i>action sheet</i>”.<br> Now, select the <b>Action</b> Sheet component.

![Scan](Images/02.png)

4. Click <b>Install</b> button to install this component in your library.

![Scan](Images/03.png)

5. You can see the <b>Action sheet</b> component, now available under <b>INSTALLED</b> tab of the logic component library.
 <br>Drag and drop the <b>Action sheet component</b> to logic canvas.

 ![Scan](Images/04.png)
 
6. Connect the nodes of <b>Component tap</b> and <b>Action sheet</b>. <br><br>
Now open the binding menu for the <b>Action sheet options</b> under the component’s properties on the right-hand side. 

![Scan](Images/05.png)

7. In the binding menu, select <b>List of values</b>.

![Scan](Images/06.png)

8. Click on <b>Add a value</b>.

![Scan](Images/07.png)

9. Under the <b>label</b> enter “<i>Scan Invoice</i>” and under <b>value</b> enter “<i>image</i>”.

![Scan](Images/08.png)

10. Now <b>Add another value</b>. Enter “<i>Upload Invoice</i>” under <b>label</b> and “<i>upload</i>” under <b>value</b><br>
and click on <b>SAVE</b>.

![Scan](Images/09.png)

11. Drag and drop the <b>If condition</b> logic component which is available under <i>UTILITY</i> in the logic component library on the left-hand side.

![Scan](Images/10.png)

12. Connect the logic nodes of <b>Action sheet</b> and <b>If condition</b>. Open the binding menu for the
Condition of the <b>If condition</b> logic component.

![Scan](Images/11.png)

13. In the binding menu, select <b>Formula</b>.

![Scan](Images/12.png)

14. Open the formula editor.<br> Select <b>Output of another node</b> and double click on
<b>outputs["Action sheet"].pickedAction.value</b> to use the function in your formula.
Now add, the following in the formula.
<pre>==”image”</pre> 
The formula should look like.
<pre>outputs["Action sheet"].pickedAction.value=="image"</pre>
Click on <b>SAVE</b> button.

![Scan](Images/13.png)

15. The <b>If condition</b> node has two output nodes. The first node is for True case and the second node is for false case.<br>
Now drag and drop <b>Take photo</b> logic component under available under <b>DEVICE</b> in the logic component library on the left-hand side.<br>
Now connect the first output node of <b>If condition</b> to the <b>Take photo</b>.

![Scan](Images/14.png)

16. Now open <b>Marketplace</b> and search for “<i>pick image</i>”.
Now select <b>Pick image from library</b> and  Click on <b>INSTALL</b> to use the component.

![Scan](Images/15.png)

18. Drag and drop the <b>Pick image from library</b> under Installed tab to the logic canvas.<br>
Connect the second output node of the <b>If condition</b> logic component with the <b>Pick image
from library</b>. 

![Scan](Images/16.png)

19. From the Core tab of the component library drag and drop the two <b>Set page variable</b> components.

![Scan](Images/17.png)

20. Connect one <b>Set page variable</b> with <b>Take photo</b> and other <b>Set page variable</b> with <b>Pick
image from library</b>.

![Scan](Images/18.png)

21. Open the binding menu for <b>Assigned value</b> of the <b>Set page variable</b> connected with <b>Take photo</b>.

![Scan](Images/19.png)

22. In the binding menu, select <b>Output value of another node</b>.

![Scan](Images/20.png)

23. Select <b>Take photo</b>.

![Scan](Images/21.png)

24. Select <b>path</b> and click on <b>SAVE</b>.

![Scan](Images/23.png)

25. Make sure the page variable here is <b>InvoiceScan</b>.

![Scan](Images/Screenshot%202022-09-29%20at%2002.55.58.png)

26. Now open the binding menu for <b>Set page variable</b> logic which is connected with the <b>Pick image from library</b> logic.

![Scan](Images/24.png)

27. Select <b>Output value of another node</b>.

![Scan](Images/25.png)

27. Select <b>Pick image from library</b> node.

![Scan](Images/26.png)

28. Now select <b>path</b> and click on <b>SAVE</b>.

![Scan](Images/27.png)

28. Click on <b>SAVE </b> again.

![Scan](Images/28.png)

29. Make sure the page variable here is <b>InvoiceScan</b>. If not change it to <b>InvoiceScan</b>.

![Scan](Images/Screenshot%202022-09-22%20at%2003.16.57.png)

30. The logic for <b>SCAN/UPLOAD</b> button should like this.

![Scan](Images/Screenshot%202022-09-29%20at%2003.02.22.png)

  Next Step: <a href="https://github.com/SAP-samples/process-automation-enablement/tree/main/Workshops/LCNC_Roadshow/AppGyver/3%20Details%20Page/3_4%20Logic%20Building%20for%20Submit%20button/Readme.md"> 3_4 Logic Building for Submit Button</a>
