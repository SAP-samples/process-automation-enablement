Two destinations have been used in this scenario.<br>
- One destination to connect SAP Build Process Automation with SAP Build Apps.
- The other to retrieve document from SAP Document Management Service to SAP Process Automation Service.

Due to time constraints, destinations have been pre-configured in this tenant. Below you can find the configuration settings.

1. Destination to connect SAP Build Process Automation with SAP Build Apps.

Enter this value under URL: <pre>https://spa-api-gateway-bpi-eu-prod.cfapps.eu10.hana.ondemand.com/public/workflow/rest/v1/workflow-instances</pre>

Change the authentication to <b>OAuth2ClientCredentials</b>. Client ID, Client Secret and Token Service URL can be retrieved from the SAP Build Process Automation Instance from your tenant.

Add these Additional Properties for this destination to work in SAP Build Apps.

<b>AppgyverEnabled</b><br>
<b>HTML5.DynamicDestination</b><br>
<b>WebIDEEnabled</b>

![](images/Screenshot%202022-10-28%20at%2013.23.50.png)

2. Destination to connect SAP Document Management Service to SAP Process Automation Service.

Change the authentication to <b>OAuth2ClientCredentials</b>. Client ID, Client Secret and Token Service URL can be retrieved from the Document Management Service Instance from your tenant.

Add these Additional Properties for this destination to work in SAP Build Process Automation:

<b>sap.processautomation.enabled<b>

![](images/Screenshot%202022-10-28%20at%2013.24.47.png)
