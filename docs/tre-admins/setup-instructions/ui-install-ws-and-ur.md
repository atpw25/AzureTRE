# Installing workspace service and user resource

## Publish and register a workspace service template

We will use the [Guacamole workspace service bundle](../../tre-templates/workspace-services/guacamole.md) for the purposes of this tutorial. These steps can be repeated for any workspace service template.

Run:

    ```cmd
    make bundle-publish DIR=$AZURETRE_HOME/templates/workspace_services/guacamole BUNDLE_TYPE=workspace_service
    make bundle-register DIR=$AZURETRE_HOME/templates/workspace_services/guacamole BUNDLE_TYPE=workspace_service
    ```


## Publish and register a user resource template

The Guacamole workspace service also has user resources, there are the VMs that researchers will deploy. These steps can be repeated for any user resource template.

Run:

    ```cmd
    make bundle-publish DIR=$AZURETRE_HOME/templates/workspace_services/guacamole/user_resources/guacamole-azure-windowsvm BUNDLE_TYPE=user_resource
    make bundle-register DIR=$AZURETRE_HOME/templates/workspace_services/guacamole/user_resources/guacamole-azure-windowsvm BUNDLE_TYPE=user_resource WORKSPACE_SERVICE_NAME=tre-service-guacamole
    ```

## Creating a workspace service

Now that we have published and registered both workspace service and user resource bundles we can use the UI to create a workspace service in our workspace.

1. In the UI go to the workspace you have created in the previous step and click on `Create New` under Workspace Services:

    ![Create Workspace Service](../../assets/create-workspace-service-new.png)
2. Choose the Guacamole (Vurtual Desktop) template:
    ![Choose Workspace Service Template](../../assets/create-workspace-service-choose-template.png)
3. Fill in the details:
    ![Fill Workspace Service Details](../../assets/create-workspace-service-details.png)
4. Go to operations tab and wait till the status is deployed:
    ![Workspace Service Status](../../assets/create-workspace-service-status.png)

## Creating a user resource

Having published and registered the user resource bundles and a Guacamole workspace service is deployed we can now create the VM user resource the researcher can connect and work on.

To create a VM user resource follow the next steps:

1. Inside the Guacamole workspace service created in a previous step, go to Resources and click on `Create New`:
    ![Create User Resource](../../assets/create-user-resource-new.png)
1. Select the VM template and click on `Create`:
    ![Select User Resource Template](../../assets/create-user-resource-template.png)
1. Fill in the details and click on `Submit`:
    ![Fill VM details](../../assets/create-user-resource-fill-details.png)
1. Go to the reource:
    ![Go to resource](../../assets/create-user-resource.png)
1. Wait until the status is deployed. Once deployed you can connect to the VM:
    ![VM status](../../assets/create-user-resource-status.png)
