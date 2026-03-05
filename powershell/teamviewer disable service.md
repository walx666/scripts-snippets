# To stop and disable the TeamViewer-Service (after install/update)
```powershell
sc.exe config TeamViewer start=disabled
sc.exe stop TeamViewer
```