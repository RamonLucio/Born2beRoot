# Born2beRoot
## Summary
_This document is a **System Administration** related exercise._
### What is a System Administrator?
>A [system administrator](https://en.wikipedia.org/wiki/System_administrator) is a person who is responsible for the upkeep, configuration, and reliable operation of computer systems; especially multi-user computers, such as servers. The system administrator seeks to ensure that the uptime, performance, resources, and security of the computers they manage meet the needs of the users, without exceeding a set budget when doing so.
## Introduction
_This project aims to introduce you to the wonderful world of **virtualization**._

_You will **create your first machine** in **VirtualBox** (or UTM if you can’t use VirtualBox)
under specific instructions. Then, at the end of this project, you will be able to set up
your own operating system while implementing strict rules._
### What is virtualization and what is VirtualBox?
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

## General guidelines
_The use of VirtualBox (or UTM if you can’t use VirtualBox) is mandatory._

_You only have to turn in a signature.txt file at the root of your repository. You
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
_⚠️ **WARNING:** Since it is a matter of setting up a server, you will install the
minimum of services. For this reason, a **graphical interface** is of no
use here. It is therefore forbidden to install X.org or any other
equivalent graphics server. Otherwise, your grade will be 0._
### What is a graphical interface?
>The [graphical user interface](https://en.wikipedia.org/wiki/Graphical_user_interface) (GUI) 
allows users to interact with electronic devices through graphical icons and audio indicator such as primary notation, instead of text-based user interfaces, typed command labels or text navigation.

_You must choose as an operating system either the latest stable version of **Debian** (no
testing/unstable), or the latest stable version of **CentOS**. Debian is highly recommended
if you are new to system administration._
### Why choose Debian?
>There are a lot of reasons to [choose Debian](https://www.debian.org/intro/why_debian) as your operating system – as a user, as a developer, and even in enterprise environments. Most users appreciate the stability, and the smooth upgrade processes of both packages and the entire distribution. Debian is also widely used by software and hardware developers because it runs on numerous architectures and devices, offers a public bug tracker and other tools for developers. If you plan to use Debian in a professional environment, there are additional benefits like LTS versions and cloud images.
### Why choose the latest stable version?
>The [latest release](https://wiki.debian.org/DebianReleases) is Debian 11.1. It is also (currently) known as stable or by its codename "Bullseye".At any given time, there is one stable release of Debian, which has the support of the Debian security team. When a new stable version is released, the security team will usually cover the previous version for a year or so, while they also cover the new/current version. Only stable is recommended for production use. Stable is recommended for applications requiring production-level stability and security (servers, firewalls etc) and is also recommended for those who are new to Linux.

ℹ️ **INFO:** Setting up CentOS is quite complex. Therefore, you don’t have to
set up KDump. However, SELinux must be running at startup and its
configuration has to be adapted for the project’s needs. AppArmor
for Debian must be running at startup too.
### What is AppArmor?
>[AppArmor](https://debian-handbook.info/browse/stable/sect.apparmor.html) is a Mandatory Access Control (MAC) system built on Linux's LSM (Linux Security Modules) interface. In practice, the kernel queries AppArmor before each system call to know whether the process is authorized to do the given operation. Through this mechanism, AppArmor confines programs to a limited set of resources.

>AppArmor applies a set of rules (known as “profile”) on each program. The profile applied by the kernel depends on the installation path of the program being executed. Contrary to SELinux, the rules applied do not depend on the user. All users face the same set of rules when they are executing the same program (but traditional user permissions still apply and might result in different behavior!).

>AppArmor profiles are stored in /etc/apparmor.d/ and they contain a list of access control rules on resources that each program can make use of. The profiles are compiled and loaded into the kernel by the apparmor_parser command. Each profile can be loaded either in enforcing or complaining mode. The former enforces the policy and reports violation attempts, while the latter does not enforce the policy but still logs the system calls that would have been denied.
### What is Mandatory Access Control?
>In computer security, [mandatory access control](https://en.wikipedia.org/wiki/Mandatory_access_control) (MAC) refers to a type of access control by which the operating system or database constrains the ability of a subject or initiator to access or generally perform some sort of operation on an object or target. In the case of operating systems, a subject is usually a process or thread; objects are constructs such as files, directories, TCP/UDP ports, shared memory segments, IO devices, etc. Subjects and objects each have a set of security attributes. Whenever a subject attempts to access an object, an authorization rule enforced by the operating system kernel examines these security attributes and decides whether the access can take place. Any operation by any subject on any object is tested against the set of authorization rules (aka policy) to determine if the operation is allowed
### How to check if AppArmor is running?
>The [`aa-status`](https://gitlab.com/apparmor/apparmor/-/wikis/AppArmorMonitoring#high-level-view) tool gives a high level status of AppArmor and applications it has profiles for (as root).

![image](https://user-images.githubusercontent.com/60623613/140406297-12047d36-09da-4e33-a19f-98dd45e55b34.png)

You must create at least 2 encrypted partitions using LVM. Below is an example of the
expected partitioning:

![image](https://user-images.githubusercontent.com/60623613/140404704-3dba0778-8f45-41c8-9cdd-757b2c1d93ec.png)
