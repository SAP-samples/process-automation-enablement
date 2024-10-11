# 3. Integrate an SAP Build Apps application into SAP Build Work Zone, advanced edition


## Access SAP Build Work Zone, advanced edition  
&nbsp;  
Click [Lobby](https://sap-build-academy-eu10.eu10.build.cloud.sap/lobby) to open the entry page of SAP Build.  
&nbsp;  
1. Click **Create** to see what you can build in SAP Build.  
&nbsp;  
![1](https://media.github.tools.sap/user/67204/files/8a2505b9-cd8f-44a1-80bd-e71f07421dd2)  
&nbsp;  
2. Click **Build a Business Site**.  
&nbsp;  
![2](https://media.github.tools.sap/user/67204/files/5a06270b-9272-4e70-9dc5-9dec3f8e4a9c)  
&nbsp;  
3. Click **Manage Pages and Workspaces**.  
&nbsp;  
![3](https://media.github.tools.sap/user/67204/files/63eaa0f3-3fdf-4af1-8357-d25bb3441840)  
&nbsp;  
You should end up in this screen:  
&nbsp;  
![WZ1](https://media.github.tools.sap/user/20498/files/f26548ca-ca62-490f-be8a-25006b40b911)
&nbsp;  
&nbsp;  
## Create your workspace  
&nbsp;  
Workspaces are the building blocks of SAP Build Work Zone, advanced edition. You can add all kinds of content to your workspace and you can invite other users to join as members.  
&nbsp;  
1. In your site, click **Workspaces** in the top-level menu, and then click **New Workspace**. You can also use the **New Workspace** button on the right.  
&nbsp;  
![WZ1](https://media.github.tools.sap/user/20498/files/babcd093-4dc4-4005-ab05-50e880be78e0)  
&nbsp;  
2. Choose **Private Workspace** from the workspace type options:  
&nbsp;  
![6](https://media.github.tools.sap/user/67204/files/41957fae-1863-48aa-ba64-9703ec9b6118)  
&nbsp;  
3. Enter this name for your workspace (replace **XX** with the last 2 digits of your user name):  
	```
	Sales Management AC099201UXX
	```
4. Copy and paste this description for your workspace: 
	```
	Use this workspace to manage your team's sales orders and to collaborate.
	```
&nbsp;  
5. Use the **value help** button to open the available templates, then scroll to the end of the list and select **No Template**.  
&nbsp;  Click **Finish**.  
&nbsp;  
![7](https://media.github.tools.sap/user/67204/files/ae0f0565-7930-4e8f-933b-7d26c9be44e6)
&nbsp;  
7. Click **Accept** if the popup appears.  
&nbsp;  
![8](https://media.github.tools.sap/user/67204/files/a36b3e32-2627-4297-86a5-97ebcf3b4df3)
&nbsp;  
8. Your workspace was created and it's ready for you to add design and content elements.  
&nbsp;  
![9](https://media.github.tools.sap/user/67204/files/b0203f28-f2f8-4084-a56a-b28883ccd746)  
&nbsp;  
&nbsp;  
## Create a workpage for your workspace  
&nbsp;  
In this step, you’ll add a workpage to your workspace - this workpage will describe the purpose of the workspace and will feature relevant content.  
&nbsp;  
1. Click **+** to add a page tab.  
&nbsp;  
![WZ2](https://media.github.tools.sap/user/20498/files/790b3f0c-7a97-4739-bd71-3ea61a57335a)  
&nbsp;  
2. Select the **Workpage** tile.  
&nbsp;  
![11](https://media.github.tools.sap/user/67204/files/37e47bcb-d5bb-4dcd-89f4-e0ec0d087b40)  
&nbsp;  
3. Enter a title for the workpage: 
	```
	Sales Orders
	```
4. Select **New Workpage** as the type and click **Add**.  
&nbsp;  
![12](https://media.github.tools.sap/user/67204/files/3e34c23c-76ac-4460-a939-098779b023ef)
&nbsp;  
5.  Scroll to the top of your page and click **Publish**.  
&nbsp;  
![WZ3](https://media.github.tools.sap/user/20498/files/8ef981d3-844b-472b-8e46-49f192ee615d)
&nbsp;  
Click again on **Publish** if you see this popup  
&nbsp;  
![WZ4](https://media.github.tools.sap/user/20498/files/e2c169b3-fbea-4178-af9d-9d7e5094b8e4)
&nbsp;  
Your workpage creation has been finished. You can now start to design the content in your workspace!  
&nbsp;  
&nbsp;  
## Add a header for your most frequently used apps  
&nbsp;  
Before you add the build app to your workspace, first add a header for a section where you will add the most frequently used apps.  
&nbsp;  
1. Click the pencil icon to open the **Page Designer**.  
&nbsp; 
![WZ5](https://media.github.tools.sap/user/20498/files/0160d546-ff42-49b0-bfd7-fa6024042fee)
&nbsp; 
2. Click on **Add section**  
&nbsp; 
![WZ8](https://media.github.tools.sap/user/20498/files/61f6925d-e3c7-4d78-9c5f-2268cb976ad2)
&nbsp; 
3. Click **Add Widget** to open the widget gallery.  
&nbsp;  
![WZ6](https://media.github.tools.sap/user/20498/files/b480fb53-5578-40b3-9279-0e48529478b3)  
&nbsp;  
4. Select the **Text** widget and design it as follows:  
&nbsp;  
	| Text | Type in: *Most Popular Apps* |
	| :------------------- | :---------- |
	| Font     | Select the text and change to Arial 14pt   | 
	| Color    | With the text still selected, choose the color black from the chart |  
&nbsp;  
![24](https://media.github.tools.sap/user/67204/files/576343dc-91b8-4189-aa61-e39dd2502148)  
&nbsp;  
Next, you’re going to add your app under this header.  
&nbsp;  
## Add a build app to the workspace  
&nbsp;  
Now it's time to complete and publish your workspace.  
&nbsp;  
1. Add another section below the existing one, by clicking on **+**.  
&nbsp;  
![26](https://media.github.tools.sap/user/67204/files/6a0b0279-8358-4be8-a46f-e90a204c2bf7)  
&nbsp;  
2. Click **Add Widget** within the new section.  
&nbsp;  
![27](https://media.github.tools.sap/user/67204/files/fbc5ccd4-32df-487d-b4ea-617adad0821a)  
&nbsp;  
3. Click **Tiles** in the widget gallery.  
&nbsp;  
![28](https://media.github.tools.sap/user/67204/files/cc9b6f98-4198-4875-9b7b-2e5e51e64c08)  
&nbsp;  
4. In the search box, select the **TA - Sales Order Build App** app, and then click **Add**.  
If you do not see your App appear when searching, please refresh the page and try again.  
&nbsp;  
![30+](https://media.github.tools.sap/user/67204/files/e497702a-ca5d-472d-a42e-5d76b0a71245)
&nbsp;  
5. After adding the App, the view looks like the image shown below.  
&nbsp;  
![31](https://media.github.tools.sap/user/67204/files/cd0f448c-8429-47a2-b4c7-7397cbf3ff90)
&nbsp;  
6. Scroll to the top of your page and click **Publish**.  
&nbsp;  
![33](https://media.github.tools.sap/user/67204/files/12f13a9b-e999-4e8b-8288-5ed32e6ec9ca)  
&nbsp;  
This is how your workspace looks like - note that the **TA - Sales Order Build App** app is under the header that you created:   
&nbsp;  
![WZ9](https://media.github.tools.sap/user/20498/files/afa0ee57-b968-4377-bc37-27f43ca4dfaf)  
&nbsp;  
Note that with some preparations (https://community.sap.com/t5/sap-builders-blog-posts/tips-to-add-your-sap-build-apps-application-to-different-btp-environments/ba-p/13631104), in a similar way it is also possible to add the build app that you created previously to this Space.
&nbsp;  
&nbsp;  
Congratulations! You successfully completly the exercises :)
