



[![Docs](https://img.shields.io/badge/docs-latest-brightgreen.svg)](http://doc.servertribe.com)
[![Discord](https://img.shields.io/discord/844971127703994369)](http://discord.servertribe.com)
[![Docs](https://img.shields.io/badge/videos-watch-brightgreen.svg)](https://www.youtube.com/@servertribe)
[![Generic badge](https://img.shields.io/badge/download-latest-brightgreen.svg)](https://www.servertribe.com/community-edition/)

# Automate Windows Installation with autounattend

You can automate Windows installation in several different ways. You can 
use the methods described below to accomplish the level of automation that 
your deployment needs.

You can prevent some or all of the user interface (UI) pages from Windows 
Setup from being displayed during installation. The default behavior of 
Windows Setup is to display the Setup UI if any of the required settings are 
incorrect or empty.

This Attune Project contains the various methods of create ISO(s) required for 
automating the Windows Setup.

## Requries Worker
Blueprints in this Attune Project require a worker to perform some tasks. The 
worker can be either the Attune instance itself or a separate machine.

## Single ISO Windows Setup Method

This is the simplest automated Windows Setup possible with the least 
dependencies and configuration.

**Advantages**
* Simple
* Doesn't require networking
* Reasonably fast

**Disadvantages**
* Requires transferring and unpacking approx 5gb ISO

## Dual ISO Windows Setup Method

This 

**Advantages**
1. Simple
2. Light weight
3. Doesn't require networking
4. Fast

**Disadvantages**
1. Requires two drives (oVirt doesn't accept a second cdrom or floppy)

## WinPE ISO Windows Setup Method

This method uses a samba share that contains each Windows ISO. The WinPE ISO 
is created with the drivers and autounattend files.

**Advantages**
1. Network efficient
2. Best for enterprise

**Disadvantages**
1. Requires the setup of a samba share with the each Windows ISO

## Blueprint Naming Guide

`Create {os_name} {boot_type} autounattend {method} on {worker}`

`os_name`:
* Windows 10 (Win10)
* Windows Server 2016 (Win2016)
* Windows Server 2019 (Win2019)
* Windows Server 2022 (Win2022)

`boot_type`:
* BIOS
* UEFI

The `boot_type` will not be in the Blueprint name if all boot types can be 
created from a single Blueprint.

`method`:
* Single ISO
* Dual ISO
* WinPE ISO

`worker`:
* macOS
* Linux
* Windows

Examples:
* Create Windows 10 (Win10) autounattend Single ISO on Windows
* Create Windows Server (Win2019) autounattend Dual ISO on Linux
* Create Windows Server (Win2022) autounattend WinPE ISO on Linux

## Understanding Autounattend Automation

Autounattend is a technology developed by Microsoft that enables 
system administrators to automate the Windows installation process 
efficiently. Instead of manually configuring each installation, 
Autounattend relies on a predefined configuration file, commonly 
known as an Autounattend.xml file, to specify various installation 
settings. These settings encompass language preferences, disk 
partitioning schemes, software package selections, network 
configuration, and various customization options. The 
Autounattend.xml file effectively scripts the installation process, 
ensuring consistency and repeatability across deployments.

## Advantages of Automated Windows Installation with Autounattend

Automating the installation of Windows operating systems using 
Autounattend offers several significant advantages:

1. **Time Efficiency:** Manual Windows installation can be a 
time-consuming and labor-intensive task, particularly when 
deploying to multiple machines. Autounattend automates the process, 
saving substantial time and effort.

2. **Consistency:** Automated installations ensure that each 
Windows instance is configured identically, reducing the risk of 
errors or discrepancies resulting from manual intervention.

3. **Reduced Human Error:** Manual Windows installations can lead 
to mistakes or deviations in configuration settings. Autounattend 
eliminates these errors by adhering to a predefined installation 
script.

4. **Standardization:** Autounattend promotes standardized 
configurations across the organization, simplifying management 
and troubleshooting of Windows-based systems.

By leveraging the power of Autounattend, system administrators can 
achieve greater efficiency, reliability, and consistency in 
deploying Windows operating systems, ultimately enhancing the 
overall manageability of their IT infrastructure. This project 
provides valuable resources and templates to facilitate the 
creation of Autounattend configuration files, enabling 
administrators to automate Windows installations seamlessly.





# Attune

[Attune](https://www.servertribe.com/)
automates and orchestrates processes to streamline deployments, scaling,
migrations, and management of your systems. The Attune platform is building a
community of sharable automated and orchestrated processes.

You can leverage the publicly available orchestrated blueprints to increase
your productivity, and accelerate the delivery of your projects. You can
open-source your own work and improve existing community orchestrated projects.

## Get Started with Attune, Download NOW!

The **Attune Community Edition** can be
[downloaded](https://www.servertribe.com/comunity-edition/)
for free from our
[ServerTribe website](https://www.servertribe.com/comunity-edition/).
You can learn more about Attune through
[ServerTribe's YouTube Channel](https://www.youtube.com/@servertribe).







# Clone this Project

To clone this project into your own instance of Attune, follow the
[Clone a GIT Project How To Instructions](https://servertribe-attune.readthedocs.io/en/latest/howto/design_workspace/clone_project.html).




## Blueprints

This Project contains the following Blueprints.



### Create Windows 10 (Win10) autounattend Dual ISO on macOS or Linux Worker


### Create Windows 10 (Win10) autounattend Single ISO on macOS or Linux Worker

Creates a single Windows Desktop 10 ISO with `autounattend.xml` for unattended installation.

The ISO will be created at `{ksAttuneBaseDir}/kickstart_{kickstartedNode.fqn}.iso`.

For both BIOS and UEFI kickstarts.

For BIOS kickstarts please set `isWin10Bios` to the string 'true'.

For UEFI kickstarts please set `isWin10Uefi` to the string 'true'.

Please set `isWinPEKickstart` to the string 'false'.

This blueprint assumes the drivers drop in directory is at `{automationWorkerBaseDirectory}/drivers-{newOsNode.fqn}` and has the correct drivers dropped in.

### Create Windows Server 2016 (Win2016) autounattend Dual ISO on macOS or Linux Worker


### Create Windows Server 2016 (Win2016) autounattend Single ISO on macOS or Linux Worker

Creates a single Windows Server 2016 ISO with `autounattend.xml` for unattended installation.

The ISO will be created at `{ksAttuneBaseDir}/kickstart_{kickstartedNode.fqn}.iso`.

For both BIOS and UEFI kickstarts.

For BIOS kickstarts please set `isWinServerBios` to the string 'true'.

For UEFI kickstarts please set `isWinServerUefi` to the string 'true'.

Please set `isWinPEKickstart` to the string 'false'.

This blueprint assumes the drivers drop in directory is at `{automationWorkerBaseDirectory}/drivers-{newOsNode.fqn}` and has the correct drivers dropped in.

### Create Windows Server 2019 (Win2019) autounattend Dual ISO on macOS or Linux Worker


### Create Windows Server 2019 (Win2019) autounattend Single ISO on macOS or Linux Worker

Creates a single Windows Server 2019 ISO with `autounattend.xml` for unattended installation.

The ISO will be created at `{ksAttuneBaseDir}/kickstart_{kickstartedNode.fqn}.iso`.

For both BIOS and UEFI kickstarts.

For BIOS kickstarts please set `isWinServerBios` to the string 'true'.

For UEFI kickstarts please set `isWinServerUefi` to the string 'true'.

Please set `isWinPEKickstart` to the string 'false'.

This blueprint assumes the drivers drop in directory is at `{automationWorkerBaseDirectory}/drivers-{newOsNode.fqn}` and has the correct drivers dropped in.

### Create Windows Server 2022 (Win2022) autounattend Dual ISO on macOS or Linux Worker


### Create Windows Server 2022 (Win2022) autounattend Single ISO on macOS or Linux Worker

Creates a single Windows Server 2022 ISO with `autounattend.xml` for unattended installation.

The ISO will be created at `{ksAttuneBaseDir}/kickstart_{kickstartedNode.fqn}.iso`.

For both BIOS and UEFI kickstarts.

For BIOS kickstarts please set `isWinServerBios` to the string 'true'.

For UEFI kickstarts please set `isWinServerUefi` to the string 'true'.

Please set `isWinPEKickstart` to the string 'false'.

This blueprint assumes the drivers drop in directory is at `{automationWorkerBaseDirectory}/drivers-{newOsNode.fqn}` and has the correct drivers dropped in.

### Perform Post Cleanup


### Perform Test Win Node

Performs basic tests for the built node.




## Parameters


| Name | Type | Script Reference | Comment |
| ---- | ---- | ---------------- | ------- |
| Automation Worker Base Directory | Text | `automationworkerbasedirectory` | Base directory for deploying temporary files to build the kickstart ISO. |
| Automation Worker Linux Node | Linux/Unix Node | `automationworkerlinuxnode` | The device used to perform tasks to create the ISO. |
| Automation Worker Linux User | Linux/Unix Credential | `automationworkerlinuxuser` | Non privilege user on the Automation Worker node. |
| Drivers and Autounattend Drive Letter | Text | `driversandautounattenddriveletter` | The Windows drive letter containing the drivers and autounattend.xml as a single letter.<br><br>This will be different for each install method.<br>D for "Single ISO"<br>E for "Dual ISO"<br>X for "WinPE ISO" |
| Is Win10 BIOS | Text | `iswin10bios` |  |
| Is Win10 UEFI | Text | `iswin10uefi` |  |
| Is WinPE Kickstart | Text | `iswinpekickstart` | Set TRUE for WinPE kickstarts and FALSE for Single ISO and Dual ISO kickstarts. |
| Is Win Server BIOS | Text | `iswinserverbios` |  |
| Is Win Server UEFI | Text | `iswinserveruefi` |  |
| Kickstarted Boot Loader is BIOS | Text | `kickstartedbootloaderisbios` |  |
| Kickstarted Boot Loader is UEFI | Text | `kickstartedbootloaderisuefi` |  |
| Kickstarted Linux Node | Linux/Unix Node | `kickstartedlinuxnode` | Refers to the node being built. |
| Kickstarted Operating System Name | Text | `kickstartedoperatingsystemname` | Set as:<br>"Windows 10",<br>"Windows Server 2016",<br>"Windows Server 2019",<br>"Windows Server 2022" |
| Linux: Attune User - DELETE | Linux/Unix Credential | `linuxattuneuserdelete` |  |
| New OS Node | Basic Node | `newosnode` | The New OS to be built. |
| New OS Node Subnet | Network IPv4 Subnet | `newosnodesubnet` | Subnet used by the new operating system to be built. |
| New OS Organisation Name | Text | `newosorganisationname` | Organisation name for the new operating system being created. |
| New OS Windows Node | Windows Node | `newoswindowsnode` |  |
| New OS Windows TimeZone | Text | `newoswindowstimezone` | Get the full list using the PowerShell command:<br>Get-TimeZone -ListAvailable |
| New OS Windows User: Administrator | Windows Credential | `newoswindowsuseradministrator` | administrator user on the New OS to be built. |
| Post Install Setup Script Drive Letter | Text | `postinstallsetupscriptdriveletter` | The Windows drive letter containing the Post Install PowerShell setup script post_install_setup.ps1 as a single letter as seen by the Windows installer.<br><br>This will be different for each install method.<br><br>D for "Single ISO"<br>E for "Dual ISO"<br>C for "WinPE ISO" |




## Files

| Name | Type | Comment |
| ---- | ---- | ------- |
| Post Install Setup PowerShell Script | Version Controlled Files | This file is called by the "<FirstLogonCommands>" section in the autounattend.xml file.<br><br>This script is run once post installation of the WIndows operating system. |
| Test File | Version Controlled Files | Test file for testing push files. |
| Win10 Desktop ISO | Large Archives | Download from https://www.microsoft.com/en-us/software-download/windows10ISO/.<br><br>Please select the English (United States) version. |
| Windows Server 2019 ISO | Large Archives | Download from https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019. |
| Windows Unattended config | Version Controlled Files | For these Windows versions:<br>* WIndows Desktop 10<br>* WIndows Server 2016<br>* WIndows Server 2019<br>* WIndows Server 2022<br><br>For these boot methods:<br>* BIOS<br>* UEFI |
| WIN Raw Win2016 ISO | Large Archives | Download from https://www.microsoft.com/en-us/evalcenter/download-windows-server-2016. |
| WIN Raw Win2022 ISO | Large Archives | Download from https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022. |






# Contribute to this Project

**The collective power of a community of talented individuals working in
concert delivers not only more ideas, but quicker development and
troubleshooting when issues arise.**

If you’d like to contribute and help improve these projects, please fork our
repository, commit your changes in Attune, push you changes, and create a
pull request.

<img src="https://www.servertribe.com/wp-content/uploads/2023/02/Attune-pull-request-01.png" alt="pull request"/>

---

Please feel free to raise any issues or questions you have.

<img src="https://www.servertribe.com/wp-content/uploads/2023/02/Attune-get-help-02.png" alt="create an issue"/>


---

**Thank you**
