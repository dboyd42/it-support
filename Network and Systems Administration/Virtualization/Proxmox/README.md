# How to Set Up a Cybersecurity Home Lab using Proxmox

**Author:** David Boyd<br>
**Date:** 2023-06-28

- [Introduction](#introduction)
- [Prerequisites](#prerequisites)
- [Steps](#steps)
  - [Step 1: Proxmox][1-pve]
  - [Step 2: pfSense][2-pfsense]
  - [Step 3: Kali][3-kali]
  - [Step 4: Vulnerable VMs][4-vms]
  - [Step 5: Active Directory][5-ad]
- [Conclusion](#conclusion)
- [Tips and Best Practices](#tips-and-best-practices)
- [Additional Resources](#additional-resources)

## Introduction

This guide aims to set up a Proxmox Virtual Environment (PVE) on a home
server, such as a server, desktop, or laptop, with the purpose of creating a
cybersecurity home lab. The lab's main objective is to provide a platform for
practicing penetration testing and incident response techniques. It includes
the setup of various vulnerable boxes and environments, including Active
Directory, to simulate real-world scenarios for hands-on learning.
Additionally, the guide covers configuring secure internet access using
CloudFlare, setting up routing, VLANs, and firewall using pfSense, and
enabling remote accessibility to an attack machine from anywhere in the world.

## Prerequisites

*#TODO*

## Steps

### Step 1: Proxmox

#### Post-Installation

##### 1. Remove Subscription Message

``` bash
# 1. Create a backup config of proxmoxlib.js
cp /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js \
/usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js.bak

# 2. Edit the following function
vim /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js 

  ## Search for:
  Ext.Msg.show({
    title: gettext('No valid subscription'),

  ## Replace with:
  void({
    title: gettext('No valid subscription'),

# 4. Restart the PVE Proxy service
systemctl restart pveproxy.service
```

##### 2. Setup Online Access via Cloudflare Tunneling

*#TODO*

### Step 2: pfSense

*#TODO*

#### Setup a 'Kali' Host Alias

*#TODO*

| Setting | Value                            |
|---------|----------------------------------|
| Name    | Kali                             |
| IP      | 10.0.0.2                         |
| MAC     | *Copy from image and paste here* |

### Step 3: Kali

*#TODO*

:bulb: When attaching the disk, append the `.raw` extension 

``` bash
# Attach the disk (examples of locations and syntax)
qm set 106 --scsi0 local-btrfs:106/vm-106-disk-0.raw
qm set 7001 --ide0 local-btrfs:7001/vm-7001-disk-0.raw
```

### Step 4: Vulnerable VMs

*#TODO*

### Step 5: Active Directory

*#TODO*

## Tips and Best Practices

1. :x: Don't be a script kiddie
    - :question: Question everything :question:
    - :book: Learn about what's going on beneath the hood :car:
    - :bulb: Learn what each command actually performs :computer:

## Conclusion

## Additional Resources

This project is LARGELY thanks to **Ben Heater's** [Proxmox VE 7: 
Converting a Laptop into a Bare Metal Server][bh-pve] series. 

<!-- Reference Links -->

[1-pve]: hxxps://TODO
[2-pfsense]: hxxps://TODO
[3-kali]: hxxps://TODO
[4-vms]: hxxps://TODO
[5-ad]: hxxps://TODO
[bh-pve]: https://benheater.com/bare-metal-proxmox-laptop/
