# Azure Arc Overview

For customers who want to simplify complex and distributed environments across on-premises, edge and multi-cloud, [Azure Arc](https://azure.microsoft.com/en-us/services/azure-arc/) enables deployment of Azure services anywhere and extends Azure management to any infrastructure.

* **Organize and govern across environments** - Get databases, Kubernetes clusters, and servers sprawling across on-premises, edge and multi-cloud environments under control by centrally organizing and governing from a single place.

* **Manage Kubernetes Apps at scale** - Deploy and manage Kubernetes applications across environments using DevOps techniques. Ensure that applications are deployed and configured from source control consistently.

* **Run data services anywhere** - Get automated patching, upgrades, security and scale on-demand across on-premises, edge and multi-cloud environments for your data estate.

# Azure Arc Jumpstart

The following guides will walk you trough on how to demo and get started with Azure Arc. They are designed with a "zero to hero" approach in mind and with much automation as possible. The goal is for you to have a working Azure Arc demo environment spined-up in no time so you can focus on showing the core values of the solution.

**Disclaimer: The intention for this repo is to focus on the core Azure Arc capabilities. deployment scenarios, use-cases and ease of use. It does not focus on Azure best-practices or the other tech and OSS project being leveraged in the guides and code.**

# Azure Arc Story Time

Fabrikam Global Manufacturing runs workloads on different hardware, across on-premises datacenters, and multiple public clouds, with Microsoft Azure being the primary cloud. They also support IoT workloads deployed on the edge. Workloads include very diverse services and are based on either virtual machines, managed Platform-as-a-Service (PaaS) services, and container-based applications. 
 
As mentioned, Fabrkam’s R&D teams are well-invested in containerized workloads for their modernized applications and as a result, they are using Kubernetes as their container orchestration platform, deployed both as a self-managed Kubernetes in their on-premises environments and managed Kubernetes deployments in the cloud.

As part of their cloud-native practices with Azure being the main hyper-scale cloud, Fabrkam’s operations teams are standardized and taking advantage of Azure Resource Manager (ARM) capabilities such as (but not limited to) tagging, Azure Monitoring for VMs and containers, logging and telemetry, policy and government, Desired State Configuration (DSC), Update Management, Change Tracking, Inventory management,etc. 

These practices and techniques are already well established for Azure-based workloads in use such as Azure VMs, Azure Kubernetes Service (AKS), Azure SQL, and many more. In order to take advantage of these well-established practices, Fabrkam are using Azure Arc to extend the ARM API’s to project and manage their workloads deployed outside of Azure. Once onboarded, Azure Arc projects resources as first-class citizens in Azure which can then take advantage of ARM capabilities mentioned above. In addition, they are able to guarantee Kubernetes deployments and app consistency through GitOps-based configuration for their Kubernetes clusters in Azure, other clouds and on-premises. 
 
With Azure Arc, Fabrikam are able to project resources and register them into Azure Resource Manager independently of where they run, so they have a single control plane and extend those cloud-native operations and governance beyond Azure.

<p align="center">
  <img src="img/architecture_white.png" width="90%"/>
</p>

## DEMO - Azure Arc enabled Servers

The below deployment scenarios will guide you through onboarding various Windows and Linux server deployments to Azure with Azure Arc. 

**Note: For a list of supported operating systems and Azure regions, please visit the official [Azure Arc docs](https://docs.microsoft.com/en-us/azure/azure-arc/servers/overview).**

**Disclaimer: Azure Arc enabled Servers is currently in Public Preview.**

#### Step 1 - creating virtual machines and connecing to Azure Arc

The following examples can be used to connect existing Windows or Linux servers to Azure with Azure Arc. Use these if you already have existing servers that you want to project into Azure. however if you don't have servers to use for the lab , you would need to create them first. as a prerequiste you will need to create a Resouce group on azure and deploy a windows and linux server in that resource group , this will mimic connecting on-premises virtual machines to azure Arc. please create both the windows and linux virtual machines before using the below links to connect the virtual machines to Azure Arc

##### creating virtual machines 
you can use the below guide to create a virtual machine on azure 

* [Creating an ubuntu linux virtual machine on azure](https://docs.microsoft.com/bs-cyrl-ba/azure/virtual-machines/linux/quick-create-portal)

* [Creating a Windows virtual machine on azure](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/quick-create-portal)

##### connecting the virtual machines to Azure Arc

The script to automate the download and installation, and to establish the connection with Azure Arc, is available from the Azure portal. To complete the process, follow the following links:

* [Recommended : Connect an existing Windows and linux server to Azure Arc using scripted and manual method](https://docs.microsoft.com/en-us/azure/azure-arc/servers/onboard-portal)

* [Optional : Connect an existing Linux server to Azure Arc - Scripted method 'Additional Reference'](azure_arc_servers_jumpstart/docs/onboard_server_linux.md)

* [Optional : Connect an existing Windows machine to Azure Arc - Scripted method 'Additional Reference'](azure_arc_servers_jumpstart/docs/onboard_server_win.md)

#### Step 2 - Azure Arc enabled Servers - Scenarios & Use-Cases

Once you have server resources projected into Azure with Azure Arc, you can start to use native Azure tooling to manage the servers as native Azure resources. The following guides show examples of using Azure management tools such as resource tags, Azure Policy, Log Analytics, and more with Azure Arc servers.

**Day 1** 
* [Tagging and querying server inventory across multiple clouds using Resource Graph Explorer](azure_arc_servers_jumpstart/docs/arc_inventory_tagging.md)

* [Deploying Microsoft Monitoring Agent Extension (MMA) to Azure Arc Linux and Windows VMs using Azure Policies](azure_arc_servers_jumpstart/docs/arc_policies_mma.md)
 
* [Azure Arc enabled Servers on Azure Security Center](azure_arc_servers_jumpstart/docs/arc_securitycenter.md)

**Day 2**
* [Deploying Microsoft Monitoring Agent Extension (MMA) to Azure Arc Linux and Windows VMs using Extension Management](azure_arc_servers_jumpstart/docs/arc_vm_extension_mma_arm.md)

* [Deploying Custom Script Extension to Azure Arc Linux and Windows VMs using Extension Management](azure_arc_servers_jumpstart/docs/arc_vm_extension_customscript_arm.md)

* [Integrate Azure Sentinel with Azure Arc enabled Servers](azure_arc_servers_jumpstart/docs/arc_azuresentinel.md)

# Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

Before contributing code, please see the [CONTRIBUTING](CONTRIBUTING.md) guide.

Issues, PRs and Feature Request have their own templates. Please fill out the whole template.

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
