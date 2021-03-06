
# Expand-CrmSolution

## Synopsis
Extracts a CRM solution zip file using the SolutionPackager tool.

## Description
This function extracts a CRM solution file to its individual components using the SolutionPackager tool included in the Dynamics 365 SDK. The SolutionPackager documentation is located online at https://msdn.microsoft.com/en-us/library/jj602987.aspx.

## Parameters
| Parameter  | Type | Description | Required? | Default Value |
|---|---|---|---|---|
| ZipFile | String | The source solution zip file to extract. See the `/zipfile` parameter of the SolutionPackager tool. | true | |
| MappingXmlFile | String | The path and name of an .xml file containing file mapping directives. See the `/map` parameter of the SolutionPackager tool. | false | |
| PackageType | String | The package type to process. See the `/packagetype` parameter of the SolutionPackager tool. | true | |
| Folder | String | The folder path to store the extracted solution file. See the `/folder` parameter of the SolutionPackager tool. | true | |

## Examples

## Example 1
This example extracts the AdventureWorks solution to a folder.
```powershell
Expand-CrmSolution -ZipFile 'C:\temp\export\AdventureWorks.zip' -PackageType Unmanaged -Folder 'C:\temp\solutions\AdventureWorks'
```

## Example 2
This example extracts the AdventureWorks solution to a folder and uses an XML mapping file as used by the `/map` parameter of the SolutionPackager tool.
```powershell
Expand-CrmSolution -ZipFile 'C:\temp\export\AdventureWorks.zip' -MappingXmlFile 'C:\temp\solutions\AdventureWorks.mapping.xml' -PackageType Unmanaged -Folder 'C:\temp\solutions\AdventureWorks'
```

## Example 3
This example extracts the unmanaged and managed versions of the AdventureWorks solution to a folder using the SolutionPackager tool. The managed version of solution must exist in the same folder as the unmanaged solution and end with the name _managed.zip (e.g. AdventureWorks_managed.zip).
```powershell
Expand-CrmSolution -ZipFile 'C:\temp\export\AdventureWorks.zip' -PackageType Both -Folder 'C:\temp\solutions\AdventureWorks'
```
