
# Remove-CrmRemoteOrganization

## Synopsis
Deletes an existing on-premise CRM organization from a remote CRM server.

## Description
This function deletes an on-premise CRM organization by using PowerShell remoting to connect to a remote CRM Server, removing the CRM organization and deleting the SQL database.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| ComputerName | String | The name of the CRM server to connect to and perform a CRM organization deletion | true | |
 | OrganizationName | String | The name of the database and organization to delete | true | |
 | Credential | PSCredential | The credentials for accessing the CRM server via PowerShell remoting | true | |

## Examples

## Example 1
This example shows how to delete an organization named Northwind on the server named dyn365.contoso.com using the supplied credentials for PowerShell remoting.
```powershell
Remove-CrmRemoteOrganization -ComputerName dyn365.contoso.com -OrganizationName Northwind -Credential $Credential
```
