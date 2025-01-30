# Get a GridView-list of all installed windows apps ...

If you find same universal or provisioned apps are difficult to remove, try the GRID command in Powershell:
PowerShell Commands to Remove Apps in GridView

Just use Out-Gridview to select which applications you want to remove.
```powershell
Get-AppxPackage | Out-GridView -Passthru | Remove-AppXPackage
```

Keep in mind the above only removed the apps for the current user. To remove the apps from the computer for all users, run the following:

```powershell
Get-AppxProvisionedPackage -Online | Out-GridView -PassThru | Remove-AppxProvisionedPackage -Online
```

This will display a grid of all installed apps. You can SELECT the apps (highlight in blue) you want to remove from the displayed list and click OK. Reboot.

(I found I could only delete a few apps at a time by repeating the above command and selecting a few each time I reran the command)
```powershell
Get-AppxPackage -Name king.com.CandyCrushSaga
```

## A list of my choices to remove...

```powershell
Get-AppxPackage *Microsoft.Xbox.TCUI* -AllUsers | Remove-AppxPackage
Get-AppxPackage *Microsoft.XboxApp* -AllUsers | Remove-AppxPackage
Get-AppxPackage *Microsoft.XboxGameOverlay* -AllUsers | Remove-AppxPackage
Get-AppxPackage *Microsoft.XboxGamingOverlay* -AllUsers | Remove-AppxPackage
Get-AppxPackage *Microsoft.XboxIdentityProvider* -AllUsers | Remove-AppxPackage
Get-AppxPackage *Microsoft.XboxSpeechToTextOverlay* -AllUsers | Remove-AppxPackage
Get-AppxPackage *Microsoft.YourPhone* -AllUsers | Remove-AppxPackage
```
