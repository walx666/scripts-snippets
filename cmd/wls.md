# Update WSL-Distros
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
