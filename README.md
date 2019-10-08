
# Configure the Azure DevOps Release Add-On

After installing the Add-On, navigate to the Configuration page.  Click "Add" and complete the following information:
 - Account Name
 - Organization
 - Personal Access Token

For more information on how to create or use a personal access token: [https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops](https://docs.microsoft.com/en-us/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate?view=azure-devops)

---

# Adding Inputs

On the Inputs page in the Add-On you can create the following inputs:

## Azure DevOps Projects Lists
Lists all Azure DevOps Projects

### Sourcetype
    AzureDevOps:Projects
### Endpoint
	GET https://dev.azure.com/{organization}/_apis/projects?api-version=5.1


## Azure DevOps Approvals
Lists all Release Approvals

### Sourcetype
	AzureDevOps:Approvals
### Endpoint
	GET https://vsrm.dev.azure.com/{organization}/{project}/_apis/release/approvals?api-version=5.1


## Azure DevOps Deployments
Lists all Release Deployments

### Sourcetype
	AzureDevOps:Deployments
### Endpoint
	GET https://vsrm.dev.azure.com/{organization}/{project}/_apis/release/deployments?api-version=5.1


## Azure DevOps Releases
Lists all Releases

### Sourcetype
	AzureDevOps:Releases
### Endpoint
	GET https://vsrm.dev.azure.com/{organization}/{project}/_apis/release/releases/{releaseId}?api-version=5.1


## Azure DevOps Release Definitions
Lists all Release Definitions

### Sourcetype
	AzureDevOps:ReleaseDefinitions
### Endpoint
	GET https://vsrm.dev.azure.com/{organization}/{project}/_apis/release/definitions/{definitionId}?api-version=5.1

---

# props.conf

Due to large JSON events in the Releases and Release Definitions the default TRUNCATE value has been increased to 50000 for the sourcetypes: AzureDevOps:Releases, AzureDevOps:Release Definitions

---

# Azure DevOps RST API Reference
[https://docs.microsoft.com/en-us/rest/api/azure/devops/?view=azure-devops-rest-5.1](https://docs.microsoft.com/en-us/rest/api/azure/devops/?view=azure-devops-rest-5.1)