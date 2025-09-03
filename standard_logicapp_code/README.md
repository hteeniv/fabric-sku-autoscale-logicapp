### Make Sure to Have a Test Workflow First to Create the Necessary API Connections

### After you create the test workflow, a connections JSON will be created automatically by the system once you save the test workflow. Please refer to the connections code to compare.

## The Fabric Autoscale code relies on API connections to the following services:

- ARM (Azure Resource Manager): This is used to read the Fabric SKU. A system-assigned managed identity is preferred for this connection.
- Power BI (Fabric Semantic Model Connection): This queries the total CUs for the past 6 minutes, which includes 12 data points.
- Office 365: For sending error notifications via emails.
- Teams: For sending the SKU details every 6 minutes.
 
# Please follow the steps below to modify the Logic App code before deploying it in your Logic App:

1. ARM Connections:

    - Lines 647, 735, 755: Please modify the code with your Fabric SKU details as mentioned.

2. Office 365 Connections:

    - Lines 671, 672, 673, 776, 777, 778, 799, 800, 801, 867, 868, 869, 1458, 1459, 1460: Please modify them to your Outlook email ID, subject, and body of the email.

3. Teams Connection:

    - Lines 713, 714, 716: Please modify with your Teams group ID, channel ID, and modify the message if needed.

4. Power BI Connections:

    - Line 1381: Please modify with your Fabric metrics app group ID and dataset ID. You can find this on the weblink when you click on the semantic model in your Fabric Capacity Metrics workspace within Power BI.


# The connections.json file is just a reference of how your connections JSON view looks once it is created. You can find this under Workflows -> Connections -> JSON View under your Standard Logic App.

Once you have created the test workflow and saved it successfully, all the connections will be automatically created.

By following these steps, you can ensure that the Fabric autoscale code is properly configured and connected to all necessary services, enhancing its reliability and effectiveness.