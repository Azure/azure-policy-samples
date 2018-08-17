# Enforce encryption on Data Lake Store accounts

This policy ensures encryption is enabled on all Data Lake Store accounts

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true&microsoft_azure_policy_policyinsights=true&feature.microsoft_azure_security_policy=true&microsoft_azure_marketplace_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2Fbuilt-in-policy%2Fdata-lake-shore-encryption%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "data-lake-shore-encryption" -DisplayName "Enforce encryption on Data Lake Store accounts" -description "This policy ensures encryption is enabled on all Data Lake Store accounts" -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/data-lake-shore-encryption/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/data-lake-shore-encryption/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition
$assignment 
````

## Try with CLI

````cli

az policy definition create --name 'data-lake-shore-encryption' --display-name 'Enforce encryption on Data Lake Store accounts' --description 'This policy ensures encryption is enabled on all Data Lake Store accounts' --rules 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/data-lake-shore-encryption/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/built-in-policy/data-lake-shore-encryption/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "data-lake-shore-encryption" 

````