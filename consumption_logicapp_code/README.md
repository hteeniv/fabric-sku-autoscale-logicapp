### Make Sure to Have a Test Workflow First to Create the Necessary API Connections

## This code relies on API connections to the following services:

- ARM (Azure Resource Manager): This is used to read the Fabric SKU. A system-assigned managed identity is preferred for this connection.
- Power BI (Fabric Semantic Model Connection): This queries the total CUs for the past 6 minutes, which includes 12 data points.
- Office 365: For sending error notifications via emails.
- Teams: For sending the SKU details every 6 minutes.
 
# Please follow the steps below to modify the Logic App code before deploying it in your Logic App:

1. ARM Connections:

    - Lines 641, 758, 778: Please modify the code with your Fabric SKU details as mentioned.

2. Office 365 Connections:

    - Lines 683, 684, 685, 799, 800, 801, 822, 823, 824, 890, 891, 892, 1470, 1471, 1472: Please modify them to your Outlook email ID, subject, and body of the email.

3. Teams Connection:

    - Lines 736, 737, 738: Please modify with your Teams group ID, channel ID, and modify the message if needed.

4. Power BI Connections:

    - Line 1393: Please modify with your Fabric metrics app group ID and dataset ID. You can find this on the weblink when you click on the semantic model in your Fabric Capacity Metrics workspace within Power BI.

5. For all the connections:

    - Lines 1595, 1596, 1605, 1606, 1610, 1611, 1615, 1616: Please modify the subscription IDs, resource group names, and locations of the resources (e.g., eastus).

Once you have created the test workflow and saved it successfully, all the connections will be automatically created. This ensures that the necessary API connections are in place before you deploy the full workflow.

By following these steps, you can ensure that the Fabric autoscale code is properly configured and connected to all necessary services, enhancing its reliability and effectiveness.