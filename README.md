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

![pic4](https://user-images.githubusercontent.com/110851315/220863099-409eb488-407d-4f35-acbd-5ad1b25a7fca.png)

- Select the version of VirtualBox that is compatible with your version of Ubuntu.
- Click the "Download" button to begin the download process.
- Once the download is complete, navigate to the directory where the .deb package was downloaded.
- double-click on the downloaded .deb package to open it with the Ubuntu Software Center.

![pic6](https://user-images.githubusercontent.com/110851315/220863147-f2310010-ec72-4862-aed8-ac9f6504dcb2.png)


- Click the "Install" button to install the software.
- You may be prompted to enter your password to authorize the installation process.

![pic7](https://user-images.githubusercontent.com/110851315/220862210-eece1b7d-14ce-4c4c-9292-0afc130564cd.png)

- wait for the installation process to complete.
- Once the installation is complete, open the VirtualBox application.


# Steps to download REmnux from their official site
- To download REMnux from the official site :

![pic1](https://user-images.githubusercontent.com/110851315/220862044-9a55a6f8-d25f-486e-b8a9-cba57e86609e.png)

- Go to the REMnux website at https://remnux.org/ and click on the "Download" link in the top navigation menu.
- On the Downloads page, you'll find various versions of REMnux that you can download, depending on your needs. Select the version you want by clicking on the corresponding link.
- Once you've clicked on the link for the version you want, you'll be taken to a page with download instructions and a list of available mirrors. Choose a mirror from the list by clicking on its link.

![pic2](https://user-images.githubusercontent.com/110851315/220862073-c7fc2e48-c6d6-4543-907e-0d47b2c2008e.png)

- You'll then be redirected to the mirror's website, where you can download the REMnux ISO file. Click on the link to start the download.

![pic3](https://user-images.githubusercontent.com/110851315/220862081-c7723e29-0dbe-43b1-a678-83b43aeae49c.png)



# Steps to install REmnux on oracle VM 
# Installing the REMnux in Oracle VM VirtualBox is a straightforward process.:

- Open Oracle VM VirtualBox and click on the "New" button to create a new virtual machine.

![pic9](https://user-images.githubusercontent.com/110851315/220862343-f364786c-e9b8-4ec5-9608-4d5ff457e8ad.png)

- Choose a name for the virtual machine and select "Linux" as the type, and "Ubuntu (64-bit)" as the version.
- Allocate at least 4GB of RAM to the virtual machine, and create a new virtual hard disk with a recommended size of 40GB.
- Once the virtual machine is created, select the newly created virtual machine and click on the "Settings" button.
- In the "Storage" tab, click on the empty CD/DVD icon, and select "Choose Virtual Optical Disk File".
- Navigate to the downloaded REMnux virtual machine file, and select it to insert it into the virtual machine.

![pic12](https://user-images.githubusercontent.com/110851315/220862374-1fbfd845-3c75-4c2a-817a-8ca39bfb1248.png)

- Start the virtual machine and wait for the operating system to load.

![pic16](https://user-images.githubusercontent.com/110851315/220862440-b8f78d09-eec2-4986-ab83-169cc19bf0dd.png)

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


# Now after Virtualbox Guest Addition you may need to adjust your virtual machine settings to enable certain features . 
For example, Video support, Shared folder , Seamless mouse intergration, Clipboard sharing , Time synchronization, Seamless Window integration, audio support


# Shared folder setup 


A shared folder is a folder on the host operating system that can be accessed from within a virtual machine
- Create a folder on your host operating system that you want to share with the REMnux virtual machine. For example, you can create a folder named "Shared" on your desktop.
- In VirtualBox, select your REMnux virtual machine and click on "Settings" in the VirtualBox menu.
- In the "Settings" window, click on the "Shared Folders" tab.
- Click on the "Add" button to add a new shared folder. In the "Add Share" dialog box, specify the following settings:
- Folder Path: Click on the folder icon to browse for the folder you created in step 1.
- Folder Name: Specify a name for the shared folder. This is the name that the shared folder will have within the virtual machine.
- Check the "Auto-mount" checkbox if you want the shared folder to be automatically mounted when the virtual machine starts.
- Click on "OK" to save the settings and close the "Settings" window.
- Start the REMnux virtual machine and log in as root or a user with sudo privileges.
- Create a directory in the virtual machine where you want to mount the shared folder. For example, you can create a directory named "shared" in the root directory by running the command
```
sudo mkdir /shared
```
- Mount the shared folder by running the following command:
```
sudo mount -t vboxsf <folder-name> /shared
```
- Replace <folder-name> with the name of the shared folder you specified in above step.
  This command mounts the shared folder in the virtual machine at the directory you created in above step.

You can now access the shared folder in the virtual machine by navigating to the directory where you mounted it. For example, if you mounted the shared folder in the directory "/shared", you can access it by running the command:
```
cd /shared
```
You can copy files to and from the shared folder just like you would with any other directory


# Guide for enabling better video support on your REMnux:
- select the REMnux virtual machine in the VirtualBox Manager, click on "Settings", and select the "Display" tab.
- Then, check the "Enable 3D Acceleration" checkbox and click "OK" to save the changes. 

# Snapshots in Oracle VM VirtualBox
   Snapshots in Oracle VM VirtualBox enable you to save the current state of your virtual machine, so you can easily revert to that state later. This is useful for tasks like software testing, configuration experimentation, or backing up your virtual machine.
# To take a snapshot
- Make sure that the REMnux virtual machine is powered off.
- In the VirtualBox Manager window, select the REMnux virtual machine.
- Click on the "Snapshots" button in the top menu bar.
- Click on the "Take" button to create a new snapshot.
- Enter a name and optional description for the snapshot and click "OK".
- The snapshot will be created and added to the list of available snapshots for the virtual machine.
   
# To revert to a previously saved snapshot:

- Power off the virtual machine if it is running.
- Select the virtual machine in the VirtualBox Manager window.
- Click on the "Snapshots" button in the top menu bar.
- Choose the snapshot you want to revert to by clicking on it in the list.
- Click on the "Restore" button to revert the virtual machine to the state it was in at the time the snapshot was taken.
- A confirmation dialog will appear. Click "Restore" to confirm.
- The virtual machine will be reverted to the state of the selected snapshot.

Note that when you restore a snapshot, any changes made to the virtual machine since the snapshot was taken will be lost. If you want to keep these changes, you should create a new snapshot before restoring an old one.
