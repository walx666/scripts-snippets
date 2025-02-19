# script snippets for installing (my) most used or needed tools

## creativity, media, office
```powershell
# essential
winget install paint.net --source winget --scope machine --accept-package-agreements
winget install freetube --source winget --scope machine --accept-package-agreements
winget install sumatrapdf --source winget --scope machine --accept-package-agreements
# bowser
winget install Brave.Brave betterbird --source winget --scope machine --accept-package-agreements
winget install Firefox thunderbird --source winget --scope machine --accept-package-agreements
# vpn
winget install OpenVPNTechnologies.OpenVPN --source winget --scope machine --accept-package-agreements
winget install WireGuard --source winget --scope machine --accept-package-agreements
winget install Tailscale --source winget --scope machine --accept-package-agreements
```
## tools for development
```powershell
# essential
winget install notepad++ --source winget --scope machine --accept-package-agreements
winget install 7zip --source winget --scope machine --accept-package-agreements
winget install winmerge --source winget --scope machine --accept-package-agreements
winget install hxd --source winget --scope machine --accept-package-agreements
winget install git --source winget --scope machine --accept-package-agreements
winget install tortoisegit --source winget --scope machine --accept-package-agreements
winget install cmake --source winget --scope machine --accept-package-agreements
winget install putty --source winget --scope machine --accept-package-agreements
winget install teraterm --source winget --scope machine --accept-package-agreements
# packaging
winget install nsis --source winget --scope machine --accept-package-agreements
winget install WiXToolset.WiXToolset --source winget --scope machine --accept-package-agreements
# editors
winget install vscodium --source winget --scope machine --accept-package-agreements
winget install vscode --source winget --scope machine --accept-package-agreements
# testing
winget install virtualbox --source winget --scope machine --accept-package-agreements
```
## some runtimes
```powershell
# VCRedist 2005 
winget install Microsoft.VCRedist.2005.x86 --source winget --scope machine --accept-package-agreements
winget install Microsoft.VCRedist.2005.x64 --source winget --scope machine --accept-package-agreements
# VCRedist 2008
winget install Microsoft.VCRedist.2008.x86 --source winget --scope machine --accept-package-agreements
winget install Microsoft.VCRedist.2008.x64 --source winget --scope machine --accept-package-agreements
# VCRedist 2010
winget install Microsoft.VCRedist.2010.x86 --source winget --scope machine --accept-package-agreements
winget install Microsoft.VCRedist.2010.x64 --source winget --scope machine --accept-package-agreements
# VCRedist 2012
winget install Microsoft.VCRedist.2012.x86 --source winget --scope machine --accept-package-agreements
winget install Microsoft.VCRedist.2012.x64 --source winget --scope machine --accept-package-agreements
# VCRedist 2013
winget install Microsoft.VCRedist.2013.x86 --source winget --scope machine --accept-package-agreements
winget install Microsoft.VCRedist.2013.x64 --source winget --scope machine --accept-package-agreements
# VCRedist 2015+
winget install Microsoft.VCRedist.2015+.x86 --source winget --scope machine --accept-package-agreements
winget install Microsoft.VCRedist.2015+.x64 --source winget --scope machine --accept-package-agreements
# DotNET Desktop Runtimes
winget install Microsoft.DotNet.DesktopRuntime.5 --source winget --scope machine --accept-package-agreements
winget install Microsoft.DotNet.DesktopRuntime.6 --source winget --scope machine --accept-package-agreements
winget install Microsoft.DotNet.DesktopRuntime.7 --source winget --scope machine --accept-package-agreements
winget install Microsoft.DotNet.DesktopRuntime.8 --source winget --scope machine --accept-package-agreements
# Python
winget install Python.Launcher --source winget --scope machine --accept-package-agreements 
winget install "Python 3.13" --source winget --scope machine --accept-package-agreements
```
## other useful tools...
```powershell
winget install packetsender --source winget --scope machine --accept-package-agreements
```

## office and other needed...
```powershell
winget install paint.net everything keepassxc libreoffice --source winget --scope machine --accept-package-agreements
```

---

## upgrading installed apps
```powershell
winget upgrade --all --silent --accept-source-agreements --accept-package-agreements 
```
