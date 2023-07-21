# Building a new image to Azure DevOps self-hosted agents

### Prerequisites
1. Install Packer: https://developer.hashicorp.com/packer/downloads
2. Install Azure CLI: https://learn.microsoft.com/en-us/cli/azure/install-azure-cli

### Building the image
1. Open a terminal
2. Login to Azure CLI by running `az login`
3. Set the correct subscription as the active subscription
   - Set the correct subscription by running `az account set --subscription "Kotipizza Verkkokauppa Shared"`
4. Change directory to `[repo root]/images/linux`
5. Run `packer build -on-error="ask" -var "location=westeurope" -var "resource_group=DevOps-PackerResources" -var "subscription_id=3578ff8c-388e-406b-b198-aa2c648430b7" ubuntu2204.pkr.hcl`. This will generate a new VM image
