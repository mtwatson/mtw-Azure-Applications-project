# Write-up Template

### Analyze, choose, and justify the appropriate resource option for deploying the app.

*For **both** a VM or App Service solution for the CMS app:*
- *Analyze costs, scalability, availability, and workflow*
- *Choose the appropriate solution (VM or App Service) for deploying the app*
- *Justify your choice*

### Assess app changes that would change your decision.

*Detail how the app and any other needs would have to change for you to change your decision in the last section.* 

# Azure Article CMS Udacity Project

## Decision: Use App Service Solution
### Justification

App Service is considerably cheaper, as it leverages (wastes) less resources. A full blown VM would consume considerably more memory, compute and storage. Even setting aside the extra resources demanded of the VM, the leftover footprint never be efficiently saturated by this simple python flaskapp.

These advantages are magnified when it comes to scaling. Replicating the application across availability zones or behind a load balancer will be dramatically more efficient. This will keep costs down, while increasing uptime for visitors.

The natural evolution of this philosophy is to, as the developer, build and deploy containerized applications into the cloud. A likely end path would be kubernetes.

VMs also require non-trivial configuration and management overhead for deployment.

### Assess app changes that would change your decision.

If there was a business or compliance demand for greater granularity of control, then a VM may be prudent. If, for example, certain configuration or security software/utilities were required by NIST, PCI-DSS, et al for a running (secure) application then a VM would be a logical choice (relative to Azure App Service). 