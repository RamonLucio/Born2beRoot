# Born2beRoot

## Summary
_This document is a **System Administration** related exercise._

### [What is a System Administrator?](https://en.wikipedia.org/wiki/System_administrator)

>A system administrator is a person who is responsible for the upkeep, configuration, and reliable operation of computer systems; especially multi-user computers, such as servers. The system administrator seeks to ensure that the uptime, performance, resources, and security of the computers they manage meet the needs of the users, without exceeding a set budget when doing so.
  
More info: [Case Study](https://www.debian.org/doc/manuals/debian-handbook/case-study.en.html)

## Introduction
_This project aims to introduce you to the wonderful world of **virtualization**._

- [x] _You will **create your first machine in VirtualBox** (or UTM if you can’t use VirtualBox)
under specific instructions. Then, at the end of this project, you will be able to set up
your own operating system while implementing strict rules._

### [What is virtualization?](https://www.virtualbox.org/wiki/Virtualization)

>When we describe VirtualBox as a "virtualization"product, we refer to "full virtualization", that is, the particular kind of virtualization that allows an unmodified operating system with all of its installed software to run in a special environment, on top of your existing operating system. This environment, called a "virtual machine", is created by the virtualization software by intercepting access to certain hardware components and certain features. The physical computer is then usually called the "host", while the virtual machine is often called a "guest". Most of the guest code runs unmodified, directly on the host computer, and the guest operating system "thinks" it's running on real machine.

>There are several scenarios that make virtualization attractive:
>- **Operating system support.** With a virtualizer such as VirtualBox, one can run software written for one operating system on another (say, Windows software on Linux) without having to reboot.
>- **Infrastructure consolidation.** Since the full performance of today's computers is rarely needed full-time, instead of running many such physical computers, one can "pack" many virtual machines onto a few powerful hosts and balance the loads between them. This can save a lot of hardware costs: e.g. by consolidating many servers into a few.
>- **Testing and disaster recovery.** Especially with the use of snapshots, one can mess with a computing environment by running it as a virtual machine. If something goes wrong, one can easily switch back to a previous snapshot and avoid the need of frequent backups and restores.

### [How to create a virtual machine in VirtualBox?](https://www.virtualbox.org/manual/UserManual.html#gui-createvm)

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

>If you have [downloaded](https://www.debian.org/download) installation media from the Internet in the form of an ISO image file such as with a Linux distribution, you would normally burn this file to an empty CD or DVD and proceed as described above. With Oracle VM VirtualBox however, you can skip this step and mount the ISO file directly. Oracle VM VirtualBox will then present this file as a CD or DVD-ROM drive to the virtual machine, much like it does with virtual hard disk images.

>![image](https://user-images.githubusercontent.com/60623613/140512001-c7fc0f10-b80c-4378-a4ba-ac75f27fd57f.png)

## General guidelines

_The use of VirtualBox (or UTM if you can’t use VirtualBox) is mandatory._

- [x] _You only have to turn in a signature.txt file at the root of your repository. You
must paste in it the **signature** of your machine’s virtual disk. Go to Submission and
peer-evaluation for more information._

### [What is virtual disk signature?](https://www.lifewire.com/what-is-a-disk-signature-2625851) 

>A disk signature is a unique, identifying number for a hard disk drive or other data storage device stored as part of the master boot record. An operating system uses it to differentiate among storage devices on your computer.

### [What is a ".vdi" file?](https://docs.oracle.com/en/virtualization/virtualbox/6.0/user/vdidetails.html)

>Disk image file reside on the host system and are seen by the guest systems as hard disks of a certain geometry. When a guest OS reads from or writes to a hard disk, Oracle VM VirtualBox redirects the request to the image file.
>- **VDI.** Normally, Oracle VM VirtualBox uses its own container format for guest hard disks. This is called a Virtual Disk Image (VDI) file. This format is used when you create a new virtual machine with a new disk.

## Mandatory part

- [x] _You must choose as an operating system either the **latest stable version** of **Debian** (no
testing/unstable), or the latest stable version of **CentOS**. Debian is highly recommended
if you are new to system administration._

### [Why choose Debian?](https://www.debian.org/intro/why_debian)

>There are a lot of reasons to choose Debian as your operating system – as a user, as a developer, and even in enterprise environments. Most users appreciate the stability, and the smooth upgrade processes of both packages and the entire distribution. Debian is also widely used by software and hardware developers because it runs on numerous architectures and devices, offers a public bug tracker and other tools for developers. If you plan to use Debian in a professional environment, there are additional benefits like LTS versions and cloud images.

More info: [Why the Debian Distribution?](https://www.debian.org/doc/manuals/debian-handbook/sect.why-debian.en.html)

### [Why choose the latest stable version?](https://wiki.debian.org/DebianReleases)

>The latest release is Debian 11.1. It is also (currently) known as stable or by its codename "Bullseye".At any given time, there is one stable release of Debian, which has the support of the Debian security team. When a new stable version is released, the security team will usually cover the previous version for a year or so, while they also cover the new/current version. Only stable is recommended for production use. Stable is recommended for applications requiring production-level stability and security (servers, firewalls etc) and is also recommended for those who are new to Linux.

### [How to install Debian](https://www.debian.org/doc/manuals/debian-handbook/sect.installation-steps.en.html)?
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

### [What is partitioning?](https://www.debian.org/doc/manuals/debian-handbook/sect.installation-steps.en.html#sect.install-partman)
>Partitioning, an indispensable step in installation, consists in dividing the available space on the hard drives (each subdivision thereof being called a “partition”) according to the data to be stored on it and the use for which the computer is intended. This step also includes choosing the filesystems to be used. All of these decisions will have an influence on performance, data security, and the administration of the server

>The partitioning step is traditionally difficult for new users. It is necessary to define the various portions of the disks (or “partitions”) on which the Linux filesystems and virtual memory (swap) will be stored. This task is complicated if another operating system that you want to keep is already on the machine. Indeed, you will then have to make sure that you do not alter its partitions (or that you resize them without causing damage).

>Fortunately, the partitioning software has a “guided” mode which recommends partitions for the user to make — in most cases, you can simply validate the software's suggestions.

>![image](https://user-images.githubusercontent.com/60623613/140538831-062ca7b4-d87d-44da-9a9f-629438ad77d9.png)

>The next screen offers to choose the disk where Linux will be installed by selecting the corresponding entry (for example, “SCSI1 (0,0,0) (sda) - 21.5 GB ATA QEMU HARDDISK”). You then start guided partitioning.

>![image](https://user-images.githubusercontent.com/60623613/140539018-af120c14-c956-4f5f-aa95-1a0e8f3179cc.png)

>The first method is called “All files in one partition”. The entire Linux system tree is stored in a single filesystem, corresponding to the root / directory. This simple and robust partitioning fits perfectly for personal or single-user systems. In fact, two partitions will be created: the first will house the complete system, the second the virtual memory (swap).

>The second method, “Separate /home partition”, is similar, but splits the file hierarchy in two: one partition contains the Linux system (/), and the second contains “home directories” (meaning user data, in files and subdirectories available under /home/).

>![image](https://user-images.githubusercontent.com/60623613/140540673-fbed1f93-ea2b-4288-aa4d-8a163b71df30.png)

>![image](https://user-images.githubusercontent.com/60623613/140543145-0995cad5-9876-4362-b4d5-e58156ccb725.png)

[More info](https://youtu.be/pZ12_E5R3qc?t=42)

### [What is LVM?](https://www.debian.org/doc/manuals/debian-handbook/advanced-administration.en.html#sect.lvm)

>LVM, the Logical Volume Manager, is another approach to abstracting logical volumes from their physical supports, which focuses on increasing flexibility rather than increasing reliability. LVM allows changing a logical volume transparently as far as the applications are concerned; for instance, it is possible to add new disks, migrate the data to them, and remove the old disks, without unmounting the volume.

>LVM allows you to create “virtual” partitions that span over several disks. The benefits are twofold: the size of the partitions are no longer limited by individual disks but by their cumulative volume, and you can resize existing partitions at any time, possibly after adding an additional disk when needed.

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

### [What is a graphical interface?](https://en.wikipedia.org/wiki/Graphical_user_interface)
>The graphical user interface (GUI) allows users to interact with electronic devices through graphical icons and audio indicator such as primary notation, instead of text-based user interfaces, typed command labels or text navigation.

>![image](https://user-images.githubusercontent.com/60623613/140555452-ed195323-bcd3-433c-96e0-b112dfc01bf8.png)

>The bootloader is the first program started by the BIOS. This program loads the Linux kernel into memory and then executes it. It often offers a menu that allows the user to choose the kernel to load and/or the operating system to boot.

>![image](https://user-images.githubusercontent.com/60623613/140557462-c42375fe-1f87-451d-a09e-db5956b58080.png)

>![image](https://user-images.githubusercontent.com/60623613/140558111-1bb737a0-ad14-4b7a-b962-69397931155c.png)

>![image](https://user-images.githubusercontent.com/60623613/140559010-f62eada8-9b11-4121-bba8-cc2a9abdf5c0.png)

_ℹ️ **INFO:** Setting up CentOS is quite complex. Therefore, you don’t have to
set up KDump. However, SELinux must be running at startup and its
configuration has to be adapted for the project’s needs. **AppArmor
for Debian must be running at startup too**._

### [What is AppArmor?](https://debian-handbook.info/browse/stable/sect.apparmor.html)
>AppArmor is a Mandatory Access Control (MAC) system built on Linux's LSM (Linux Security Modules) interface. In practice, the kernel queries AppArmor before each system call to know whether the process is authorized to do the given operation. Through this mechanism, AppArmor confines programs to a limited set of resources.

>AppArmor applies a set of rules (known as “profile”) on each program. The profile applied by the kernel depends on the installation path of the program being executed. Contrary to SELinux, the rules applied do not depend on the user. All users face the same set of rules when they are executing the same program (but traditional user permissions still apply and might result in different behavior!).

>AppArmor profiles are stored in /etc/apparmor.d/ and they contain a list of access control rules on resources that each program can make use of. The profiles are compiled and loaded into the kernel by the apparmor_parser command. Each profile can be loaded either in enforcing or complaining mode. The former enforces the policy and reports violation attempts, while the latter does not enforce the policy but still logs the system calls that would have been denied.

>AppArmor support is built into the standard kernels provided by Debian. Enabling AppArmor is thus just a matter of installing some packages by executing `apt install apparmor apparmor-profiles apparmor-utils` with root privileges.

### [What is Mandatory Access Control?](https://en.wikipedia.org/wiki/Mandatory_access_control)
>In computer security, mandatory access control (MAC) refers to a type of access control by which the operating system or database constrains the ability of a subject or initiator to access or generally perform some sort of operation on an object or target. In the case of operating systems, a subject is usually a process or thread; objects are constructs such as files, directories, TCP/UDP ports, shared memory segments, IO devices, etc. Subjects and objects each have a set of security attributes. Whenever a subject attempts to access an object, an authorization rule enforced by the operating system kernel examines these security attributes and decides whether the access can take place. Any operation by any subject on any object is tested against the set of authorization rules (aka policy) to determine if the operation is allowed

### [How to check if AppArmor is running?](https://gitlab.com/apparmor/apparmor/-/wikis/AppArmorMonitoring#high-level-view)
>The `aa-status` tool gives a high level status of AppArmor and applications it has profiles for (as root).

![image](https://user-images.githubusercontent.com/60623613/140406297-12047d36-09da-4e33-a19f-98dd45e55b34.png)

_ℹ️ **INFO:** During the defense, you will be asked a few questions about the
operating system you chose. For instance, **you should know the
differences between aptitude and apt**, or **what SELinux or AppArmor
is**. In short, understand what you use!_

### [What is APT?](https://debian-handbook.info/browse/stable/apt.html#sect.apt-sources.list)
>APT is the abbreviation for Advanced Package Tool. What makes this program “advanced” is its approach to packages. It doesn't simply evaluate them individually, but it considers them as a whole and produces the best possible combination of packages depending on what is available and compatible according to dependencies.

>APT needs to be given a “list of package sources (repositories)”: the file /etc/apt/sources.list will list the different repositories that publish Debian packages. APT will then import the list of packages published by each of these sources.

### [What is apt?](https://www.debian.org/doc/manuals/debian-handbook/sect.apt-get.en.html)
>apt-get is the first front end — command-line based — which was developed within the APT project. apt is a second command-line based front end provided by APT which overcomes some design mistakes of apt-get. The default behavior of apt has been improved for interactive use and to actually do what most users expect. The APT developers reserve the right to change the public interface of this tool to further improve it. On the opposite, the public interface of apt-get is well defined and will not change in any backwards incompatible way. It is thus the tool that you want to use when you need to script package installation requests.

### [What is aptitude?](https://www.debian.org/doc/manuals/debian-handbook/sect.after-first-boot.en.html)
>[aptitude](https://www.debian.org/doc/manuals/aptitude/pr01s01.en.html) is a featureful package manager for Debian GNU/Linux systems, based on the renowned apt package management infrastructure. aptitude provides the functionality of dselect and apt-get, as well as many additional features not found in either program.

>aptitude is an interface to APT that can be used in semi-graphical mode on the console. It allows the user to browse the list of available packages according to various categories (installed or not-installed packages, by task, by section, etc.), and to view all of the information available on each of them (dependencies, conflicts, description, etc.). Each package can be marked “install” (to be installed, + key) or “remove” (to be removed, - key). All of these operations will be conducted simultaneously once you've confirmed them by pressing the g key (“g” for “go!”). If you have forgotten some programs, no worries; you will be able to run aptitude again once the initial installation has been completed.

### [What is a package manager?](https://www.debian.org/doc/manuals/aptitude/pr01s02.en.html)
>A package manager keeps track of what software is installed on your computer, and allows you to easily install new software, upgrade software to newer versions, or remove software that you previously installed. As the name suggests, package managers deal with packages: collections of files that are bundled together and can be installed and removed as a group.

- [ ] _A **SSH service will be running** on **port 4242** only. For security reasons, **it must not be
possible to connect using SSH as root**._

ℹ️ **INFO**: _The use of SSH will be tested during the defense by setting up a new account. You must therefore understand how it works._

### [What is SSH?](https://en.wikipedia.org/wiki/Secure_Shell)
>Secure Shell SSH is a cryptographic network protocol for operating network services securely over an unsecured network. SSH provides a secure channel over an unsecured network by using a client–server architecture, connecting an SSH client application with an SSH server. 

>The SSH client drives the connection setup process and uses public key cryptography to verify the identity of the SSH server. After the setup phase the [SSH protocol](https://www.ssh.com/academy/ssh/protocol) uses strong symmetric encryption and hashing algorithms to ensure the privacy and integrity of the data that is exchanged between the client and server.

>The figure below presents a simplified setup flow of a secure shell connection.

>![image](https://user-images.githubusercontent.com/60623613/140618919-8617389f-2f37-4b9b-8ec3-64fc6c3447e9.png)

### [How to know if a service is running?](https://debian-handbook.info/browse/stable/unix-services.html#sect.system-boot)

>When you boot the computer, first, the BIOS takes control of the computer, detects the disks, loads the Master Boot Record, and executes the bootloader. The bootloader takes over, finds the kernel on the disk, loads and executes it. The kernel is then initialized, and starts to search for and mount the partition containing the root filesystem, and finally executes the first program — init.  Frequently, this “root partition” and this init are, in fact, located in a virtual filesystem that only exists in RAM (hence its name, “initramfs”, formerly called “initrd” for “initialization RAM disk”). This filesystem is loaded in memory by the bootloader, often from a file on a hard drive or from the network. It contains the bare minimum required by the kernel to load the “true” root filesystem: this may be driver modules for the hard drive, or other devices without which the system cannot boot, or, more frequently, initialization scripts and modules for assembling RAID arrays, opening encrypted partitions, activating LVM volumes, etc. Once the root partition is mounted, the initramfs hands over control to the real init, and the machine goes back to the standard boot process. The “real init” is currently provided by systemd.

>![image](https://user-images.githubusercontent.com/60623613/140621013-0d898c30-33e7-4207-b62c-4c87d1e0db80.png)

>A systemd “service file” describes a process managed by systemd. It contains roughly the same information as old-style init-scripts, but expressed in a declaratory (and much more concise) way. Systemd handles the bulk of the repetitive tasks (starting and stopping the process, checking its status, logging, dropping privileges, and so on), and the service file only needs to fill in the specifics of the process. For instance, here is the service file for SSH:

>![image](https://user-images.githubusercontent.com/60623613/140621048-f9759fd1-c0d7-4f54-9d39-94f0a9145a73.png)

>Since unit files are declarative rather than scripts or programs, they cannot be run directly, and they are only interpreted by systemd; several utilities therefore allow the administrator to interact with systemd and control the state of the system and of each component. The first such utility is systemctl. When run without any arguments, it lists all the unit files known to systemd (except those that have been disabled), as well as their status. `systemctl status` gives a better view of the services, as well as the related processes. If given the name of a service (as in `systemctl status ssh.service`), it returns even more details, as well as the last few log lines related to the service.

>![image](https://user-images.githubusercontent.com/60623613/140622396-4c5b14cc-5311-4427-8159-dc93e6cdd8c4.png)

### [How to change the SSH port in the server?](https://www.ssh.com/academy/ssh/port)

>By default, the SSH server still runs in port 22. However, there are occasions when it is run in a different port. Testing use is one reason. Running multiple configurations on the same host is another. Rarely, it may also be run without root privileges, in which case it must be run in a non-privileged port (i.e., port number >= 1024).

>The port number can be configured by changing the Port 22 directive in `/etc/ssh/sshd_config`. It can also be specified using the -p <port> option to sshd. The SSH client and sftp programs also support the -p <port> option. This for a simple reason, there is a large number of robots on the internet that scan ports 22 of all public IPs to find an SSH server to use, by changing the default port of your SSH service, [you will protect yourself from a large number of robots that automate scans and attacks](https://www.it-connect.fr/chapitres/openssh-configuration-du-serveur-ssh/).
  
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
  
>The problem being that if the brute force attack is successful on the "root" account, it becomes very dangerous for the attacked server because it ends up entirely in the hands of the hacker. For security reasons, it is therefore forbidden to connect to it as root . If an attacker decides to brute force an SSH access, he must first find the name of a valid user (other than root, which is the only user present on all Linux machines in the world) and if he succeeds then to find a valid login: password combination, it will end up with a limited number of rights on the server. Which is a lesser evil.
  
### [How to specify whether root can log in using ssh](https://man7.org/linux/man-pages/man5/sshd_config.5.html)?

> `vim etc/sshd/sshd_config`
  
>Search for PermitRootLogin. It specifies whether root can log in using ssh.  The argument must be yes, prohibit-password, forced-commands-only, or no.  The default is prohibit-password. If this option is set to no, root is not allowed to log in.

>![image](https://user-images.githubusercontent.com/60623613/140977183-dffa1d79-8d72-4502-982f-6b370b0647c2.png)

> `systemctl restart sshd`
  
- [x] _You have to configure your operating system with the **UFW firewall** and thus leave only port 4242 open._

### [What is firewall?](https://en.wikipedia.org/wiki/Firewall_(computing))
>A firewall is a network security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. A firewall typically establishes a barrier between a trusted network and an untrusted network, such as the Internet.
  
### [What is UFW?](https://wiki.debian.org/Uncomplicated%20Firewall%20%28ufw%29)
>The Uncomplicated Firewall is a frontend for iptables and is particularly well-suited for host-based firewalls. UFW provides a framework for managing netfilter, as well as a command-line interface for manipulating the firewall.
  
### [How to configure Debian with UFW](https://wiki.debian.org/Uncomplicated%20Firewall%20%28ufw%29)?
>Uncomplicated Firewall can be easily installed by typing this command into the terminal as a super user:

`apt install ufw`
  
>![image](https://user-images.githubusercontent.com/60623613/140982199-56b3f6c4-958e-44de-a749-99b29977a49c.png)

>However, simply installing the firewall will not turn it on automatically, nor it will have any rule set by default.
  
>⚠️ Warning: If you are configuring over SSH, you may wish to allow SSH before enabling the firewall. If your connection gets interrupted before allowing SSH you may be locked out of your system.

> Firstly, the firewall must be enabled by typing:

> `ufw enable`
  
> ![image](https://user-images.githubusercontent.com/60623613/140982597-99f37ad8-0284-4cab-885b-dc78a1f56993.png)

> Secondly, defaults must be set up. For normal users the following defaults will do just fine.

> `ufw default deny incoming`
  
> `ufw default allow outgoing`
  
>![image](https://user-images.githubusercontent.com/60623613/140983592-28753217-5d49-4c9f-8aad-1c704e624088.png)

> Next, it is recommended to verify that the firewall is enabled by typing:

> `ufw status verbose` 
  
>![image](https://user-images.githubusercontent.com/60623613/140983751-a6ba5e04-9863-490e-b36f-facaa59c983b.png)

> Allowing rules is quite simple from the command line, and it is sometimes necessary. For example, by default ufw denies all of the incoming connections, which will make it a problem if you are using SSH. Therefore, you must create a rule which allows SSH connections, by typing:
  
> `ufw allow ssh`
  
>![image](https://user-images.githubusercontent.com/60623613/140983873-e64c2765-458b-4b92-aaab-58c56ce4e9c9.png)

> Port ranges may also be specified, a simple example for tcp would be:

> `ufw allow 4242/tcp`
  
>![image](https://user-images.githubusercontent.com/60623613/140985819-9c52531b-e19a-4c36-9201-d8650fd6eecc.png)

> You may also delete rules by number. To show a numbered list of rules:

> `ufw status numbered`

> This will output a numbered list of rules, and the number may be used to delete a particular rule:

> `ufw delete 2`

> ![image](https://user-images.githubusercontent.com/60623613/140986151-82a8daeb-36e8-4a94-9d44-464c2828211f.png)

ℹ️ **INFO**: _Your firewall must be active when you launch your virtual machine.
For CentOS, you have to use UFW instead of the default firewall. To
install it, you will probably need DNF._

- [x] _The hostname of your virtual machine must be your login ending with 42 (e.g.,
wil42). **You will have to modify this hostname during your evaluation**._
  
### [How to modify the machine's hostname](https://wiki.debian.org/Hostname)?
  
> Versions of Debian with systemd installed can use `hostnamectl set-hostname mymachine`. This tool depends on dbus so be sure to install that first.
  
>![image](https://user-images.githubusercontent.com/60623613/141003352-304b0997-1159-4b90-9ab3-827f963c67b2.png)
  
>![image](https://user-images.githubusercontent.com/60623613/141003726-e9e8957a-c6ed-49de-b42e-1c299cf6eddb.png)

> [The purpose](https://debian-handbook.info/browse/stable/sect.hostname-name-service.html) of assigning names to IP numbers is to make them easier for people to remember.
In reality, an IP address identifies a network interface associated with a device such as a network
card. Since each machine can have several network cards, and several interfaces on each card,
one single computer can have several names in the domain name system.

> Each machine is, however, identified by a main (or “canonical”) name, stored in the /etc/
hostname file and communicated to the Linux kernel by initialization scripts through the
hostname command. The current value is available in a virtual filesystem, and you can get it
with the cat /proc/sys/kernel/hostname command.
  
- [x] _You have to implement a strong **password policy**._
  
### [Password Policy: The Good, The Bad, and The Ugly](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=Password+Policy%3A+The+Good%2C+The+Bad%2C+and+The+Ugly&btnG=)

#### Introduction
>In today’s world of increasing dependence on computers and computer systems, it is
imperative that we be able to rely on secure and confidential connections to the computers.
Traditionally, this has been by authentication with usernames and passwords. “A password is
information associated with an entity that confirms the entity’s identity.” [Bishop] The
password is a string of characters that can either be automatically generated by the system or
selected by the entity or user. Passwords can range from a single character to passphrases,
which can be hundreds of characters in length and be comprised of series of words and
phrases. The goal of a password is to authenticate a user. It is a piece of information that the
user knows. If someone can guess a user’s password, she can impersonate the user.

#### The Bad
>In early versions of UNIX, passwords were stored in a file /etc/passwd. This file was
available to anyone who had an account on the computer. The passwords were stored in
encrypted form as 11 characters with a 2-character salt. UNIX uses one-way hash algorithm
(Crypt) to disguise the passwords. It was very easy to copy to a file and use a cracker
program on a fast computer to discover the passwords. Some versions of UNIX now use the
MD5 hash algorithm. Most versions today keep the passwords in a shadow file that is only
accessible to the root account.
  
> There are many schemes for password cracking. Among the different types of password
cracking attacks are:
  > - Dictionary Attack - uses a file that contains most of the words found in a dictionary
  > - Brute Force Attack - tries every possible combination of letters, numbers and special
characters
  > - Hybrid Attack - concatenates extra characters to dictionary words and trying different
combinations

#### The Good
> It is imperative that organizations have and enforce a password policy. Policies explain what
the rules are and what is expected of the computer users. Having a policy also provides a
framework for enforcing password rules in a consistent fashion.

> Features of a strong password include: 
  > - Minimum length of six-ten characters. The longer the password, the longer it will take
  to crack.
  > - Must contain at least three of the following: lowercase alpha, uppercase alpha, digit,
  and special character. The more variety in the password, the longer it will take to
  crack.
  > - Alpha, number and special characters must be mixed up. Don’t just add digits to the
  end of the password.
  > - Do not use "dictionary" words. This includes dictionaries of common proper names
  and foreign language dictionaries. Also avoid “common words” with digits appended.
  
>Other password policy features include:
  > - Do not reuse the previous five passwords. Some organizations suggest never reusing a
password.
  > - Minimum password age of ten days. To keep users from going back to a previous
  password.
  > - Maximum password age of 45-60 days. This should be determined by how long it
  would take a hacker to crack the passwords
  > - Lock password after three-five failed logon attempts. This eliminates hackers from
  running a program to try different password combinations.

#### Conclusions
> Passwords are an important component of securing our computer systems, but they are not
the entire solution. Their purpose has been and should continue to be a mechanism for
determining what a user knows. We need to include more than that. In addition to what we
know, we should be including one or more of the following: “what you have”, “who you
are”, and “what you produce.” What you have may include physical devices like smart cards
and tokens. Who you are include physical features like fingerprints, hand topography and
geometry, retinal and iris scans, and facial scans. What you produce may include voice and
signature patterns.
  
> One popular variation of this is to use one-time passwords. With a one-time password, the
user is given a device that generates a new password at a fixed time interval. The device is
synchronized to a server that generates the same password at the same time. When the user
wants to log into the system, the user looks at the device and types in the password, which is
authenticated by comparing with the password generated by the server. Each time, the user is
assigned a unique password. If a password is compromised, it will only work the one time.
The drawback to this system is that the user must have the device with them whenever the
user wants to connect to the computer.
  
### [How to set up a strong password policy on Debian?](https://www.server-world.info/en/note?os=Debian_11&p=pam&f=1)
  > Install password quality checking library.
  
  >![image](https://user-images.githubusercontent.com/60623613/141208607-e0031a96-37ec-40a1-889c-4ddf85d893ac.png)
  
  _To set up a strong password policy, you have to comply with the following requirements:_

  - [x] _Your password has to expire every 30 days._
    
    > Set number of days for password Expiration. Users must change their password within the days. This setting impacts only when creating a user, not impacts to exisiting users. If set to exisiting users, run the command [chage -M (days) (user)].
    
    > `vim /etc/login.defs`
  
    >![image](https://user-images.githubusercontent.com/60623613/141210480-17c81ea5-117c-4577-b243-cf78ee8245e2.png)
  
    >![image](https://user-images.githubusercontent.com/60623613/141211094-374023a2-2e94-4a4d-ae9e-a521845e950b.png)

    
    >![image](https://user-images.githubusercontent.com/60623613/141209040-c9228ba5-eea4-4a1c-a38c-df445380e21a.png)

    >![image](https://user-images.githubusercontent.com/60623613/141210102-4f733765-1e8d-48bf-af75-c55893b3a10a.png)

  - [x] _The minimum number of days allowed before the modification of a password will
be set to 2._
  
    > Set minimum number of days available of password. Users must use their password at least this days after changing it. This setting impacts only when creating a user, not impacts to exisiting users. If set to exisiting users, run the command [chage -m (days) (user)].

    > `vim /etc/login.defs`
  
    >![image](https://user-images.githubusercontent.com/60623613/141210301-962d6dce-6a80-4735-9dc9-30d31ee4dcd6.png)

    >![image](https://user-images.githubusercontent.com/60623613/141210381-aab429af-895d-4826-86c1-336036a74388.png)

  - [x] _The user has to receive a warning message 7 days before their password expires._
    
    > Set number of days for warnings before expiration.
      This setting impacts only when creating a user, not impacts to exisiting users.
      If set to exisiting users, run the command [chage -W (days) (user)].
  
    > `vim /etc/login.defs`
  
    >![image](https://user-images.githubusercontent.com/60623613/141210772-75bf4ffb-87a6-4f3e-8b5e-9a1abd78a7a2.png)

    >![image](https://user-images.githubusercontent.com/60623613/141210833-7d4d6adf-0e86-4ea4-ac12-998c74af40c9.png)

  - [x] _Your password must be at least 10 characters long. It must contain an uppercase letter and a number. Also, it must not contain more than 3 consecutive identical characters._
  
    >	Set minimum password length. Users can not set their password length less than this parameter.
  
    > `vim /etc/security/pwquality.conf`
  
    >![image](https://user-images.githubusercontent.com/60623613/141211527-82833888-f1db-4af3-8e2f-aa98a63c78c5.png)

    >![image](https://user-images.githubusercontent.com/60623613/141211611-18ebc508-b098-49a9-b8e1-ddb2a4b99e1a.png)

    >	Require at least one uppercase character in the new password.
  
    >![image](https://user-images.githubusercontent.com/60623613/141305935-28eda24c-4621-4a2c-9148-ddfe10db8403.png)

    >	Require at least one digit in the new password.
  
    >![image](https://user-images.githubusercontent.com/60623613/141212018-43fb81a9-263b-46e1-8fe9-7ae65f7b1b5f.png)

    >	Set maximum number of allowed consecutive same characters in the new password.
  
    >![image](https://user-images.githubusercontent.com/60623613/141212139-b069388a-8d6b-4979-8ce1-46d36a2fe8a5.png)
  
  - [x] _The password must not include the name of the user._
  
    > Check whether the words longer than 3 characters from the GECOS field of the user's passwd entry are contained in the new password.
  
    > The [gecos field](https://en.wikipedia.org/wiki/Gecos_field) is a field of each record in the /etc/passwd file on Unix, and similar operating systems. On UNIX, it is the 5th of 7 fields in a record. It is typically used to record general information about the account or its user(s) such as their real name and phone number.
  
    >![image](https://user-images.githubusercontent.com/60623613/141298683-8cb025a5-8ea4-4284-ac5c-0800560e038a.png)
  
    >![image](https://user-images.githubusercontent.com/60623613/141306286-0fba9b9b-770c-4222-bad7-1cd802fc8755.png)

  - [x] _The following rule does not apply to the root password: The password must have
at least 7 characters that are not part of the former password._
  
    > Set number of characters in the new password that must not be present in the old password.
  
    >![image](https://user-images.githubusercontent.com/60623613/141301300-e5dd496b-9b07-42d4-8880-c37eed43a519.png)

  - [x] _Of course, your root password has to comply with this policy._
  
    >![image](https://user-images.githubusercontent.com/60623613/141306669-2d77c501-551e-4a15-b4e5-a82c0f33a581.png)
    
    >![image](https://user-images.githubusercontent.com/60623613/144090757-0a0d3e68-7a47-4082-9652-8f0ceb917e3c.png)

⚠️ **WARNING**: _After setting up your configuration files, you will have to **change all the passwords** of the accounts present on the virtual machine, including the root account._
  
### [How to change passwords?](https://tldp.org/LDP/lame/LAME/linux-admin-made-easy/changing-user-passwords.html)
  
> To change a password on behalf of a user, first sign on or "su" to the "root" account. Then type, `passwd user` (where user is the username for the password you are changing). The system will prompt you to enter a password. Passwords do not echo to the screen when you enter them.

> You can also change your own password, by typing `passwd` (without specifying a username). You will be prompted to enter your old password for verification, and then a new password.
  
>![image](https://user-images.githubusercontent.com/60623613/141308751-a3565c72-e839-4962-8bd5-a1a055e12524.png)

>![image](https://user-images.githubusercontent.com/60623613/141309128-20573df3-6ce1-4e2e-a097-09bade3ddb99.png)

>![image](https://user-images.githubusercontent.com/60623613/141328959-e83a36de-af03-4334-a82b-4e6733aabe92.png)

>![image](https://user-images.githubusercontent.com/60623613/141330071-8fff764b-b45e-4a63-8fe3-766dae88f6a0.png)

- [x] _You have to **install and configure sudo** following strict rules_
  
### How to install sudo?
  
`apt install sudo`
  
![image](https://user-images.githubusercontent.com/60623613/141348477-9a6c4fc6-435a-4983-aa2d-11fe795149b4.png)

### [What is sudo?](https://wiki.debian.org/sudo/) 
  
>Sudo (sometimes considered as short for Super-user do) is a program designed to let system administrators allow some users to execute some commands as root (or another user). The basic philosophy is to give as few privileges as possible but still allow people to get their work done. Sudo is also an effective way to log who ran which command and when.
  
### Why use sudo?
  
>Using sudo is better (safer) than opening a session as root for a number of reasons, including:
  > - Nobody needs to know the root password (sudo prompts for the current user's password). Extra privileges can be granted to individual users temporarily, and then taken away without the need for a password change.
  > - It's easy to run only the commands that require special privileges via sudo; the rest of the time, you work as an unprivileged user, which reduces the damage that mistakes can cause.
  > - Auditing/logging: when a sudo command is executed, the original username and the command are logged.

>For the reasons above, switching to root using sudo -i (or sudo su) is usually deprecated because it cancels the above features. 

>Debian's default configuration allows users in the sudo group to run any command via sudo.

#### Verifying sudo membership

>Once logged in as a user, you can verify whether or not the user belongs to group=sudo using either the id or groups commands. E.g., a user with id=foo should see output from
  
>![image](https://user-images.githubusercontent.com/60623613/141338540-9737ecd1-6516-4f76-8b18-3c465cda7ee5.png)

#### Add existing user from commandline

>To add an existing user with id=username to group=sudo:
  
  `sudo adduser username sudo`

>Alternatively, you can first get root (e.g., sudo su -) and then run the same commands without prefix=sudo:
  
  >![image](https://user-images.githubusercontent.com/60623613/141374362-725be6d5-ab2e-4ba1-9a64-0dabd1f227dc.png)

>After being added to a new group **the user must log out and then log back in again for the new group to take effect**. Groups are only assigned to users at login time. A most common source of confusion is that people add themselves to a new group but then do not log out and back in again and then have problems because the group is not assigned; be sure to verify group membership.
    
  >![image](https://user-images.githubusercontent.com/60623613/141374485-ac5cb64c-35ba-4dc1-9425-b2c64622ab28.png)

- [x] _A user with your login as username has to belong to the user42 and sudo groups._
  
### [How to create a group?](https://linux.die.net/man/8/groupadd)
  
>The `groupadd` command creates a new group account using the values specified on the command line plus the default values from the system. The new group will be entered into the system files as needed.
  
![image](https://user-images.githubusercontent.com/60623613/143143721-4a96196c-b07d-4599-ba8f-6b5c342f9e77.png)
  
ℹ️ **INFO**: _During the defense, you will have to create a new user and assign it to a group._
  
### [How to create a new user?](https://linux.die.net/man/8/useradd)
  
>`useradd` - create a new user or update default new user information

![image](https://user-images.githubusercontent.com/60623613/143146327-b4c57854-ccfc-43c9-8705-0e58b730fc82.png)
    
### [How to configure sudo group?](https://manpages.debian.org/bullseye/sudo-ldap/sudoers.5.en.html)
  
>The sudoers policy plugin determines a user's sudo privileges. It is the default sudo policy plugin. The policy is driven by the /etc/sudoers file or, optionally in LDAP.
  
>![image](https://user-images.githubusercontent.com/60623613/141489375-505810eb-4f68-4b32-9c1f-e5cf4cdfac7f.png)
  
>![image](https://user-images.githubusercontent.com/60623613/141491250-19d9abbe-ea60-46c2-b58b-caa18968a311.png)

#### [What is visudo?](https://linux.die.net/man/8/visudo)
  
>visudo edits the sudoers file in a safe fashion. visudo locks the sudoers file against multiple simultaneous edits, provides basic sanity checks, and checks for parse errors. If the sudoers file is currently being edited you will receive a message to try again later.
  
_To set up a strong **configuration for your sudo group**, you have to comply with the following requirements:_
      
  - [x] _Authentication using sudo has to be limited to 3 attempts in the event of an incorrect password._
  
    >[passwd_tries](https://manpages.debian.org/bullseye/sudo-ldap/sudoers.5.en.html#SUDOERS_OPTIONS)
      > - The number of tries a user gets to enter his/her password before sudo logs the failure and exits. The default is 3.
  
  - [x] _A custom message of your choice has to be displayed if an error due to a wrong password occurs when using sudo._
  
    >[badpass_message](https://manpages.debian.org/bullseye/sudo-ldap/sudoers.5.en.html#SUDOERS_OPTIONS)
      > - Message that is displayed if a user enters an incorrect password. The default is Sorry, try again. unless insults are enabled.
  
      >![image](https://user-images.githubusercontent.com/60623613/141497000-425bd100-8eea-4be2-9362-a109e90d0092.png)

      >![image](https://user-images.githubusercontent.com/60623613/141496802-81b43198-7905-4da6-bee1-ce133cc918c8.png)

  - [x] _Each action using sudo has to be archived, both inputs and outputs. The log file has to be saved in the /var/log/sudo/ folder._
  
    >When I/O logging is enabled, sudo will run the command in a pseudo-terminal and log all user input and/or output, depending on which options are enabled. I/O can be logged either to the local machine or to a remote log server. For local logs, I/O is logged to the directory specified by the iolog_dir option (/var/log/sudo-io by default) using a unique session ID that is included in the sudo log line, prefixed with “TSID=”.
  
    >![image](https://user-images.githubusercontent.com/60623613/143683138-5ee3bc66-1175-43d2-bdc5-77de5b46e3a8.png)
  
  - [x] _The TTY mode has to be enabled for security reasons._
  
    >[requiretty](https://manpages.debian.org/bullseye/sudo-ldap/sudoers.5.en.html#SUDOERS_OPTIONS)
      > - If set, sudo will only run when the user is logged in to a real tty. When this flag is set, sudo can only be run from a login session and not via other means such as cron(8) or cgi-bin scripts. This flag is off by default.
      
  More info: [Why would I want to require a tty for sudo? What's the security benefit of requiring it?](https://stackoverflow.com/questions/67985925/why-would-i-want-to-require-a-tty-for-sudo-whats-the-security-benefit-of-requi)
  
  >![image](https://user-images.githubusercontent.com/60623613/141503188-9bc1ea9c-d5f7-4ee8-b5e2-c39271113f4a.png)
  
  - [x] _For security reasons too, the paths that can be used by sudo must be restricted._
  Example: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin

    >Previous versions did not include that line. If you had a locally modified /etc/sudoers (most would) and then upgraded and kept your locally modified version then this required line is now missing. It no longer overrides your PATH when using sudo. This most likely results in PATH not being set properly and not including the system directories. The fix is to merge your local changes into the new package /etc/sudoers file. Or to put your local changes in the new /etc/sudoers.d/ location as a uniquely named file such as /etc/sudoers.d/local-sudoers.
  
    >![image](https://user-images.githubusercontent.com/60623613/141481834-43c17b44-7d24-4e4e-8897-9fef32dfe449.png)

<hr>
  
- [x] _Finally, **you have to create a simple script called monitoring.sh. It must be developed in bash**._
  
### [What is a script?](https://tldp.org/LDP/Bash-Beginners-Guide/html/sect_02_01.html)
  
>A shell script is a sequence of commands for which you have a repeated use. This sequence is typically executed by entering the name of the script on the command line. Alternatively, you can use scripts to automate tasks using the **cron** facility.
  
### [How to create a script in bash?](https://www.shellscript.sh/)
  
>To create a shell script, open a new empty file in your editor. You might want to chose a more advanced editor like **vim** or emacs, however, because these can be configured to recognize shell and Bash syntax and can be a great help in preventing those errors that beginners frequently make, such as forgetting brackets and semi-colons.
  
### Which shell will run the script?
  
>When running a script in a subshell, you should define which shell should run the script. The shell type in which you wrote the script might not be the default on your system, so commands you entered might result in errors when executed by the wrong shell.
  
>The first line of the script determines the shell to start. The first two characters of the first line should be #!, then follows the path to the shell that should interpret the commands that follow. Blank lines are also considered to be lines, so don't start your script with an empty line.
  
>monitoring.sh will start with the line
  
>`#!/bin/bash`
  
>As noted before, this implies that the Bash executable can be found in /bin.
  
>Note that to make a file executable, you must set the eXecutable bit, and for a shell script, the Readable bit must also be set:
  
![image](https://user-images.githubusercontent.com/60623613/143475455-2083e297-ba03-4af8-a293-97268272e7bb.png)
  
- [x] _**At server startup, the script will display some information (listed below) on all terminals every 10 minutes (take a look at wall)**. The banner is optional. No error must be visible._
  
### [What is wall?](https://man7.org/linux/man-pages/man1/wall.1.html)
  
>wall displays a message, or the contents of a file, or otherwise
its standard input, on the terminals of all currently logged in
users.
  
More info: [wall (Unix)](https://en.wikipedia.org/wiki/Wall_(Unix))
  
![image](https://user-images.githubusercontent.com/60623613/143479972-ef987ba3-bce4-4f9e-b66c-e64f3951bb8a.png)
  
_Your script must always be able to display the following information:_

- [x] _The **architecture** of your operating system and its **kernel version**._

  [`uname --all`](https://linux.die.net/man/1/uname)

  ![image](https://user-images.githubusercontent.com/60623613/142035328-559a05c6-b6d3-46b9-89cf-9d6f5e193507.png)

  More info: [Uname Command in Linux](https://linuxize.com/post/uname-command-in-linux/)

- [x] _The number of physical processors._

  >[To find out how many processors you have](https://www.networkworld.com/article/2715970/counting-processors-on-your-linux-box.html), for example, look through /proc/cpuinfo for lines containing the string "physical id". You can grab this with grep and then pass that information through a couple handy filters like this to get a count:

  `grep "physical id" /proc/cpuinfo | sort | uniq | wc -l`

  ![image](https://user-images.githubusercontent.com/60623613/142243768-d0bb68bd-459e-451c-8906-68083572dca5.png)

  >This tells you how many physical processors are on your system, but doesn't answer questions about how many cores or whether your system is using hyper-threading. Note that any particular physical id may appear in the file more than once, so you want to sort lines that contain that string (e.g., "physical id : 0") to be sure that each gets counted only once.

- [x] _The number of virtual processors._

  >If your processors are multi-core, you need to know how many virtual processors you have. You can count those by looking for lines that start with "processor".

  `grep "^processor" /proc/cpuinfo | wc -l`

  ![image](https://user-images.githubusercontent.com/60623613/142246260-00f204eb-2640-43ae-b90c-ab6408c05c2b.png)

  >You might have more virtual processors than physical processors because your processors are mutli-core, because your processors are hyper-threaded, or both. The way to tell how may cores you have is to look for "cpu cores" in your /proc/cpuinfo file. This line will show up for each virtual processor. If the number of cores shown is less than the number of virtual processors, your system is multi-threading.

- [x] _The current available RAM on your server and its utilization rate as a percentage._

  >[free](https://man7.org/linux/man-pages/man1/free.1.html) displays the total amount of free and used physical and swap memory in the system, as well as the buffers and caches used by the kernel. The information is gathered by parsing /proc/meminfo.

  >--mega Display the amount of memory in megabytes. Implies --si.

  ![image](https://user-images.githubusercontent.com/60623613/142268158-80579178-3eb0-41ae-99d4-6f8ca4ab858d.png)

  `free --mega | grep Mem | awk '{printf("Memory Usage: %i/%iMB (%.2f%%)\n", $3, $2, $3/$2*100}'`

  ![image](https://user-images.githubusercontent.com/60623613/142268803-6aa16303-fe5e-419b-b0c1-96ad95cdf00f.png)

- [x] _The current available memory on your server and its utilization rate as a percentage._

  >[df](https://linux.die.net/man/1/df) displays the amount of disk space available on the file system containing each file name argument. If no file name is given, the space available on all currently mounted file systems is shown.

  >--total
    > - produce a grand total

  >-h, --human-readable
    > - print sizes in human readable format (e.g., 1K 234M 2G)

  `df --total --human-readable | grep "total" | awk '{printf("Disk Usage: %s\%s (%.1f%%)\n", $3, $2, $3/2*100)}'`

  ![image](https://user-images.githubusercontent.com/60623613/142290244-38e413e7-dc73-45a6-9cf3-e7fb19832e6f.png)

- [x] _The current utilization rate of your processors as a percentage._

  >The [top](https://man7.org/linux/man-pages/man1/top.1.html) program provides a dynamic real-time view of a running system.  It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel.
  
  >-b : Batch-mode operation
  >- Starts top in Batch mode, which could be useful for sending
  output from top to other programs or to a file.  In this
  mode, top will not accept input and runs until the
  iterations limit you've set with the `-n' command-line
  option or until killed.

  >-n : Number-of-iterations limit as: -n number
  >- Specifies the maximum number of iterations, or frames, top should produce before ending.

  `top -bn1 | grep "%Cpu" | awk '{printf("CPU load: %.1f%%\n", (100.0-$8)%100)}'`
  
  ![image](https://user-images.githubusercontent.com/60623613/145411951-9395799f-9e42-4540-961f-e1f9f197fd0f.png)

- [x] _The date and time of the last reboot._

  `who --boot | awk '{printf("Last boot: %s %s", $3, $4)}'`

  ![image](https://user-images.githubusercontent.com/60623613/142692434-e5a72686-48d8-4ae3-883a-578e0a7d273a.png)

- [x] _Whether LVM is active or not._

  `if [ $(lsblk | grep "lvm" | wc -l) -eq 0 ]; then echo "no"; else echo "yes"; fi`

  ![image](https://user-images.githubusercontent.com/60623613/142705580-3dba1b72-017c-4431-88a6-941439954807.png)

- [x] _The number of active connections._

  >[ss](https://man7.org/linux/man-pages/man8/ss.8.html) is used to dump socket statistics. It allows showing information similar to netstat.  It can display more TCP and state information than other tools.

  > -s, --summary

    > - Print summary statistics. This option does not parse socket lists obtaining summary from various sources. It is useful when amount of sockets is so huge that parsing /proc/net/tcp is painful.

  `ss -s | grep "TCP:" | tr ',' ' ' | awk '{printf("Connections TCP : %s ESTABLISHED\n", $4)}'`

  ![image](https://user-images.githubusercontent.com/60623613/142728665-d72dfb48-8256-49bb-8a19-e7fcd9e5e773.png)

- [x] _The number of users using the server._

  > `who --count`

    >all login names and number of users logged on

  `who --count | grep "users" | tr '=' ' ' | awk '{printf("User log: %s\n", $3)}'`

  ![image](https://user-images.githubusercontent.com/60623613/142728930-c18503c3-3037-4efa-a387-84758cc32f67.png)

- [x] _The IPv4 address of your server and its MAC (Media Access Control) address._

  ### [Virtual Networking](https://www.virtualbox.org/manual/ch06.html)
  
  >- Bridged networking. This is for more advanced networking needs, such as network simulations and running servers in a guest. When enabled, Oracle VM VirtualBox connects to one of your installed network cards and exchanges network packets directly, circumventing your host operating system's network stack.
  
  ### [How to find the IPv4 address of your server?](https://linux.die.net/man/1/hostname)
  
  >`hostname -I`
  
  >Hostname is the program that is used to either set or display the current host, domain or node name of the system.  These names are used by many of the networking programs to identify the machine.
  
  >-I, --all-ip-addresses
  
  >Display all network addresses of the host. This option enumerates all configured addresses on all network interfaces. **The loopback interface and IPv6 link-local addresses are omitted**. Contrary to option -i, this option does not depend on name resolution. Do not make any assumptions about the order of the output.
  
  ### [How to find the MAC address of your server?](https://linux.die.net/man/8/ip)
  
    `ip link | grep "ether" | awk '{print($2)}'`
  
- [x] _The number of commands executed with the sudo program._
  
  `sudo ls var/log/sudo/00/00 | wc -l`
  
  ![image](https://user-images.githubusercontent.com/60623613/143683681-67835b30-3f88-4e37-9d58-d44a68917720.png)
  
_This is an example of how the script is expected to work:_
  
![image](https://user-images.githubusercontent.com/60623613/143685573-9cea8162-ec76-43f4-bbc0-e5832727e99a.png)

ℹ️ **INFO**: _During the defense, you will be asked to explain how this script works. **You will also have to interrupt it without modifying it**. **Take a look at cron**._
  
### [What is cron?](https://debian-handbook.info/browse/stable/sect.task-scheduling-cron-atd.html)
  
>cron is the [daemon](https://en.wikipedia.org/wiki/Daemon_(computing)) responsible for executing scheduled and recurring commands (every day, every week, etc.). 
  
>By default, all users can schedule the execution of tasks. Each user has thus their own crontab
in which they can record scheduled commands. It can be edited by running `crontab -e` (its
content is stored in the /var/spool/cron/crontabs/user file).

### [What is crontab?](https://linux.die.net/man/5/crontab)

>A crontab file contains instructions to the cron(8) daemon of the general form: "run this command at this time on this date". Each user has their own crontab, and commands in any given crontab will be executed as the user who owns the crontab.

### [How to display some information on all terminals every 10 minutes?](https://www.cyberciti.biz/faq/crontab-every-10-min/)
  
>To get crontab to run a task every 10 minutes you could type as follow:

  >`*/10 * * * * /path/to/script`
  
>The */10 is used in conjunction with ranges. For example, 0-23/2 can be used in the hours field to specify command execution every other hour. Steps are also permitted after an asterisk, so if you want to say every two hours just use */2. In this example, */10 in the minutes field to specify command execution every 10 minutes.
  
![image](https://user-images.githubusercontent.com/60623613/144088241-0a2c0131-d4d0-40fd-9d8f-a5061c1bb259.png)
  
### [How to interrupt the script without modifying it?](https://www.debian.org/doc/manuals/debian-handbook/sect.task-scheduling-cron-atd.en.html)
  
>To cancel a task scheduled by cron, simply run crontab -e and delete the corresponding line in the crontab file.

## Submission and peer-evaluation
  
>To get the signature, you first have to open the default installation folder
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
  
ℹ️ **INFO**: _Please note that your virtual machine’s signature may be altered after your first evaluation. **To solve this problem, you can duplicate your virtual machine or use save state**._
  
### [How to save state of a virtual machine?](https://www.virtualbox.org/manual/UserManual.html#snapshots)
  
>With snapshots, you can save a particular state of a virtual machine for later use. At any later time, you can revert to that state, even though you may have changed the VM considerably since then. A snapshot of a virtual machine is thus similar to a machine in Saved state, but there can be many of them, and these saved states are preserved.
  
>To see the snapshots of a virtual machine, click on the machine name in VirtualBox Manager. Then click the List icon next to the machine name, and select Snapshots. Until you take a snapshot of the machine, the list of snapshots will be empty except for the Current State item, which represents the "now" point in the lifetime of the virtual machine.
  
>Restore a snapshot. In the list of snapshots, right-click on any snapshot you have taken and select Restore. By restoring a snapshot, you go back or forward in time. The current state of the machine is lost, and the machine is restored to the exact state it was in when the snapshot was taken.
  
>Think of a snapshot as a point in time that you have preserved. More formally, a snapshot consists of the following:

  >- The snapshot contains a complete copy of the VM settings, including the hardware configuration, so that when you restore a snapshot, the VM settings are restored as well. For example, if you changed the hard disk configuration or the VM's system settings, that change is undone when you restore the snapshot.
  
  >- The complete state of all the virtual disks attached to the machine is preserved. Going back to a snapshot means that all changes that had been made to the machine's disks, file by file and bit by bit, will be undone as well. Files that were since created will disappear, files that were deleted will be restored, changes to files will be reverted.
  
![image](https://user-images.githubusercontent.com/60623613/144112142-125c6bb6-dea3-433b-8a55-bb073b84d872.png)
  
⚠️ **WARNING:** _It is of course FORBIDDEN to turn in your virtual machine in your Git repository. During the defense, the signature of the signature.txt file will be compared with the one of your virtual machine. If the
two of them are not identical, your grade will be 0._
