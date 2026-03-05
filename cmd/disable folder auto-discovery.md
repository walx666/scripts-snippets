# To disable the auto-discovery of every explorer folder

https://www.borncity.com/blog/2025/11/03/windows-11-folder-auto-discovery-bremst-explorer-optionen-zum-abschalten/

https://www.ninjaone.com/blog/manage-folder-and-library-templates-in-file-explorer/


Registry File
```reg
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Classes\Local Settings\Software\Microsoft\Windows\Shell\Bags\AllFolders\Shell] 
"FolderType"="NotSpecified"
```

```bat
reg add "HKCU\SOFTWARE\Classes\Local Settings\Software\Microsoft\Windows\Shell\Bags\AllFolders\Shell" /v FolderType /t REG_SZ /d "NotSpecified" /f
```