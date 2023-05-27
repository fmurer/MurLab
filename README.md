# README - MurLAB

## Requirements

### Vagrant Reload Plugin
The vagrant reload plugin needs to be installed. To do so:
```PowerShell
vagrant plugin install vagrant-reload 
vagrant plugin install virtualbox_WSL2
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

## Known Issues

### Invalid Permissions SSH Private Key
Using `WSL2`, there is an issue with wrong permissions of the vagrand SSH private key as it defaults to `777` and cannot be changed, because it is located outside of `WSL`. To solve this, follow these steps:

1. Move the key inside `WSL`
2. Change the key's permission to `0600`
3. Create a soft-link to the key's original location