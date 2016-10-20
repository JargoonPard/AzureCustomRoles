# AzureCustomRoles

### Overview

**_Note_** that these files contain an ID for the roles. This ID is generated when the role is created and used for updates to the role.  To create a role using one of these files first remove the "Id" element.  Add the "Id" element back after the role is created in your subscription and provide the Id value assigned by Azure.  

These files also contain a subscription in the "AssignableScopes" section. You will need to replace this with an appropriate value for your subscription.

### Creating and Updating Custom Roles

Create the role in your subscription using the following CLI command:
```
azure role create --inputfile LabAdminNoNetwork.json
```

Update the role using the following command: 
```
azure role set --inputfile LabAdminNoNetwork.json
```

### Roles Descriptions

The "No Network Guy" is a simple role definition to demonstrate how things can be controlled. It lets a user assinged to this role view resource groups and network resources within a resource group but not modify or create networking resources. They are also allowed to perform all actions for compute and storage resources.

The "NetworkRestrictedLabAdministrator" role is defined for an enterprise that needs to control the network configuration within an Azure subscription by the Subscription owners but still needs to assign a DevTest Lab administrator to perform all other actions.  this is typically required when the labs are connected to an enterprise network via VPN or Express Route and modifications to the Azure networks must be done in coordination with the enterprise netwrok address space.
