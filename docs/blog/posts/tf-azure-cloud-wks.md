---
# draft: true
date: 2023-07-21
authors:
  - mnye
categories:
  - Cloud Security
  - Azure
  - Terraform
---

# Deploy a Desktop on Azure Using Terraform

This terraform script deploys an Ubuntu Workstation with minimal additional software installed.  It enables SSH and RDP and uses security groups to restrict the administrative access to your current external IP address only to prevent it being wide open to the world.

An example use case is a temporary sandbox system for surfing potentially dangerous websites.

_NOTE: Don't break the law, as Azure Terms of Service still apply and this is not exactly covert._
<!-- more -->
## Prerequisites
 
- This assumes that you have both `git` and `terraform` installed.
- You also need to have the `az` CLI installed and configured.
- An SSH key pair should be created with the `.pem` file saved locally to reference.

## Deployment

Git clone the repository and provision the cloud workstation by running the following commands, one at a time:

```
git clone https://github.com/mnyethecyberguy/terraform-azure-workstation.git
```
and then

```
cd terraform-azure-workstation
```

Next modify the `terraform.tfvars` contents with the settings that are appropriate for your Azure Account.

Now run these commands:

```
terraform init
terraform apply
```

## Usage

The cloud workstation can be accessed via either SSH or RDP. The necessary information will be an output when the script is complete.

Sample Output:

```
RDP_Password = "Changemenow"
RDP_UserName = "clouduser"
RDP_address = "<your-AzureVM-public-IP>"
ssh_connection_string = "ssh -i ~/cloud_workstation.pem ubuntu@<your-AzureVM-public-IP>"
```

## Teardown

To destroy the workstation and all the resources created in your Azure account run the following command from the repository directory:

```
terraform destroy
```

## Additional Notes

The `temp-workstation.sh` is passed as user data to the instance and runs the first time the system boots. The script generates a log entry for almost every command as it runs and sends it to `/tmp/first-boot.log`

Since the script installs updates and some software, it may take a while. I like to watch the first boot script by watching its log when connected via SSH. Just run:

```
tail -f /tmp/first-boot.log
```

Otherwise, if you are connected via SSH, you will get a system message when the boot script has completed:

```
NOTICE: First Boot Setup Has Completed
```

After that point it is ready for an Remote Desktop (RDP) Connection. Use an RDP client, such as Microsoft Terminal Services Client (MSTSC) to RDP to the IP address that is output by the Terraform script.

**DON'T FORGET TO CHANGE THE RDP PASSWORD AFTER LOGON**

## Customization

This script is configured to deploy the Ubuntu instance as a `Standard_DS1_v2` instance.  This will cost $53.29 per Month according to the [Azure Linux Virtual Machines Pricing Page](https://azure.microsoft.com/en-us/pricing/details/virtual-machines/linux/). If you want to change this, locate the `resource "azurerm_linux_virtual_machine" "temp-workstation"` block in the `main.tf` file and update the `instance_type` argument to a [valid instance type](https://azure.microsoft.com/en-us/pricing/details/virtual-machines/series/). 

The default user created for RDP is named `clouduser` with a password of `Changemenow`.  You can find these settings in the `temp-workstation.sh` shell script, and an Output reference to them in the `main.tf` script.