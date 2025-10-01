# Update WSL-Distros

## Vartiant 1
```bat
@echo off
wsl -u root -d Ubuntu-24.04 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
wsl -u root -d Ubuntu-22.04 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
wsl -u root -d Ubuntu-20.04 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
wsl -u root -d Debian-12 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
wsl -u root -d Debian-11 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
::wsl -u root -d Debian-10 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
::wsl -u root -d Debian-9 -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
pause
```

## Vartiant 2
```bat
@echo off
setlocal EnableDelayedExpansion

set "DISTROS=Ubuntu-24.04;Ubuntu-22.04;Ubuntu-20.04;Debian-12;Debian-11"

for %%A in ("%DISTROS:;=";"%") do (
 	title Update %%~A
	echo.
	echo --- Update %%~A ---
	wsl -u root -d %%~A -- bash -c "apt-get update && apt-get -y upgrade && apt-get autoremove -y && apt-get autoclean"
	
	if [!ERRORLEVEL!] neq [0] (
		echo ERROR !ERRORLEVEL!
		timeout 30
	)
	echo.
)
```
