# Delete

        Install-Module MSOnline
        Import-Module MSOnline
        Connect-MsolService
        Remove-MsolUser -UserPrincipalName `n.ramani@scantechlaser.com' -RemoveFromRecycleBin
        Get-MsolUser -ReturnDeletedUsers | Remove-MsolUser -RemoveFromRecycleBin -Force