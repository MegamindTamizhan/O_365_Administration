# Delete

        Install-Module MSOnline
        Import-Module MSOnline
        Connect-MsolService
        Remove-MsolUser -UserPrincipalName `raja@test.com' -RemoveFromRecycleBin
        Get-MsolUser -ReturnDeletedUsers
        Get-MsolUser -ReturnDeletedUsers | Remove-MsolUser -RemoveFromRecycleBin -Force