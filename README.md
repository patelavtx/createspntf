# Launch an Aviatrix Controller and CoPilot in Azure

## Description
1
Makefile
README.md
backend.org
ignore.gitignore
main.tf
modules
outputs.tf
requirements.txt
sample_vars
variables.tf
versions.tf
It also creates the Aviatrix CoPilot in the same VNET/Subnet as the controller

## Prerequisites

1. [Terraform v0.13+](https://www.terraform.io/downloads.html) - execute terraform files
2. [Python3](https://www.python.org/downloads/) - execute `accept_license.py` and `aviatrix_controller_init.py` python
   scripts

## Providers

| Name | Version |
|------|---------|
| <a name="provider_azuread"></a> [azuread](#provider\_azuread) | ~> 2.0 |
| <a name="provider_azurerm"></a> [azurerm](#provider\_azurerm) | \>= 2.0 |
| <a name="provider_null"></a> [null](#provider\_null) | \>= 2.0 |


## Available Modules

Module  | Description |
| ------- | ----------- |
|[aviatrix_controller_azure](modules/aviatrix_controller_azure) |Creates Azure Active Directory Application and Service Principal for Aviatrix access account setup |
|[aviatrix_controller_build](modules/aviatrix_controller_build) |Builds the Aviatrix Controller VM on Azure |
|[aviatrix_controller_initialize](modules/aviatrix_controller_initialize) | Initializes the Aviatrix Controller (setting admin email, setting admin password, upgrading controller version, and setting up access account) |
|[az_copilot](modules/az_copilot) | Builds the Aviatrix CoPilot in the same VNET/Subnet as the controller |

## Procedures for Building and Initializing a Controller in Azure

### 1. Create the Python virtual environment and install required dependencies

Create the virtual environment.

``` shell
 python3 -m venv venv
```

Activate the virtual environment.

``` shell
 source venv/bin/activate
```

Install required dependencies.

``` shell
 pip install -r requirements.txt
```

### 2. Authenticating to Azure

Please refer to the documentation for
the [azurerm](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs)
and [azuread](https://registry.terraform.io/providers/hashicorp/azuread/latest/docs) Terraform providers to decide how
to authenticate to Azure.

``` shell
az login
az account set --subscription <subscription_id>
```

### 3. Applying Terraform configuration

Build and initialize the Aviatrix Controller and the CoPilot


*Execute*

```shell
terraform init
terraform apply
```
# bekaert
# createspntf
