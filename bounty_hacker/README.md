Bounty Hacker | THM | Vishakhan Pillai | 23 - 05 - 2025


```
IP = 10.10.84.239

```

## Nmap Scan

```
# Nmap 7.94SVN scan initiated Fri May 23 00:32:43 2025 as: nmap -sC -sV -oN nmap/intial -vv 10.10.84.239
Nmap scan report for 10.10.84.239
Host is up, received syn-ack (0.21s latency).
Scanned at 2025-05-23 00:32:43 IST for 61s
Not shown: 967 filtered tcp ports (no-response)
PORT      STATE  SERVICE         REASON       VERSION
20/tcp    closed ftp-data        conn-refused
21/tcp    open   ftp             syn-ack      vsftpd 3.0.3
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT
| ftp-syst: 
|   STAT: 
| FTP server status:
|      Connected to ::ffff:10.17.58.216
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 1
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
22/tcp    open   ssh             syn-ack      OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 dc:f8:df:a7:a6:00:6d:18:b0:70:2b:a5:aa:a6:14:3e (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCgcwCtWTBLYfcPeyDkCNmq6mXb/qZExzWud7PuaWL38rUCUpDu6kvqKMLQRHX4H3vmnPE/YMkQIvmz4KUX4H/aXdw0sX5n9jrennTzkKb/zvqWNlT6zvJBWDDwjv5g9d34cMkE9fUlnn2gbczsmaK6Zo337F40ez1iwU0B39e5XOqhC37vJuqfej6c/C4o5FcYgRqktS/kdcbcm7FJ+fHH9xmUkiGIpvcJu+E4ZMtMQm4bFMTJ58bexLszN0rUn17d2K4+lHsITPVnIxdn9hSc3UomDrWWg+hWknWDcGpzXrQjCajO395PlZ0SBNDdN+B14E0m6lRY9GlyCD9hvwwB
|   256 ec:c0:f2:d9:1e:6f:48:7d:38:9a:e3:bb:08:c4:0c:c9 (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBMCu8L8U5da2RnlmmnGLtYtOy0Km3tMKLqm4dDG+CraYh7kgzgSVNdAjCOSfh3lIq9zdwajW+1q9kbbICVb07ZQ=
|   256 a4:1a:15:a5:d4:b1:cf:8f:16:50:3a:7d:d0:d8:13:c2 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAICqmJn+c7Fx6s0k8SCxAJAoJB7pS/RRtWjkaeDftreFw
80/tcp    open   http            syn-ack      Apache httpd 2.4.18 ((Ubuntu))
|_http-server-header: Apache/2.4.18 (Ubuntu)
|_http-title: Site doesn't have a title (text/html).
| http-methods: 
|_  Supported Methods: OPTIONS GET HEAD POST
990/tcp   closed ftps            conn-refused
40193/tcp closed unknown         conn-refused
40911/tcp closed unknown         conn-refused
41511/tcp closed unknown         conn-refused
42510/tcp closed caerpc          conn-refused
44176/tcp closed unknown         conn-refused
44442/tcp closed coldfusion-auth conn-refused
44443/tcp closed coldfusion-auth conn-refused
44501/tcp closed unknown         conn-refused
45100/tcp closed unknown         conn-refused
48080/tcp closed unknown         conn-refused
49152/tcp closed unknown         conn-refused
49153/tcp closed unknown         conn-refused
49154/tcp closed unknown         conn-refused
49155/tcp closed unknown         conn-refused
49156/tcp closed unknown         conn-refused
49157/tcp closed unknown         conn-refused
49158/tcp closed unknown         conn-refused
49159/tcp closed unknown         conn-refused
49160/tcp closed unknown         conn-refused
49161/tcp closed unknown         conn-refused
49163/tcp closed unknown         conn-refused
49165/tcp closed unknown         conn-refused
49167/tcp closed unknown         conn-refused
49175/tcp closed unknown         conn-refused
49176/tcp closed unknown         conn-refused
49400/tcp closed compaqdiag      conn-refused
49999/tcp closed unknown         conn-refused
50000/tcp closed ibm-db2         conn-refused
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Fri May 23 00:33:44 2025 -- 1 IP address (1 host up) scanned in 61.52 seconds

```
1. Deploy the machine.

```
No Answer Needed
```

2. Find open ports on the machine

```
No Answer Needed
```

3. Who wrote the task list?

```
lin
```


4. What service can you bruteforce with the text file found?

```
SSH
```

5. What is the users password? 

```
RedDr4gonSynd1cat3
```

6. user.txt

```
THM{CR1M3_SyNd1C4T3}
```

7. root.txt

```
THM{80UN7Y_h4cK3r}
```