# How to Purge Deleted MSOL Users From the Office 365 Recycle Bin - (When you delete a user from Office 365 that user is moved into a recycle bin so that it can be restored back to production within in establish threshold, generally 30 days.)

Note: Once an object has been deleted from the recycle bin in cannot be restored and is permanent, please use with care

Before that you have to install the MSOL Module:

        PS> Install-Module MSOnline
        PS> Import-Module MSOnline
        PS> Connect-MsolService

To see a list of deleted users currently in the recycle bin you can use the following Powershell command:
        
        PS> Get-MsolUser -ReturnDeletedUsers

If you wish to remove a single item from the recycle bin use can use the Powershell command:
        
        PS> Remove-MsolUser -UserPrincipalName `raja@test.com' -RemoveFromRecycleBin

Subsequently, if you would like to remove all the users in the recycle bin you can use the following Powershell command: (If you would like to be prompted for each delete, you can remove the -Force switch from the command above.)

        PS> Get-MsolUser -ReturnDeletedUsers | Remove-MsolUser -RemoveFromRecycleBin -Force