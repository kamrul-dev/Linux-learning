# How to Find Linux Distribution and System Information

There are multiple commands available in Linux to determine the distribution, kernel version, and hardware details. Below are practical examples of how to gather this information.

## 1. Finding Linux Distribution Information

### 1.1 Using `/etc/os-release`
The `/etc/os-release` file contains the distribution details. This method works across most Linux distros.

#### Command:
```bash
cat /etc/os-release
```
#### Example Output:
```
NAME="Ubuntu"
VERSION="20.04.4 LTS (Focal Fossa)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 20.04.4 LTS"
VERSION_ID="20.04"
```

### 1.2 Using `lsb_release` (if available)
The `lsb_release` command displays distribution information.

#### Command:
```bash
lsb_release -a
```
#### Example Output:
```
Distributor ID: Ubuntu
Description:    Ubuntu 20.04.4 LTS
Release:        20.04
Codename:       focal
```

### 1.3 Using `hostnamectl`
This command is used for system control and can also show distribution details.

#### Command:
```bash
hostnamectl
```
#### Example Output:
```
Static hostname: myhost
Icon name: computer-vm
Chassis: vm
Machine ID: b47dfd3f64fb4653ae339c617e401cb1
Boot ID: 3b8492d8e53b4ae5ac46f86a1a44780d
Operating System: Ubuntu 20.04.4 LTS
Kernel: Linux 5.4.0-110-generic
Architecture: x86-64
```

---

## 2. Checking Kernel Version

To find out the kernel version of your Linux system:

### 2.1 Using `uname`
The `uname` command provides information about the kernel.

#### Command:
```bash
uname -r
```
#### Example Output:
```
5.4.0-110-generic
```

### 2.2 Full Kernel Information with `uname -a`
To get more detailed kernel and system architecture information:

#### Command:
```bash
uname -a
```
#### Example Output:
```
Linux myhost 5.4.0-110-generic #124-Ubuntu SMP Fri Mar 18 14:21:40 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
```

---

## 3. Finding Hardware Information

### 3.1 Using `lscpu` (CPU Information)
The `lscpu` command provides detailed CPU architecture information.

#### Command:
```bash
lscpu
```
#### Example Output:
```
Architecture:        x86_64
CPU(s):              4
Model name:          Intel(R) Core(TM) i7-8650U CPU @ 1.90GHz
CPU MHz:             2112.123
Virtualization:      VT-x
```

### 3.2 Using `free` (Memory Information)
The `free` command displays memory usage details.

#### Command:
```bash
free -h
```
#### Example Output:
```
              total        used        free      shared  buff/cache   available
Mem:           7.6Gi       2.5Gi       4.5Gi        211Mi       570Mi       4.5Gi
Swap:          2.0Gi          0B       2.0Gi
```

### 3.3 Using `df` (Disk Usage Information)
The `df` command shows the disk space usage of the file system.

#### Command:
```bash
df -h
```
#### Example Output:
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda1        50G   15G   33G  31% /
```

### 3.4 Using `lshw` (Detailed Hardware Information)
The `lshw` command provides detailed information about all hardware.

#### Command:
```bash
sudo lshw
```
#### Example Output (truncated):
```
  *-cpu
       description: CPU
       product: Intel(R) Core(TM) i7-8650U CPU @ 1.90GHz
       vendor: Intel Corp.
       physical id: 3
       bus info: cpu@0
       size: 2112MHz
       capacity: 4200MHz
  *-memory
       description: System Memory
       physical id: 4
       size: 8GiB
```

---

## 4. Checking System Uptime

To find out how long your system has been running:

#### Command:
```bash
uptime
```
#### Example Output:
```
 15:03:41 up 5 days,  4:31,  2 users,  load average: 0.03, 0.10, 0.11
```

---

## 5. Checking Network Information

### 5.1 Using `ip a` (IP Address Information)
To view network interfaces and IP addresses:

#### Command:
```bash
ip a
```
#### Example Output (truncated):
```
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000
    inet 192.168.1.10/24 brd 192.168.1.255 scope global dynamic enp0s3
       valid_lft 86110sec preferred_lft 86110sec
```

### 5.2 Using `ifconfig` (Legacy Network Info)
Older Linux systems may use `ifconfig` to display network interface information.

#### Command:
```bash
ifconfig
```
---

## Conclusion

These commands give you detailed information about your Linux system, including the distribution name, kernel version, hardware details, and network information. You can use them to troubleshoot, monitor, and understand your system's configuration.
