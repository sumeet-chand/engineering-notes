
# PROGRAMMING WITH POWERSHELL

By: Sumeet Singh

Date: July 2024

# TABLE OF CONTENTS
- [1. Terminologies](#terminologies)
- [2. Requirements](#requirements)
- [3. Installing](#installing)
- [4. Profile script](#profile-script)
- [5. Common Commands](#common-commands)
- [6. Scripts](#scripts)
- [7. Winget](#winget)

# TERMINOLOGIES

# REQUIREMENTS

MAKE PROFILE
```powershell
```

# INSTALLING

MAKE PROFILE
```powershell
```

# PROFILE SCRIPT

MAKE PROFILE
```bash
PS C:\Users\Sumeet\Documents\sandbox> $PROFILE
C:\Users\Sumeet\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1
mkdir C:\Users\Sumeet\Documents\WindowsPowerShell # make profile directory
new-item -path C:\Users\Sumeet\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1 # make profile
notepad $PROFILE # open profile
Write-Host "Welcome, $env:USERNAME@$env:COMPUTERNAME Today is $(Get-Date -Format 'dddd, MMMM dd yyyy')." # add line in profile
. $PROFILE # reset profile

# RESULT
Welcome, Sumeet@SUMEETS-PC Today is Sunday, July 07 2024.
PS C:\Users\Sumeet\Documents\sandbox>
```

# COMMON COMMANDS

1. COPY SUBDIRECTORIES CONTENTS TO PARENT THEN DELETE
```powershell
cd "C:\Users\Sumeet\Downloads"

$source = "C:\Users\Sumeet\Downloads"
$destination = "C:\Users\Sumeet\Downloads"

Get-ChildItem -Directory | ForEach-Object {
    $subDirPath = $_.FullName
    Write-Host "Copying contents from: $subDirPath to  $destination"

    # Use robocopy to move files
    robocopy "$subDirPath" "$destination" /MOV /E /Z /NP /NFL /NDL /NJH /NJS /XD "$subDirPath" /R:1 /W:1
}

# Clean up empty subdirectories
Get-ChildItem -Directory -Recurse | Where-Object { $_.GetFileSystemInfos().Count -eq 0 } | ForEach-Object {
    $directoryPath = $_.FullName
    Write-Host "Deleting directory: $directoryPath"
    $_ | Remove-Item -Force
}
```

# SCRIPTS

SCRIPTS
```powershell

```

# WINGET

SEARCH INSTALLED PACKAGES
```powershell
winget list
```

SEARCH PACKAGE
```powershell
winget search g++
```

INSTALL
```powershell
winget install LLVM
```

UNINSTALL
```powershell
winget remove LLVM
```


UPLOADING A WINGET
```powershell

```


# MICROSOFT 365 AZURE AD

CONNECT TO TENANT
```powershell
Install-Module -Name AzureAD -Force
Set-ExecutionPolicy RemoteSigned
Import-Module AzureAD
Connect-AzureAD -Credential (Get-Credential)
```

FIND USERS GROUPS
```powershell
Get-AzureADUser
```

# MICROSOFT 365 EXCHANGE

CONNECT TO TENANT
```powershell
Install-Module -Name ExchangeOnlineManagement -Force
Set-ExecutionPolicy RemoteSigned
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -Credential (Get-Credential)
```

FIND MAILBOX SIZE
```powershell
Get-MailboxStatistics -Identity "user@domain.com"
```