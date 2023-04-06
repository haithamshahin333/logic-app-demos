# Steps to Deploy Kubernetes Version Monitor

1. Create a new logic app:
    - You can create a new plan or use an existing plan
    - Since this will run as a recurring trigger, public access can be turned off

    ![Logic App Create - Basics Tab](./images/logicapp-create-basics.png)

    ![Logic App Create - Networking Tab](./images/logicapp-create-networking.png)

2. Create a workflow in the logic app and copy and paste the `workflow.json` contents:

    ![Logic App Create Workflow](./images/logicapp-create-workflow.png)

    ![Logic App Copy Code](./images/logicapp-create-workflow-code.png)

3. Copy and update the parameters for your workflow using `parameters.json`:

    ![Logic App Create Parameters](./images/logicapp-create-parameters.png)

4. Assign a role to the logic app managed identity to read the resource group containing the monitoring AKS Cluster:

    ![Logic App Managed Identity](./images/logicapp-create-identity.png)

    ![Logic App Assign Role](./images/logicapp-assign-reader-role.png)

5. As a last step, manually add a send email action so you can receive a notification in your email with the response:

    ![Logic App Create Email](./images/logicapp-create-email.png)

6. You can test by triggering the workflow and you should receive an email in your inbox