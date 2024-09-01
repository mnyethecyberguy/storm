# Azure CLI

## Authentication

After creating an Azure AD user in the Azure Portal and creating an access key, configure the Azure CLI interactively using browser-based authentication with:

```
az login
```

### Show the signed-in user

```
az ad signed-in-user show
```

Alternatively, you can ensure the CLI is configured properly by running the following command to request a new access token for the currently logged in user:

```
az account get-access-token
```

### CLI Version Details

```
az --version
```

## Filtering and Querying


## Azure Storage 

### Enumerate Storage

Enumerate all storage accounts in an account:

```
az storage account list
```

Enumerate all containers in an Azure storage account:

```
az storage container list --account-name <STORAGE_ACCOUNT_NAME>
```

Enumerate all objects or blobs in a container:

```
az storage blob list --account-name <STORAGE_ACCOUNT_NAME> --container-name <CONTAINER_NAME>
```

### Uploading and Downloading Files from Storage

Uploading

```
az storage blob upload --account-name <STORAGE_ACCOUNT_NAME> --container-name <CONTAINER_NAME> --name file.txt --file file.txt
```

Downloading

```
az storage blob download --account-name <STORAGE_ACCOUNT_NAME> --container-name <CONTAINER_NAME> --name file.txt --file file.txt
```

## Azure Key Vaults

List Azure Key Vaults for a specific resource group

```
az keyvault list --resource-group <RESOURCE_GROUP>
```

Create a new key vault

```
az keyvault create --name <KEY_VAULT_NAME> --resource-group <RESOURCE_GROUP> --location <REGION>
```

Delete a key vault

```
az keyvault delete --name <KEY_VAULT_NAME> --resource-group <RESOURCE_GROUP>
```

## SSH to a Public Cloud VM

```
ssh ubuntu@$(az vm list-ip-addresses --query "[?virtualMachine.name=='<VM_NAME>'].virtualMachine.network.publicIpAddresses[0].ipAddress" --output tsv)
```

## Encrypt and Decrypt Data

