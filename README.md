# AUKS
Auks is an open source project that helps Batch Systems to provide 
Kerberos Credential Support. Auks is not an authentication system.
It only enables to set up a trusted remote cache system for storage 
and retrieval of Kerberos TGT.

# Ubuntu 20.04

## Build

```bash
apt-get install --yes flex bison libkrb5-dev libtirpc-dev
mkdir -p ~/git
pushd ~/git
git clone https://github.com/hautreux/auks.git
cd auks/
aclocal && libtoolize --force && automake --add-missing && autoreconf
./configure
make
```

## Install


## Configure


## Test

