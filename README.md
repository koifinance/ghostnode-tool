# Ghostnode Tool

[![Build Status Travis CI](hhttps://github.com/nixplatform/ghostnode-tool.svg?branch=master)](https://github.com/nixplatform/ghostnode-tool) [![Build status AppVeyor](https://ci.appveyor.com/api/projects/status/kkcf324yn6dn6woj/branch/master?svg=true)](https://ci.appveyor.com/project/nixplatform/ghostnode-tool/branch/master)

The main purpose of the application is to give Ghostnode (NIX masternode) operators the ability to send the "start Ghostnode" command through an easy to use a graphical user interface if the Ghostnode collateral is controlled by a hardware wallet such as Trezor or Ledger.

Ghostnode Tool is based on [Dash Masternode Tool (DMT)](https://github.com/Bertrand256/dash-masternode-tool) by Bertrand256. Ghostnodes and Dash masternodes are very similar, so most of the [original DMT documentation](README-DMT.md) still applies to Ghostnode Tool as well.

## Feature list

* Sending the "start Ghostnode" command if the collateral is controlled by a hardware wallet
* Transferring Ghostnode earnings safely, without touching the 40000 NIX funding transaction
* Signing messages with a hardware wallet
* Initialization/recovery of hardware wallets seeds
* Updating of hardware wallets firmware (Trezor)
* Support for NIX Testnet

## Supported hardware wallets

- Trezor (model One and T)
- Ledger Nano S

## Note on binary Linux builds

Binary Linux builds are known to be not reliable due to ABI incompatibility between different Linux distributions. You might want to build Ghostnode Tool yourself if provided binary does not work for your distribution:
```
sudo apt-get update
sudo apt-get -y upgrade
sudo apt-get -y install libudev-dev libusb-1.0-0-dev libfox-1.6-dev autotools-dev autoconf automake libtool libpython3-all-dev python3-pip git
sudo pip3 install virtualenv
virtualenv -p python3 venv
. venv/bin/activate
pip install --upgrade setuptools
git clone https://github.com/nixplatform/ghostnode-tool/
cd ghostnode-tool/
pip install -r requirements.txt
pyinstaller ghostnode-tool.spec
```

Ghostnode Tool requires Python 3.6. Use [pyenv](https://github.com/pyenv/pyenv) if you distribution comes with older python version. Run following command before installing Python with pyenv:
```
export PYTHON_CONFIGURE_OPTS="--enable-shared --disable-static"
```
