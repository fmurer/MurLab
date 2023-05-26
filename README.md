# README - MurLAB

## Requirements

### Vagrant Reload Plugin
The vagrant reload plugin needs to be installed. To do so:
```PowerShell
vagrant plugin install vagrant-reload 
```

### Download and Adding Boxes

1. Download the boxes [here](http://example.com) and unzip them
2. Add the boxes to your vagrant environment

```
vagrant box add win2019eval PATH_TO_BOX
vagrant box add win10 PATH_TO_BOX
```
### Create own Boxes

1. Create a new VM to your needs
2. Run the following command to create a box

```PowerShell
vagrant package --base Windows_Server_2019 --output win2019eval.box
```

## Installation

## Velociraptor-Server
```
username: admin
password: SuperSecret
```