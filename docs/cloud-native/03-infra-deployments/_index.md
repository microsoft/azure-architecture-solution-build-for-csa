## Have they got a complex infrastructure they need to deploy? 

The flexibility in deployment options has never been greater on Azure, so it is important for all architects to get hands on with the various technologies and see how they work individually and combined with each other. This is one area where simply reading about infrastructure is not enough, hands on experience is essential. A depth and breadth of architectural understanding in this space is needed to effectively navigate particular requirements and recommend the correct combination of technologies. Always ask plenty of open questions and listening and be aware of your own biases and moving too fast to known solutions.

Automation of deployment is absolutely key for speed consistency and quality. Common options include **ARM templates** (including the Bicep wrapper), **Terraform**, **PowerShell** / **Azure CLI** scripts, SDKs and direct REST API calls are common, as well as configuration management tooling (e.g. **Ansible**, **Chef**, **Puppet**) or higher level programming abstraction such as **Pulumi**. 

* [Deploy and manage resources in Azure by using ARM templates](https://docs.microsoft.com/learn/paths/deploy-manage-resource-manager-templates/)
* [Get Started with Terraform on Azure](https://learn.hashicorp.com/collections/terraform/azure-get-started)
* [Control Azure services with the CLI](https://docs.microsoft.com/learn/modules/control-azure-services-with-cli/)
* [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps?view=azps-5.2.0)
* [Azure Citadel](https://azurecitadel.com/)

Ask the right questions to help to reduce down the options. For example, **should the solution be Marketplace deployable?** If so then that is a natural constraint and ARM templating provides the greatest integration. Or it may be that they already have existing skills and a desire to use open source and multi cloud vendor tooling which pushes towards other common patterns such as a mix of Terraform, Helm, Packer and Ansible.

* [Azure Marketplace Publishing Guide](https://docs.microsoft.com/azure/marketplace/publisher-guide-by-offer-type)
* [Develop on AKS with Helm](https://docs.microsoft.com/azure/aks/quickstart-helm)
* [Create Linux Azure VM Images with Packer](https://docs.microsoft.com/azure/virtual-machines/linux/build-image-with-packer)

Understand the partner organisation and technical groups. For more complex deployments then understanding how the groups works together can help define points of delineation that help to map on new technologies as you transform them towards cloud. For example, if they are IaaS focused and a group has historically spent time installing software and running scripts to semi automate solution deployment then move towards an image factory to help generate custom images in Shared Image Gallery. Moving towards custom VM and container images, plus infrastructure as code deployments is important as a shift in mindset.

* [Share VM images with Shared Image Galleries](https://docs.microsoft.com/azure/virtual-machines/shared-image-galleries)
* [Azure Container Registry](https://docs.microsoft.com/azure/container-registry/container-registry-intro)

Explore the arrangement and phasing of deployments. Understand which parts of the solution are base and foundational (such as core connectivity, central secret management, management and monitoring resources), which are multi-tenanted and which (if any) are deployed per customer in a multi-tenanted solution. 

* [Enterprise Scale landing zone architecture](https://docs.microsoft.com/azure/cloud-adoption-framework/ready/enterprise-scale/architecture)
* [Decomposition with Terraform Remote State](https://www.terraform.io/docs/state/remote.html#delegation-and-teamwork)

Where resources are deployed and how they are managed is flexible when you understand how to use Azure Lighthouse, Azure Arc and the Private Link Service in an ISV context. Deploying to customer subscriptions, mixing cloud and on prem resources, or providing services between tenant is all possible. Providing ongoing service management in Azure with Lighthouse is more flexible than before. Using GitOps with Azure Arc for Kubernetes can provide deployment control for the on prem containerised workloads. 

* [What is Azure Lighthouse?](https://docs.microsoft.com/azure/lighthouse/overview)
* [Overview of Azure Arc enabled Kubernetes](https://docs.microsoft.com/azure/azure-arc/kubernetes/overview)
* [What is Azure Private Link service?](https://docs.microsoft.com/azure/private-link/private-link-service-overview)

Address compliancy and governance requirements. Focus on adhering to the functionality used in the Cloud Adoption Framework and Enterprise Scale. This can be an effective way of leveraging Azure Policy Initiatives and management group level to help confirm compliancy within specific governmental and vertical requirements. Leverage Deploy If Not Exists policies to simplify the deployment by automatically configuring security, management and monitoring. Policy uniformly applies those at scale rather than complicating the infrastructure as code definitions. 

* [Overview of Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview)
* [Regulatory Compliance in initiative definitions](https://docs.microsoft.com/azure/governance/policy/concepts/regulatory-compliance)
* [Cloud Adoption Framework](https://aka.ms/adopt)

The introduction of new technologies usually requires an element of partner enablement followed by setting milestones and tracking progress. Meet with the partner’s technical community at a regular cadence to check status, unblock issues and provide additional insights as required. This approach will gain and maintain momentum.
