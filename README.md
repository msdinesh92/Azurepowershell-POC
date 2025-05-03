# Azurepowershell-POC

Create multiple Resource Groups
Each Resource Group in different Azure locations
# Define Resource Group names and locations
$resourceGroups = @(
    @{ Name = "RG-EastUS"; Location = "EastUS" },
    @{ Name = "RG-CentralIndia"; Location = "CentralIndia" },
    @{ Name = "RG-WestEurope"; Location = "WestEurope" },
    @{ Name = "RG-JapanEast"; Location = "JapanEast" }
)

# Loop to create each Resource Group
foreach ($rg in $resourceGroups) {
    New-AzResourceGroup -Name $rg.Name -Location $rg.Location
    Write-Output "Resource Group $($rg.Name) created in $($rg.Location)"
}
Script to Delete All the Above Resource Groups
# Define the same Resource Groups again
$resourceGroups = @(
    @{ Name = "RG-EastUS" },
    @{ Name = "RG-CentralIndia" },
    @{ Name = "RG-WestEurope" },
    @{ Name = "RG-JapanEast" },
    @{ Name = "RG01" },
    @{ Name = "RG02" }
)

# Loop to delete each Resource Group
foreach ($rg in $resourceGroups) {
    Remove-AzResourceGroup -Name $rg.Name -Force
    Write-Output "Deleted Resource Group: $($rg.Name)"
}
