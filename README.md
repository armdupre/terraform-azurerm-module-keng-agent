# module-keng-agent/azurerm

## Description
Terraform module for KENG agent deployment on Microsoft Azure

## Deployment
This module creates a single instance having five network interfaces.

## Usage
```tf
module "Agent" {
	source  = "armdupre/module-keng-agent/azurerm"
	Eth0SubnetId = module.Vnet.PublicSubnet.id
	Eth1SubnetId = module.Vnet.Private1Subnet.id
	Eth2SubnetId = module.Vnet.Private2Subnet.id
	Eth3SubnetId = module.Vnet.Private3Subnet.id
	Eth4SubnetId = module.Vnet.Private4Subnet.id
	ResourceGroupName = azurerm_resource_group.ResourceGroup.name
	SshKeyName = azurerm_ssh_public_key.SshKey.name
}
```