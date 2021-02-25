# AUKS
Auks is an open source project that helps Batch Systems to provide 
Kerberos Credential Support. Auks is not an authentication system.
It only enables to set up a trusted remote cache system for storage 
and retrieval of Kerberos TGT.

# Ubuntu 20.04

## Install Pre-reqs
This assumes that you've installed slurm-wlm

```bash
apt-get install --yes flex bison libkrb5-dev libtirpc-dev libslurm-dev
```

## Clone and configure build
```bash
mkdir -p ~/git
pushd ~/git
git clone git@github.com:CGRET/auks.git
cd auks/
./autogen.sh
./configure --prefix=/usr --with-slurm
```

## Install
```bash
make
sudo make install
```

## Configure installed

SLURM plugin for AUKS.
```bash
echo "optional /usr/lib/slurm/auks.so default=disabled spankstackcred=no minimum_uid=0 sync=no" >> src/plugins/slurm/slurm-spanks-auks.conf
sudo cp src/plugins/slurm/slurm-spanks-auks.conf /etc/slurm-llnl/plugstack.conf.d/
```

## Test

