# Remnux_Installation

# About
REMnux is a Linux distribution designed for malware analysis and reverse engineering. It includes a collection of tools and techniques for analyzing and investigating malicious software, and is widely used by security researchers, malware analysts, and incident responders.
This repository contains the installation procedure of the REmnux tool.

For more details about it, visit [here](https://docs.remnux.org/).

# Installation

# Operating System Setup

- Make sure to Update your ubuntu system before proceeding installation :
```
sudo apt update
sudo apt upgrade -y
```
# Steps to download and install Oracle VM VirtualBox on Ubuntu
- Open a web browser and go to the Oracle VM VirtualBox download page.
- Select the version of VirtualBox that is compatible with your version of Ubuntu.
- Click the "Download" button to begin the download process.
- Once the download is complete, navigate to the directory where the .deb package was downloaded.
- double-click on the downloaded .deb package to open it with the Ubuntu Software Center.
- Click the "Install" button to install the software.
- You may be prompted to enter your password to authorize the installation process.
- wait for the installation process to complete.
- Once the installation is complete, open the VirtualBox application.

# Steps to install REmnux on oracle VM 
# Installing the REMnux in Oracle VM VirtualBox is a straightforward process.:

- Open Oracle VM VirtualBox and click on the "New" button to create a new virtual machine.
- Choose a name for the virtual machine and select "Linux" as the type, and "Ubuntu (64-bit)" as the version.
- Allocate at least 4GB of RAM to the virtual machine, and create a new virtual hard disk with a recommended size of 40GB.
- Once the virtual machine is created, select the newly created virtual machine and click on the "Settings" button.
- In the "Storage" tab, click on the empty CD/DVD icon, and select "Choose Virtual Optical Disk File".
- Navigate to the downloaded REMnux virtual machine file, and select it to insert it into the virtual machine.
- Start the virtual machine and wait for the operating system to load.
- Log in to the REMnux virtual machine using the default credentials provided on the REMnux website.

# steps to configure REMnux after installing it on an Oracle VM running Ubuntu:
- Update the system: Run the command 
```
   sudo apt update 
   sudo apt upgrade 
``` 
to make sure that the system is up to date.
VirtualBox Guest Additions is a set of drivers and software that enhances the performance and functionality of a virtual machine running on VirtualBox. Here's how to install and use VirtualBox Guest Additions on your REMnux virtual machine:
- Start your REMnux virtual machine and log in as root or a user with sudo privileges.
- Click on the "Devices" menu in the VirtualBox menu bar, and select "Insert Guest Additions CD image". This will mount the VirtualBox Guest Additions ISO as a CD in   the virtual machine.
- Install the necessary packages by running the following command:
```
sudo apt-get update
sudo apt-get install build-essential dkms linux-headers-$(uname -r)
```
This command updates the package list and installs the packages required to build kernel modules.
- Install VirtualBox Guest Additions by running the following command:
```
sudo sh ./VBoxLinuxAdditions.run
```
This command starts the installation script for VirtualBox Guest Additions.

- Restart the virtual machine to complete the installation by running the command:
```
sudo reboot
```
After the virtual machine restarts, you should be able to use the enhanced features provided by VirtualBox Guest Additions, such as better video support, shared folders, and seamless mouse integration.
