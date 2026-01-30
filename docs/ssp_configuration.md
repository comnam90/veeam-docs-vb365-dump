---
title: "Configuration"
product: "vb365"
doc_type: "guide"
source_url: "https://helpcenter.veeam.com/docs/vbo365/guide/ssp_configuration.html"
last_updated: "12/2/2025"
product_version: "8.3.0.2201"
---

# Configuration


Restore Portal is deployed automatically along with the Veeam Backup for Microsoft 365 REST API component installation.

The Veeam Backup for Microsoft 365 administrator can configure Restore Portal for the following backup infrastructures:

* [Single Microsoft 365 Organization](#single_tenant)
* [Multiple Tenants on Service Provider Side](#multiple_tenants)

Configuring Restore Portal for Single Microsoft 365 Organization

If the Veeam Backup for Microsoft 365 administrator wants to allow end users and restore operators in a Microsoft 365 organization to explore and restore data from backups using Restore Portal, the following actions must be performed before users start using the web application:

1. Check that the Veeam Backup for Microsoft 365 REST API component is installed either on the Veeam Backup for Microsoft 365 server or on a separate machine.

Deployment of the Veeam Backup for Microsoft 365 REST API component on a separate machine decreases the load on the backup infrastructure when exploring and restoring data from backups using Restore Portal. For more information, see [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md) to deploy the solution to the Veeam Backup for Microsoft 365 server and [Installing REST API](vbo_installing_rest.md) to deploy the Veeam Backup for Microsoft 365 REST API component separately.

1. Enable Veeam Backup for Microsoft 365 REST API Service.

This service processes REST API commands and allows Restore Portal to communicate with Veeam Backup for Microsoft 365. For more information, see [REST API Settings](vbo_rest_api_settings.md) if you have deployed the solution on the Veeam Backup for Microsoft 365 server and [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md#rest) if you have installed REST API separately.

1. Enable restore operator authentication to the Veeam Backup for Microsoft 365 server. For more information, see [Authentication Settings](vbo_authentication_settings.md#restore_operator).
2. Enable Restore Portal and configure access to it. For more information, see [Restore Portal Settings](vbo_restore_portal_settings.md) if you have deployed the solution on the Veeam Backup for Microsoft 365 server and [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md#ssp) if you have installed REST API separately.
3. Add restore operator roles to assign permissions to users who act as restore operators. For more information, see [Adding Restore Operator Role](ssp_adding_operator_roles.md).
4. Provide end users and restore operators with the Restore Portal web address.

Configuring Restore Portal for Multiple Tenants

|  |
| --- |
| Note |
| Follow these steps as a part of Backup as a Service with Veeam Backup for Microsoft 365 usage scenario. For more information, see [Backup as Service with Veeam Backup for Microsoft 365](vbo_mail_baas.md). |

On Service Provider Side

To configure access for end users and restore operators from tenant organizations to Restore Portal, the following actions must be performed on a service provider side before users start using the web application:

1. Check that the Veeam Backup for Microsoft 365 REST API component is installed either on the Veeam Backup for Microsoft 365 server or on a separate machine.

Deployment of the Veeam Backup for Microsoft 365 REST API component on a separate machine decreases the load on the backup infrastructure when exploring and restoring data from backups using Restore Portal. For more information, see [Installing Veeam Backup for Microsoft 365](vbo_installing_vbo.md) to deploy the solution to the Veeam Backup for Microsoft 365 server and [Installing REST API](vbo_installing_rest.md) to deploy the Veeam Backup for Microsoft 365 REST API component separately.

1. Enable Veeam Backup for Microsoft 365 REST API Service.

This service processes REST API commands and allows Restore Portal to communicate with Veeam Backup for Microsoft 365. For more information, see [REST API Settings](vbo_rest_api_settings.md) if you have deployed the solution on the Veeam Backup for Microsoft 365 server and [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md#rest) if you have installed REST API separately.

1. Enable tenant and restore operator authentication to the Veeam Backup for Microsoft 365 server. For more information, see [Authentication Settings](vbo_authentication_settings.md).
2. Enable Restore Portal and configure access to it. For more information, see [Restore Portal Settings](vbo_restore_portal_settings.md) if you have deployed the solution on the Veeam Backup for Microsoft 365 server and [Configuring REST API and Restore Portal on Separate Machine](vbo_configuring_rest_separate.md#ssp) if you have installed REST API separately.

|  |
| --- |
| Important |
| Microsoft Entra application that end users and restore operators from tenant organizations will use to access Restore Portal must be created for a Microsoft 365 organization on a service provider side. |

1. Run the [Install-Module](https://learn.microsoft.com/en-us/powershell/module/powershellget/install-module?view=powershellget-3.x) cmdlet to install the Microsoft Graph PowerShell module. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/powershell/microsoftgraph/installation?view=graph-powershell-1.0).

|  |
| --- |
| Install-Module Microsoft.Graph |

1. Share the configured Microsoft Entra application with all tenant organizations.

To do this, authenticate to Microsoft Entra ID using the [Connect-MgGraph](https://learn.microsoft.com/en-us/powershell/module/microsoft.graph.authentication/connect-mggraph?view=graph-powershell-1.0) cmdlet and than run the [New-MgServicePrincipal](https://learn.microsoft.com/en-us/powershell/module/microsoft.graph.applications/new-mgserviceprincipal?view=graph-powershell-1.0) cmdlet. Specify an application ID of the Microsoft Entra application configured for authentication to Restore Portal as the AppId parameter value.

|  |
| --- |
| Connect-MgGraph -Scopes "Application.ReadWrite.All","Directory.ReadWrite.All"  New-MgServicePrincipal -AppId "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX" |

|  |
| --- |
| Note |
| To run the [Connect-MgGraph](https://learn.microsoft.com/en-us/powershell/module/microsoft.graph.authentication/connect-mggraph?view=graph-powershell-1.0) cmdlet, a user account must be assigned the Global Administrator or Application Administrator role. |

Although [Microsoft deprecated Azure AD PowerShell](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/important-update-deprecation-of-azure-ad-powershell-and-msonline-powershell-modu/4094536), you can run the [Connect-AzureAD](https://learn.microsoft.com/en-us/powershell/module/azuread/connect-azuread?view=azureadps-2.0) cmdlet and then run the [New-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/new-azureadserviceprincipal?view=azureadps-2.0) cmdlet. Specify an application ID of the Microsoft Entra application configured for authentication to Restore Portal as the AppId parameter value.

For more information on how to migrate from Azure AD PowerShell to Microsoft Graph PowerShell, see [this Microsoft article](https://learn.microsoft.com/en-us/powershell/microsoftgraph/migration-steps?view=graph-powershell-1.0).

|  |
| --- |
| Connect-AzureAD  New-AzureADServicePrincipal -AppId "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX" |

1. Configure access to Restore Portal on each tenant side. For more information, see [On Tenant Side](#tenantside).
2. Add restore operator roles to assign permissions to users who act as restore operators. For more information, see [Adding Restore Operator Role](ssp_adding_operator_roles.md).
3. Provide end users and restore operators with the Restore Portal web address.

On Tenant Side

Perform the following actions for all tenant organizations before users start using the web application:

1. Run the [Install-Module](https://learn.microsoft.com/en-us/powershell/module/powershellget/install-module?view=powershellget-3.x) cmdlet to install the Microsoft Graph PowerShell module. For more information, see [this Microsoft article](https://learn.microsoft.com/en-us/powershell/microsoftgraph/installation?view=graph-powershell-1.0).

|  |
| --- |
| Install-Module Microsoft.Graph |

1. Authenticate to Microsoft Entra ID using the [Connect-MgGraph](https://learn.microsoft.com/en-us/powershell/module/microsoft.graph.authentication/connect-mggraph?view=graph-powershell-1.0) cmdlet and than run the [New-MgServicePrincipal](https://learn.microsoft.com/en-us/powershell/module/microsoft.graph.applications/new-mgserviceprincipal?view=graph-powershell-1.0) cmdlet. Specify an application ID of the Microsoft Entra application configured by a service provider for authentication to Restore Portal as the AppId parameter value.

|  |
| --- |
| Connect-MgGraph -Scopes "Application.ReadWrite.All","Directory.ReadWrite.All"  New-MgServicePrincipal -AppId "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX" |

Alternatively, you can perform a login attempt to Restore Portal to create a service principal automatically.

|  |
| --- |
| Note |
| To run the [Connect-MgGraph](https://learn.microsoft.com/en-us/powershell/module/microsoft.graph.authentication/connect-mggraph?view=graph-powershell-1.0) cmdlet, a user account must be assigned the Global Administrator or Application Administrator role. |

Although [Microsoft deprecated Azure AD PowerShell](https://techcommunity.microsoft.com/blog/microsoft-entra-blog/important-update-deprecation-of-azure-ad-powershell-and-msonline-powershell-modu/4094536), you can run the [Connect-AzureAD](https://learn.microsoft.com/en-us/powershell/module/azuread/connect-azuread?view=azureadps-2.0) cmdlet and then run the [New-AzureADServicePrincipal](https://docs.microsoft.com/en-us/powershell/module/azuread/new-azureadserviceprincipal?view=azureadps-2.0) cmdlet. Specify an application ID of the Microsoft Entra application configured by a service provider for authentication to Restore Portal as the AppId parameter value.

For more information on how to migrate from Azure AD PowerShell to Microsoft Graph PowerShell, see [this Microsoft article](https://learn.microsoft.com/en-us/powershell/microsoftgraph/migration-steps?view=graph-powershell-1.0).

|  |
| --- |
| Connect-AzureAD  New-AzureADServicePrincipal -AppId "XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX" |

1. Sign in to the [Microsoft Entra admin center](https://entra.microsoft.com/) of the tenant organization.
2. Go to Identity > Applications > Enterprise applications.
3. Search for Microsoft Entra application configured for authentication to Restore Portal by ObjectID that you have obtained at step 2. Alternatively, you can get ObjectID by running the following command:

|  |
| --- |
| Get-MgServicePrincipal -Filter "AppId eq 'XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX'" |

Specify an ID of the Microsoft Entra application configured by a service provider for authentication to Restore Portal as the AppId parameter value.

1. Go to the application permissions and grant admin consent to this application on behalf of all users in the tenant organization. For more information, see [this Microsoft article](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/manage-application-permissions), [Permissions for Authentication to Restore Portal](ssp_ad_application_permissions.md) and contact Veeam Customer Support.

In This Section

* [Adding Restore Operator Role](ssp_adding_operator_roles.md)
* [Editing Restore Operator Role Settings](editing_operator_role_settings.md)
* [Removing Restore Operator Role](removing_operator_role.md)


