# Removing drivers from Windows driver store
To completely remove your driver files, first uninstall your printer driver. See section Printer drivers removal. 
When you remove your printer driver from your computer, this procedure only removes the printer as a device. Driver files still exist on the disk. 
When you connect your printer next time, Windows installs the stored previously-used printer driver. To verify which drivers are stored in the system, 
do the following:

Run Command Prompt as an administrator.

Enter the command:
```cmd
pnputil.exe -e
```

A list of all INF files for installed drivers appears. The files are listed as
oem<number>.inf

Search for the right INF file. Check for:
- Driver package provider.
- Driver date and version.

Delete the driver files using the following command:
```cmd
pnputil.exe -f -d oem<number>.inf
```

Your driver and all the driver files are now removed from the system.