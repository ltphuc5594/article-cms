# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

--------------------
#### Analysis

**Costs**:
Azure VMs are more expensive to run in comparison to Azure App Service.
VMs are only charged on disk costs when stopped.
Azure App Service will continue charging even though apps are unused or when stopped.

**Scalability**:
Both the Virtual machine and the App Service can be scaled horizontally and vertically.
VMs can be scaled horizontally using a Scale Sets, while provides an integrated load balancer and can easily increase instances.

**Availability**:
Virtual machines generally have more availability than App Services, but require extra setup and configuration to be fault-tolerant and avoid downtimes during maintenance and upgrades

**Workflow**:
It is easy to deploy applications to App Service than it is to Virtual Machines. Although an automated CI/CD pipeline could be designed to resolve this issue, overhead time would be spent in the process

--------------------
#### Decision

Deployment option: App Service

--------------------
#### Justification

This application is lightweight web application, so it is suitable App Service over VMs.
And this application is a CMS system, is used for internal user. So the number of users is not large.
App Services cost less than VMs do.
The app service is a PaaS option, it supports continuous deployment model using GitHub, Azure DevOps, or any Git repo.

--------------------

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.*

App Service's are limited 14 GB of Memory and 4 VCPUs. If the application were to be a high compute application the need to extend hardware requirements would call for a Virtual Machine.
App Service's are limited to just using those languages (as of when this course was built). If the application is built by new/unsupported languages (such as Go,...), we need to use Virtual Machine.
