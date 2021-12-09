Objective : Deploying a Kubernates cluster in Azure
Commands : 
1 . 

## az group create --name AZ-K8s --location eastus

	 *This will create a resource group named "AZ-K8s*
2. 

## az aks create --resource-group AZ-K8s --name my-k8s-cluster1 --node-count 1 --node-vm-size Standard_B2s --generate-ssh-keys
*minimum mandatory commands to deploy the k8s cluster 
cluster name , node count, vm size and ssh keys generation is required as it may be required to login into the pod*

**output of the command**     
{
  "aadProfile": null,
  "addonProfiles": null,
  "agentPoolProfiles": [
    {
      "availabilityZones": null,
      "count": 1,
      "enableAutoScaling": false,
      "enableEncryptionAtHost": false,
      "enableFips": false,
      "enableNodePublicIp": false,
      "enableUltraSsd": false,
      "gpuInstanceProfile": null,
      "kubeletConfig": null,
      "kubeletDiskType": "OS",
      "linuxOsConfig": null,
      "maxCount": null,
      "maxPods": 110,
      "minCount": null,
      "mode": "System",
      "name": "nodepool1",
      "nodeImageVersion": "AKSUbuntu-1804gen2containerd-2021.11.06",
      "nodeLabels": null,
      "nodePublicIpPrefixId": null,
      "nodeTaints": null,
      "orchestratorVersion": "1.20.9",
      "osDiskSizeGb": 128,
      "osDiskType": "Managed",
      "osSku": "Ubuntu",
      "osType": "Linux",
      "podSubnetId": null,
      "powerState": {
        "code": "Running"
      },
      "provisioningState": "Succeeded",
      "proximityPlacementGroupId": null,
      "scaleDownMode": null,
      "scaleSetEvictionPolicy": null,
      "scaleSetPriority": null,
      "spotMaxPrice": null,
      "tags": null,
      "type": "VirtualMachineScaleSets",
      "upgradeSettings": null,
      "vmSize": "Standard_B2s",
      "vnetSubnetId": null
    }
  ],
  "apiServerAccessProfile": null,
  "autoScalerProfile": null,
  "autoUpgradeProfile": null,
  "azurePortalFqdn": "my-k8s-clu-az-k8s-953f8d-eaf75f4a.portal.hcp.eastus.azmk8s.io",
  "disableLocalAccounts": false,
  "diskEncryptionSetId": null,
  "dnsPrefix": "my-k8s-clu-AZ-K8s-953f8d",
  "enablePodSecurityPolicy": null,
  "enableRbac": true,
  "extendedLocation": null,
  "fqdn": "my-k8s-clu-az-k8s-953f8d-eaf75f4a.hcp.eastus.azmk8s.io",
  "fqdnSubdomain": null,
  "httpProxyConfig": null,
  "id": "/subscriptions/953f8dc1-d0cf-4078-9761-0efcb55e64f5/resourcegroups/AZ-K8s/providers/Microsoft.ContainerService/managedClusters/my-k8s-cluster1",
  "identity": {
    "principalId": "0a8af01e-842f-430e-a974-7bee16735f8f",
    "tenantId": "a2c99a11-9c0f-47cc-a52c-63738b0a5269",
    "type": "SystemAssigned",
    "userAssignedIdentities": null
  },
  "identityProfile": {
    "kubeletidentity": {
      "clientId": "f1da76f1-883a-4a57-93c8-c72ca9842a9e",
      "objectId": "658b4a02-8662-4c21-a578-a2b1679bc905",
      "resourceId": "/subscriptions/953f8dc1-d0cf-4078-9761-0efcb55e64f5/resourcegroups/MC_AZ-K8s_my-k8s-cluster1_eastus/providers/Microsoft.ManagedIdentity/userAssignedIdentities/my-k8s-cluster1-agentpool"
    }
  },
  "kubernetesVersion": "1.20.9",
  "linuxProfile": {
    "adminUsername": "azureuser",
    "ssh": {
      "publicKeys": [
        {
          "keyData": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCfDYXSdW9CXsAoa8ENkc+mU9RrT3zal9TYGeAB3sZw8ZBgiha3BGtQOZjY5c1Ww/X5Sq8rU6vALV4xLZBlCGM5/mF20Cf8nw23EuiW45UFbC50gmcWg8Wzmlp+IGRh2EkCPkcIX1ypOkJnYIGlGz9MstHdl9Qz1aNDGSCJYOxbBAwilwUdUFyZWgN4OcScLVun/VNCvfYGnJjKuPdWi2zwxPDJ0eLA8hARHEoXMmmrF9eMMLvD13+YgIKMMo9osZ1L1rKsKnWMjtz28QviVaFel/8a2jl78vA1UFeSjG560lCVqB+AmDGbGrrCNcIS8Df+Fxx+S7qCK8XvrTAsLBXd"
        }
      ]
    }
  },
  "location": "eastus",
  "maxAgentPools": 100,
  "name": "my-k8s-cluster1",
  "networkProfile": {
    "dnsServiceIp": "10.0.0.10",
    "dockerBridgeCidr": "172.17.0.1/16",
    "loadBalancerProfile": {
      "allocatedOutboundPorts": null,
      "effectiveOutboundIPs": [
        {
          "id": "/subscriptions/953f8dc1-d0cf-4078-9761-0efcb55e64f5/resourceGroups/MC_AZ-K8s_my-k8s-cluster1_eastus/providers/Microsoft.Network/publicIPAddresses/b24d4b95-7afb-4b9c-8c6a-30f83b56f65b",
          "resourceGroup": "MC_AZ-K8s_my-k8s-cluster1_eastus"
        }
      ],
      "idleTimeoutInMinutes": null,
      "managedOutboundIPs": {
        "count": 1
      },
      "outboundIPs": null,
      "outboundIpPrefixes": null
    },
    "loadBalancerSku": "Standard",
    "natGatewayProfile": null,
    "networkMode": null,
    "networkPlugin": "kubenet",
    "networkPolicy": null,
    "outboundType": "loadBalancer",
    "podCidr": "10.244.0.0/16",
    "serviceCidr": "10.0.0.0/16"
  },
  "nodeResourceGroup": "MC_AZ-K8s_my-k8s-cluster1_eastus",
  "podIdentityProfile": null,
  "powerState": {
    "code": "Running"
  },
  "privateFqdn": null,
  "privateLinkResources": null,
  "provisioningState": "Succeeded",
  "resourceGroup": "AZ-K8s",
  "securityProfile": null,
  "servicePrincipalProfile": {
    "clientId": "msi",
    "secret": null
  },
  "sku": {
    "name": "Basic",
    "tier": "Free"
  },
  "tags": null,
  "type": "Microsoft.ContainerService/ManagedClusters",
  "windowsProfile": null
}

**az resource list --output table **
use this command to check the resources created,
P.S : some additional resources will be created go through thoose once.

**az aks get-credentials --resource-group AZ-K8s --name my-k8s-cluster1**

This command merges into current context

lastly run any kubectl commands 
like..
**kubectl get nodes**
