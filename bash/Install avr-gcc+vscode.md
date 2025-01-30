# Install VSCodium
```bash
sudo apt install dirmngr software-properties-common apt-transport-https curl -y
curl -fSsL https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/raw/master/pub.gpg | sudo gpg --dearmor | sudo tee /usr/share/keyrings/vscodium.gpg > /dev/null
echo deb [signed-by=/usr/share/keyrings/vscodium.gpg] https://download.vscodium.com/debs vscodium main | sudo tee /etc/apt/sources.list.d/vscodium.list
sudo apt update
sudo apt install codium -y
```

# may be needed for installing gcc-avr
```bash
sudo apt install libfl2 bzip2 make
```

# gcc-avr 7.3.0 from Microchip / Atmel
```bash
mkdir ~/.avr-gcc/ ; cd ~/.avr-gcc
wget https://ww1.microchip.com/downloads/aemDocuments/documents/DEV/ProductDocuments/SoftwareTools/avr8-gnu-toolchain-3.7.0.1796-linux.any.x86_64.tar.gz && tar -xvf avr8-gnu-toolchain-3.7.0.1796-linux.any.x86_64.tar.gz && mv avr8-gnu-toolchain-linux_x86_64 7.3.0
rm avr8-gnu-toolchain-3.7.0.1796-linux.any.x86_64.tar.gz
```

# gcc-avr 8.3.0 from ZakKemble 
```bash
mkdir ~/.avr-gcc/ ; cd ~/.avr-gcc
wget https://github.com/ZakKemble/avr-gcc-build/releases/download/v8.3.0-1/avr-gcc-8.3.0-x64-linux.tar.bz2 && tar -xvf avr-gcc-8.3.0-x64-linux.tar.bz2 && mv avr-gcc-8.3.0-x64-linux 8.3.0
rm ~/.avr-gcc/avr-gcc-8.3.0-x64-linux.tar.bz2
```

# gcc-avr 12.1.0 from ZakKemble 
```bash
mkdir ~/.avr-gcc ; cd ~/.avr-gcc
wget https://github.com/ZakKemble/avr-gcc-build/releases/download/v12.1.0-1/avr-gcc-12.1.0-x64-linux.tar.bz2 && tar -xvf avr-gcc-12.1.0-x64-linux.tar.bz2 && mv avr-gcc-12.1.0-x64-linux 12.1.0
rm ~/.avr-gcc/avr-gcc-12.1.0-x64-linux.tar.bz2
```

# gcc-avr 14.1.0 from ZakKemble 
```bash
mkdir ~/.avr-gcc ; cd ~/.avr-gcc
wget https://github.com/ZakKemble/avr-gcc-build/releases/download/v14.1.0-1/avr-gcc-14.1.0-x64-linux.tar.bz2 && tar -xvf avr-gcc-14.1.0-x64-linux.tar.bz2 && mv avr-gcc-14.1.0-x64-linux 14.1.0
rm ~/.avr-gcc/avr-gcc-14.1.0-x64-linux.tar.bz2 
```

# some environment variables for (my) use of avrgcc (i.e in ~/.bash_exports)
```bash
export GCCAVR=$HOME/.avr-gcc/8.3.0
export LD_LIBRARY_PATH=$GCCAVR/avr/lib
export PATH="$GCCAVR/bin:$PATH"
```

# for easy switching between versions with symlink 'ver'
```bash
cd ~/.avr-gcc/ ; rm ver ; ln -s 8.3.0 ver && avr-gcc -dumpversion
cd ~/.avr-gcc/ ; rm ver ; ln -s 12.1.0 ver && avr-gcc -dumpversion
cd ~/.avr-gcc/ ; rm ver ; ln -s 14.1.0 ver && avr-gcc -dumpversion

# and in ~/.bash_exports
export GCCAVR=$HOME/.avr-gcc/ver
export LD_LIBRARY_PATH=$GCCAVR/avr/lib
export PATH="$GCCAVR/bin:$PATH"
```

# setting of AVRGCC_VERSION
```bash
export AVRGCC_VERSION=$(avr-gcc -dumpversion) ; echo $AVRGCC_VERSION
```
