# Born2beRoot
## Summary
_This document is a **System Administration** related exercise._
### What is a System Administrator?
>A [system administrator](https://en.wikipedia.org/wiki/System_administrator) is a person who is responsible for the upkeep, configuration, and reliable operation of computer systems; especially multi-user computers, such as servers. The system administrator seeks to ensure that the uptime, performance, resources, and security of the computers they manage meet the needs of the users, without exceeding a set budget when doing so.
## Introduction
_This project aims to introduce you to the wonderful world of **virtualization**._

- [x] _You will **create your first machine in VirtualBox** (or UTM if you can’t use VirtualBox)
under specific instructions. Then, at the end of this project, you will be able to set up
your own operating system while implementing strict rules._
### What is virtualization?
>When we describe VirtualBox as a ["virtualization"](https://www.virtualbox.org/wiki/Virtualization) product, we refer to "full virtualization", that is, the particular kind of virtualization that allows an unmodified operating system with all of its installed software to run in a special environment, on top of your existing operating system. This environment, called a "virtual machine", is created by the virtualization software by intercepting access to certain hardware components and certain features. The physical computer is then usually called the "host", while the virtual machine is often called a "guest". Most of the guest code runs unmodified, directly on the host computer, and the guest operating system "thinks" it's running on real machine.

>There are several scenarios that make virtualization attractive:
>- **Operating system support.** With a virtualizer such as VirtualBox, one can run software written for one operating system on another (say, Windows software on Linux) without having to reboot.
>- **Infrastructure consolidation.** Since the full performance of today's computers is rarely needed full-time, instead of running many such physical computers, one can "pack" many virtual machines onto a few powerful hosts and balance the loads between them. This can save a lot of hardware costs: e.g. by consolidating many servers into a few.
>- **Testing and disaster recovery.** Especially with the use of snapshots, one can mess with a computing environment by running it as a virtual machine. If something goes wrong, one can easily switch back to a previous snapshot and avoid the need of frequent backups and restores.

### How to [create a virtual machine](https://www.virtualbox.org/manual/UserManual.html#gui-createvm) in VirtualBox?
>Click New in the VirtualBox Manager window.

>![image](https://user-images.githubusercontent.com/60623613/140510013-8ac8b077-a4f8-434e-9064-b417594b3776.png)

>For Operating System Type, select the OS that you want to install.

>![image](https://user-images.githubusercontent.com/60623613/140510188-122f1ed6-d62a-4094-b918-6dc5ed8bbbd2.png)

>On the next page, select the Memory (RAM) that Oracle VM VirtualBox should allocate every time the virtual machine is started. The amount of memory given here will be taken away from your host machine and presented to the guest OS, which will report this size as the virtual computer's installed RAM.

>![image](https://user-images.githubusercontent.com/60623613/140510263-cc879637-3f4b-48ac-91e3-3c74f9540d5b.png)

>To create a new, empty virtual hard disk, click the Create button.

>![image](https://user-images.githubusercontent.com/60623613/140510381-47666bfa-a900-4153-b3c3-d7c58f0df34e.png)

>![image](https://user-images.githubusercontent.com/60623613/140510419-6263288d-86c1-4d79-ae0c-4efdf63e77b1.png)

>A dynamically allocated file only grows in size when the guest actually stores data on its virtual hard disk. Therefore, this file is small initially. As the drive is filled with data, the file grows to the specified size.

>![image](https://user-images.githubusercontent.com/60623613/140510510-09d70e08-135d-4b2b-9203-1dbde481f50f.png)

>![image](https://user-images.githubusercontent.com/60623613/140510531-8b1b6965-c4ae-4763-9299-b767eac1b96e.png)

>When a VM is started for the first time, the First Start Wizard, is displayed. This wizard helps you to select an installation medium. Since the VM is created empty, it would otherwise behave just like a real computer with no OS installed. It will do nothing and display an error message that no bootable OS was found.

>![image](https://user-images.githubusercontent.com/60623613/140512001-c7fc0f10-b80c-4378-a4ba-ac75f27fd57f.png)

>If you have [downloaded](https://www.debian.org/download) installation media from the Internet in the form of an ISO image file such as with a Linux distribution, you would normally burn this file to an empty CD or DVD and proceed as described above. With Oracle VM VirtualBox however, you can skip this step and mount the ISO file directly. Oracle VM VirtualBox will then present this file as a CD or DVD-ROM drive to the virtual machine, much like it does with virtual hard disk images.

## General guidelines
_The use of VirtualBox (or UTM if you can’t use VirtualBox) is mandatory._

- [ ] _You only have to turn in a signature.txt file at the root of your repository. You
must paste in it the **signature** of your machine’s virtual disk._
>To get this signature, you first have to open the default installation folder
(it is the folder where your VMs are saved):
>- Windows: %HOMEDRIVE%%HOMEPATH%\VirtualBox VMs\
>- Linux: ~/VirtualBox VMs/
>- MacM1: ~/Library/Containers/com.utmapp.UTM/Data/Documents/
>- MacOS: ~/VirtualBox VMs/

>Then, retrieve the signature from the **".vdi"** file (or ".qcow2 for UTM’users) of your
virtual machine in sha1 format. Below are 4 command examples for a centos_serv.vdi
file:
>- Windows: certUtil -hashfile centos_serv.vdi sha1
>- Linux: sha1sum centos_serv.vdi
>- For Mac M1: shasum Centos.utm/Images/disk-0.qcow2
>- MacOS: shasum centos_serv.vdi
>This is an example of what kind of output you will get:
>- 6e657c4619944be17df3c31faa030c25e43e40af

### What is virtual disk signature?
>A [disk signature](https://www.lifewire.com/what-is-a-disk-signature-2625851) is a unique, identifying number for a hard disk drive or other data storage device stored as part of the master boot record. An operating system uses it to differentiate among storage devices on your computer.
### What is a ".vdi" file?
>[Disk image files](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/vdidetails.html) reside on the host system and are seen by the guest systems as hard disks of a certain geometry. When a guest OS reads from or writes to a hard disk, Oracle VM VirtualBox redirects the request to the image file.
>- **VDI.** Normally, Oracle VM VirtualBox uses its own container format for guest hard disks. This is called a Virtual Disk Image (VDI) file. This format is used when you create a new virtual machine with a new disk.
## Mandatory part
- [x] _You must choose as an operating system either the **latest stable version** of **Debian** (no
testing/unstable), or the latest stable version of **CentOS**. Debian is highly recommended
if you are new to system administration._
### Why choose Debian?
>There are a lot of reasons to [choose Debian](https://www.debian.org/intro/why_debian) as your operating system – as a user, as a developer, and even in enterprise environments. Most users appreciate the stability, and the smooth upgrade processes of both packages and the entire distribution. Debian is also widely used by software and hardware developers because it runs on numerous architectures and devices, offers a public bug tracker and other tools for developers. If you plan to use Debian in a professional environment, there are additional benefits like LTS versions and cloud images.
### Why choose the latest stable version?
>The [latest release](https://wiki.debian.org/DebianReleases) is Debian 11.1. It is also (currently) known as stable or by its codename "Bullseye".At any given time, there is one stable release of Debian, which has the support of the Debian security team. When a new stable version is released, the security team will usually cover the previous version for a year or so, while they also cover the new/current version. Only stable is recommended for production use. Stable is recommended for applications requiring production-level stability and security (servers, firewalls etc) and is also recommended for those who are new to Linux.

### How to [install Debian](https://www.debian.org/doc/manuals/debian-handbook/sect.installation-steps.en.html)?
>For a standard installation, you only need to choose “Install” or “Graphical install” (with the arrow keys), then press the Enter key to initiate the remainder of the installation process.

>![image](https://user-images.githubusercontent.com/60623613/140512599-b71d5ab2-6e4f-4755-a2ce-dd422fec0315.png)

>The installation program begins in English, but the first step allows the user to choose the language that will be used in the rest of the process. Choosing French, for example, will provide an installation entirely translated into French (and a system configured in French as a result). This choice is also used to define more relevant default choices in subsequent stages (notably the keyboard layout).

>![image](https://user-images.githubusercontent.com/60623613/140512720-09b48988-5aa9-45c9-9a1e-eb22b1ef53be.png)

>The second step consists in choosing your country. Combined with the language, this information enables the program to offer the most appropriate keyboard layout. This will also influence the configuration of the time zone. In the United States, a standard QWERTY keyboard is suggested, and a choice of appropriate time zones is offered.

>![image](https://user-images.githubusercontent.com/60623613/140512827-0c3552b5-19dc-460a-bea1-a6b1c843e96d.png)
>![image](https://user-images.githubusercontent.com/60623613/140512932-7a006e1f-1204-4dde-a952-a200ef4c9934.png)
>![image](https://user-images.githubusercontent.com/60623613/140513021-cd99398e-0556-49c3-80a1-71f9c46a0ba5.png)

- [x] _The **hostname of your virtual machine must be your login ending with 42** (e.g.,
wil42). You will have to modify this hostname during your evaluation._

>![image](https://user-images.githubusercontent.com/60623613/140513375-37de4146-4116-4f75-b2dc-a08461fc53a8.png)

>[Correct domain name for a home desktop Linux machine](https://superuser.com/questions/889456/correct-domain-name-for-a-home-desktop-linux-machine)

>![image](https://user-images.githubusercontent.com/60623613/140513550-b13b07bd-be16-4aef-a937-ec99b6798a62.png)

>The super-user root account, reserved for the machine's administrator, is automatically created during installation; this is why a password is requested. The installer also asks for a confirmation of the password to prevent any input error which would later be difficult to amend. Note that you can leave both fields empty if you want the root account to be disabled. In that case, the first regular user — that will be created by the installer in the next step — will have administrative rights through sudo.

>![image](https://user-images.githubusercontent.com/60623613/140513836-36af19ba-e853-4236-812b-fb521df0c52e.png)

>Debian also imposes the creation of a standard user account so that the administrator doesn't get into the bad habit of working as root. The precautionary principle essentially means that each task is performed with the minimum required rights, in order to limit the damage caused by human error. This is why the installer will ask for the complete name of this first user, their username, and their password (twice, to prevent the risk of erroneous input).

>![image](https://user-images.githubusercontent.com/60623613/140514046-d7ad13dc-6b8f-44da-9602-58d6908df958.png)

- [x] _In addition to the root user, a **user with your login as username** has to be present._

>![image](https://user-images.githubusercontent.com/60623613/140514114-520bcafe-aafb-4e26-ba8f-84244ede8151.png)

>If the network is available, the system's internal clock is updated (in a one-shot way) from an NTP server. This way the timestamps on logs will be correct from the first boot. For them to remain consistently precise over time, an NTP daemon needs to be set up after initial installation.

>![image](https://user-images.githubusercontent.com/60623613/140514336-a0d050e2-e5b0-444e-9190-49e19fcbf69a.png)

- [x] _You must create **at least 2 encrypted partitions** using **LVM**. Below is an example of the
expected partitioning:_

>![image](https://user-images.githubusercontent.com/60623613/140404704-3dba0778-8f45-41c8-9cdd-757b2c1d93ec.png)

### What is partitioning?
>[Partitioning](https://www.debian.org/doc/manuals/debian-handbook/sect.installation-steps.en.html#sect.install-partman), an indispensable step in installation, consists in dividing the available space on the hard drives (each subdivision thereof being called a “partition”) according to the data to be stored on it and the use for which the computer is intended. This step also includes choosing the filesystems to be used. All of these decisions will have an influence on performance, data security, and the administration of the server

>The partitioning step is traditionally difficult for new users. It is necessary to define the various portions of the disks (or “partitions”) on which the Linux filesystems and virtual memory (swap) will be stored. This task is complicated if another operating system that you want to keep is already on the machine. Indeed, you will then have to make sure that you do not alter its partitions (or that you resize them without causing damage).

>Fortunately, the partitioning software has a “guided” mode which recommends partitions for the user to make — in most cases, you can simply validate the software's suggestions.

>![image](https://user-images.githubusercontent.com/60623613/140538831-062ca7b4-d87d-44da-9a9f-629438ad77d9.png)

>The next screen offers to choose the disk where Linux will be installed by selecting the corresponding entry (for example, “SCSI1 (0,0,0) (sda) - 21.5 GB ATA QEMU HARDDISK”). You then start guided partitioning.

>![image](https://user-images.githubusercontent.com/60623613/140539018-af120c14-c956-4f5f-aa95-1a0e8f3179cc.png)

>The first method is called “All files in one partition”. The entire Linux system tree is stored in a single filesystem, corresponding to the root / directory. This simple and robust partitioning fits perfectly for personal or single-user systems. In fact, two partitions will be created: the first will house the complete system, the second the virtual memory (swap).

>The second method, “Separate /home partition”, is similar, but splits the file hierarchy in two: one partition contains the Linux system (/), and the second contains “home directories” (meaning user data, in files and subdirectories available under /home/).

>![image](https://user-images.githubusercontent.com/60623613/140540673-fbed1f93-ea2b-4288-aa4d-8a163b71df30.png)

>![image](https://user-images.githubusercontent.com/60623613/140543145-0995cad5-9876-4362-b4d5-e58156ccb725.png)

### What is LVM?
>[LVM](https://www.debian.org/doc/manuals/debian-handbook/advanced-administration.en.html#sect.lvm) allows you to create “virtual” partitions that span over several disks. The benefits are twofold: the size of the partitions are no longer limited by individual disks but by their cumulative volume, and you can resize existing partitions at any time, possibly after adding an additional disk when needed.

>LVM uses a particular terminology: a virtual partition is a “logical volume”, which is part of a “volume group”, or an association of several “physical volumes”. Each of these terms in fact corresponds to a “real” partition (or a software RAID device).

>![image](https://user-images.githubusercontent.com/60623613/140537250-7a63e5b7-eb9f-4f86-8fd4-7f2bb28f4d1a.png)

>![image](https://user-images.githubusercontent.com/60623613/140537285-9f0baae5-6cf5-4c2d-a70e-79604e472fb9.png)

>This technique works in a very simple way: each volume, whether physical or logical, is split into blocks of the same size, which are made to correspond by LVM. The addition of a new disk will cause the creation of a new physical volume, and these new blocks can be associated to any volume group. All of the partitions in the volume group that is thus expanded will have additional space into which they can extend.

### Why use encrypted partitions?
>To guarantee the confidentiality of your data, for instance in the event of the loss or theft of your computer or a hard drive, it is possible to encrypt the data on some partitions. This feature can be added underneath any filesystem, since, as for LVM, Linux uses the Device Mapper to create a virtual partition based on an underlying partition that will store the data in an encrypted form.
### Why use at least 2 encrypted partitions?
>When an encrypted partition is used, the encryption key is stored in memory (RAM). Since retrieving this key allows the decryption of the data, it is of utmost importance to avoid leaving a copy of this key that would be accessible to the possible thief of the computer or hard drive, or to a maintenance technician. This is, however, something that can easily occur with a laptop, since when hibernating the contents of RAM is stored on the swap partition. If this partition isn't encrypted, the thief may access the key and use it to decrypt the data from the encrypted partitions. This is why, when you use encrypted partitions, it is imperative to also encrypt the swap partition!

<hr>

>The software will then propose to initialize the physical volume with random data (making the localization of the real data more difficult), and will ask you to enter an “encryption passphrase”, which you will have to enter every time you boot your computer in order to access the content of the encrypted partition. Once this step has been completed, and you have returned to the partitioning tool menu, a new partition will be available in an “encrypted volume”, which you can then configure just like any other partition. In most cases, this partition is used as a physical volume for LVM so as to protect several partitions (LVM logical volumes) with the same encryption key, including the swap partition.

>![image](https://user-images.githubusercontent.com/60623613/140543288-7f0fe6f5-ba14-46f5-8668-d139288eceb1.png)

>![image](https://user-images.githubusercontent.com/60623613/140545402-287e6637-c3d4-4c33-aaba-55bef308f7b6.png)

>![image](https://user-images.githubusercontent.com/60623613/140551160-1a5b92b4-8e08-443b-9f15-6c9bedeaa17a.png)

>![image](https://user-images.githubusercontent.com/60623613/140551283-5a3679b1-d19a-4689-8f5f-41ce908a3f16.png)

>![image](https://user-images.githubusercontent.com/60623613/140551340-3d787bf1-866a-4cf8-b1f3-f816ab060ef6.png)

>This step, which doesn't require any user interaction, installs the Debian “base system” packages. This includes the dpkg and apt tools, which manage Debian packages, as well as the utilities necessary to boot the system and start using it.

>![image](https://user-images.githubusercontent.com/60623613/140551477-2d7661d7-9da6-4039-b7d8-8d607adc861e.png)

>If the installer detects a Debian installation disk in the CD/DVD reader, it is not necessary to configure APT to go looking for packages on the network: APT is automatically configured to read packages from a removable media drive. If the disk is part of a set, the software will offer to “explore” other disks in order to reference all of the packages stored on them.

>![image](https://user-images.githubusercontent.com/60623613/140553971-832d8b2d-90f2-4216-8f53-d9e12014cf22.png)

>If getting packages from the network is requested, the next two questions allow to choose a server from which to download these packages, by choosing first a country, then a mirror available in that country (a mirror is a public server hosting copies of all the files of the Debian master archive).

>![image](https://user-images.githubusercontent.com/60623613/140554280-a0d7448f-3464-417f-b5c1-b7f0d2e03369.png)

>![image](https://user-images.githubusercontent.com/60623613/140554322-c5cd7aea-5769-478a-9891-27b4cf21a475.png)

>Finally, the program proposes to use an HTTP proxy. If there is no proxy, Internet access will be direct.
>- An HTTP proxy is a server that forwards an HTTP request for network users. It sometimes helps to speed up downloads by keeping a copy of files that have been transferred through it (we then speak of proxy/cache). In some cases, it is the only means of accessing an external web server; in such cases it is essential to answer the corresponding question during installation for the program to be able to download the Debian packages through it.

>![image](https://user-images.githubusercontent.com/60623613/140554649-e9874e98-8cf0-4e19-9fa5-21f9df40eaaf.png)

>The Debian system contains a package called popularity-contest, whose purpose is to compile package usage statistics. Each week, this program collects information on the packages installed and those used recently, and anonymously sends this information to the Debian project servers. The project can then use this information to determine the relative importance of each package, which influences the priority that will be granted to them. In particular, the most “popular” packages will be included in the installation CD-ROM, which will facilitate their access for users who do not wish to download them or to purchase a complete set.

>![image](https://user-images.githubusercontent.com/60623613/140555001-68b38921-6c9d-499c-897b-08de3ea2d01b.png)

_⚠️ **WARNING:** Since it is a matter of setting up a server, you will install the
minimum of services. For this reason, a **graphical interface** is of no
use here. It is therefore forbidden to install X.org or any other
equivalent graphics server. Otherwise, your grade will be 0._
### What is a graphical interface?
>The [graphical user interface](https://en.wikipedia.org/wiki/Graphical_user_interface) (GUI) 
allows users to interact with electronic devices through graphical icons and audio indicator such as primary notation, instead of text-based user interfaces, typed command labels or text navigation.

>![image](https://user-images.githubusercontent.com/60623613/140555452-ed195323-bcd3-433c-96e0-b112dfc01bf8.png)

>The bootloader is the first program started by the BIOS. This program loads the Linux kernel into memory and then executes it. It often offers a menu that allows the user to choose the kernel to load and/or the operating system to boot.

>![image](https://user-images.githubusercontent.com/60623613/140557462-c42375fe-1f87-451d-a09e-db5956b58080.png)

>![image](https://user-images.githubusercontent.com/60623613/140558111-1bb737a0-ad14-4b7a-b962-69397931155c.png)

>![image](https://user-images.githubusercontent.com/60623613/140559010-f62eada8-9b11-4121-bba8-cc2a9abdf5c0.png)

_ℹ️ **INFO:** Setting up CentOS is quite complex. Therefore, you don’t have to
set up KDump. However, SELinux must be running at startup and its
configuration has to be adapted for the project’s needs. **AppArmor**
for Debian must be running at startup too._

### What is AppArmor?
>[AppArmor](https://debian-handbook.info/browse/stable/sect.apparmor.html) is a Mandatory Access Control (MAC) system built on Linux's LSM (Linux Security Modules) interface. In practice, the kernel queries AppArmor before each system call to know whether the process is authorized to do the given operation. Through this mechanism, AppArmor confines programs to a limited set of resources.

>AppArmor applies a set of rules (known as “profile”) on each program. The profile applied by the kernel depends on the installation path of the program being executed. Contrary to SELinux, the rules applied do not depend on the user. All users face the same set of rules when they are executing the same program (but traditional user permissions still apply and might result in different behavior!).

>AppArmor profiles are stored in /etc/apparmor.d/ and they contain a list of access control rules on resources that each program can make use of. The profiles are compiled and loaded into the kernel by the apparmor_parser command. Each profile can be loaded either in enforcing or complaining mode. The former enforces the policy and reports violation attempts, while the latter does not enforce the policy but still logs the system calls that would have been denied.

>AppArmor support is built into the standard kernels provided by Debian. Enabling AppArmor is thus just a matter of installing some packages by executing apt install apparmor apparmor-profiles apparmor-utils with root privileges.

### What is Mandatory Access Control?
>In computer security, [mandatory access control](https://en.wikipedia.org/wiki/Mandatory_access_control) (MAC) refers to a type of access control by which the operating system or database constrains the ability of a subject or initiator to access or generally perform some sort of operation on an object or target. In the case of operating systems, a subject is usually a process or thread; objects are constructs such as files, directories, TCP/UDP ports, shared memory segments, IO devices, etc. Subjects and objects each have a set of security attributes. Whenever a subject attempts to access an object, an authorization rule enforced by the operating system kernel examines these security attributes and decides whether the access can take place. Any operation by any subject on any object is tested against the set of authorization rules (aka policy) to determine if the operation is allowed

### How to check if AppArmor is running?
>The [`aa-status`](https://gitlab.com/apparmor/apparmor/-/wikis/AppArmorMonitoring#high-level-view) tool gives a high level status of AppArmor and applications it has profiles for (as root).

![image](https://user-images.githubusercontent.com/60623613/140406297-12047d36-09da-4e33-a19f-98dd45e55b34.png)

_ℹ️ **INFO:** During the defense, you will be asked a few questions about the
operating system you chose. For instance, you should know the
differences between **aptitude and apt**, or what SELinux or **AppArmor**
is. In short, understand what you use!_

### What is APT?
>[APT](https://www.debian.org/doc/manuals/debian-handbook/sect.apt-frontends.en.html#sect.aptitude) is a C++ program whose code mainly resides in the libapt-pkg shared library. APT is a vast project, whose original plans included a graphical interface.

### What is apt?
>apt-get is the first front end — command-line based — which was developed within the project. [apt](https://www.debian.org/doc/manuals/debian-handbook/sect.apt-get.en.html) is a second command-line based front end provided by APT which overcomes some design mistakes of apt-get. The default behavior of apt has been improved for interactive use and to actually do what most users expect. The APT developers reserve the right to change the public interface of this tool to further improve it. On the opposite, the public interface of apt-get is well defined and will not change in any backwards incompatible way. It is thus the tool that you want to use when you need to script package installation requests.

### What is aptitude?
>[aptitude](https://www.debian.org/doc/manuals/aptitude/pr01s01.en.html) is a featureful package manager for Debian GNU/Linux systems, based on the renowned apt package management infrastructure. aptitude provides the functionality of dselect and apt-get, as well as many additional features not found in either program.

>[Aptitude](https://www.debian.org/doc/manuals/debian-handbook/sect.after-first-boot.en.html) is an interface to **APT** that can be used in semi-graphical mode on the console. It allows the user to browse the list of available packages according to various categories (installed or not-installed packages, by task, by section, etc.), and to view all of the information available on each of them (dependencies, conflicts, description, etc.). Each package can be marked “install” (to be installed, + key) or “remove” (to be removed, - key). All of these operations will be conducted simultaneously once you've confirmed them by pressing the g key (“g” for “go!”). If you have forgotten some programs, no worries; you will be able to run aptitude again once the initial installation has been completed.

### What is a package manager?
>A [package manager](https://www.debian.org/doc/manuals/aptitude/pr01s02.en.html) keeps track of what software is installed on your computer, and allows you to easily install new software, upgrade software to newer versions, or remove software that you previously installed. As the name suggests, package managers deal with packages: collections of files that are bundled together and can be installed and removed as a group.

- [ ] _A **SSH service will be running** on **port 4242** only. For security reasons, **it must not be
possible to connect using SSH as root**._

### What is SSH?
>Secure Shell ([SSH](https://en.wikipedia.org/wiki/Secure_Shell)) is a cryptographic network protocol for operating network services securely over an unsecured network. SSH provides a secure channel over an unsecured network by using a client–server architecture, connecting an SSH client application with an SSH server. 

>The SSH client drives the connection setup process and uses public key cryptography to verify the identity of the SSH server. After the setup phase the [SSH protocol](https://www.ssh.com/academy/ssh/protocol) uses strong symmetric encryption and hashing algorithms to ensure the privacy and integrity of the data that is exchanged between the client and server.

>The figure below presents a simplified setup flow of a secure shell connection.
>![image](https://user-images.githubusercontent.com/60623613/140618919-8617389f-2f37-4b9b-8ec3-64fc6c3447e9.png)

### How to know if a service is running?
>When you [boot](https://debian-handbook.info/browse/stable/unix-services.html#sect.system-boot) the computer, first, the BIOS takes control of the computer, detects the disks, loads the Master Boot Record, and executes the bootloader. The bootloader takes over, finds the kernel on the disk, loads and executes it. The kernel is then initialized, and starts to search for and mount the partition containing the root filesystem, and finally executes the first program — init.  Frequently, this “root partition” and this init are, in fact, located in a virtual filesystem that only exists in RAM (hence its name, “initramfs”, formerly called “initrd” for “initialization RAM disk”). This filesystem is loaded in memory by the bootloader, often from a file on a hard drive or from the network. It contains the bare minimum required by the kernel to load the “true” root filesystem: this may be driver modules for the hard drive, or other devices without which the system cannot boot, or, more frequently, initialization scripts and modules for assembling RAID arrays, opening encrypted partitions, activating LVM volumes, etc. Once the root partition is mounted, the initramfs hands over control to the real init, and the machine goes back to the standard boot process. The “real init” is currently provided by systemd.

>![image](https://user-images.githubusercontent.com/60623613/140621013-0d898c30-33e7-4207-b62c-4c87d1e0db80.png)

>A systemd “service file” describes a process managed by systemd. It contains roughly the same information as old-style init-scripts, but expressed in a declaratory (and much more concise) way. Systemd handles the bulk of the repetitive tasks (starting and stopping the process, checking its status, logging, dropping privileges, and so on), and the service file only needs to fill in the specifics of the process. For instance, here is the service file for SSH:

>![image](https://user-images.githubusercontent.com/60623613/140621048-f9759fd1-c0d7-4f54-9d39-94f0a9145a73.png)

>Since unit files are declarative rather than scripts or programs, they cannot be run directly, and they are only interpreted by systemd; several utilities therefore allow the administrator to interact with systemd and control the state of the system and of each component. The first such utility is systemctl. When run without any arguments, it lists all the unit files known to systemd (except those that have been disabled), as well as their status. `systemctl status` gives a better view of the services, as well as the related processes. If given the name of a service (as in `systemctl status ssh.service`), it returns even more details, as well as the last few log lines related to the service.

>![image](https://user-images.githubusercontent.com/60623613/140622396-4c5b14cc-5311-4427-8159-dc93e6cdd8c4.png)

### How to change the SSH port in the server?
>By default, the SSH server still runs in [port 22](https://www.ssh.com/academy/ssh/port). However, there are occasions when it is run in a different port. Testing use is one reason. Running multiple configurations on the same host is another. Rarely, it may also be run without root privileges, in which case it must be run in a non-privileged port (i.e., port number >= 1024). 

>The port number can be configured by changing the Port 22 directive in `/etc/ssh/sshd_config`. It can also be specified using the -p <port> option to sshd. The SSH client and sftp programs also support the -p <port> option. This for a simple reason, there is a large number of robots on the internet that scan ports 22 of all public IPs to find an SSH server to use, by [changing the default port of your SSH service](https://www.it-connect.fr/chapitres/openssh-configuration-du-serveur-ssh/), you will protect yourself from a large number of robots that automate scans and attacks.
  
>`apt install vim`
  
>`cd etc/ssh/`
  
>`vim sshd_config`
  
>`type 'i'` (Switch to Insert mode)
  
>Change port 22 to 4242
  
>`type ':wq'` (Save and quit)
  
>![image](https://user-images.githubusercontent.com/60623613/140950738-598cd9a4-b41a-4b9c-b68a-495bbb5278ea.png)
  
>`cd ../..`
  
>`systemctl restart sshd`

>`ss - tunlp`
  
>![image](https://user-images.githubusercontent.com/60623613/140971829-5317b061-85a4-4c85-bbf0-154536cec0d0.png)

### [Why forbid SSH connections from root by default](https://www.it-connect.fr/chapitres/openssh-configuration-du-serveur-ssh/)?
>The SSH service is a very popular service for attackers and hackers, it allows you to have direct control over the server as if you were in the same room as it. It turns out that the SSH service can be vulnerable to Brute Force attacks , which consist in testing, for a given user, a large number of passwords chosen more or less at random, betting on the fact that at the end of 'at a certain point, we will inevitably come across the right one.
  
>The problem being that if the brute force attack is successful on the " root " account, it becomes very dangerous for the attacked server because it ends up entirely in the hands of the hacker. For security reasons, it is therefore forbidden to connect to it as root . If an attacker decides to brute force an SSH access, he must first find the name of a valid user (other than root, which is the only user present on all Linux machines in the world) and if he succeeds then to find a valid login: password combination, it will end up with a limited number of rights on the server. Which is a lesser evil.
