# CEH-Practical

## Footprinting and recon
#### Reverse image serach
```bash
https://mattw.io/youtube-metadata/
```
#### Ping finding  maximum packet/frame size
```bash
ping <address> -f -l 1500
```

#### Find primary server with nslookup 
```bash
nslookup -querytype=soa <URL>
```

## Scanning Netwroks
#### ICMP Echo
```bash
nmap <IP/mask>
```
#### OS-discovery
```bash
sudo nmap --script smb-os-discovery.nse
```

#### Netdiscover
```bash
sudo netdiscover -i eth0
```
#### Nmap scan IP's
```bash
nmap -sn IP-Address/mask -oG liveip.txt
```
#### Nmap scan ports and version on IP
```bash
nmap -sV -p IP-Address
```
## Enumeration
#### NetBIOS Enumeration
```bash
nbtscan -v -s : <target-ip-or-hostname>
```
```bash
nmap -sV 172.16.1.102 --script nbstat.nse
```
#### SNMP-check to find information about a host
```bash
snmp-check <target-ip-address>
```
##### You can alose perfom a SNMP enumeration using SoftPerfect on the windows machine :)
#### LDAP enumeration
##### You can alose perfom a LDAP enumeration by the tool on thw windows machine named "Active Directory Explorer"
## Service brute force
#### DNS enumeration
```bash
dnsenum <hostname>
```
#### Reversese lookup
#### Just use nslookup
```bash
nslookup <IP-Address>
```
#### SMTP list number of users
```bash
nmap --script smtp-enum-users <target>
```
#### Find http-server-header
```bash
nmap -sV -A -p 80 <target>
```

#### Enum4linux to find  users, groups, shares, (RID)
```bash
enum4linux <target>
```

## Vulnerability analysis
### can vulnerbilites with nikto to find uncommon header
```bash
nikto -h (Target Website) -Tuning x
```
### See if smb signing is enabled
```bash
nmap -p137,139,445 --script smb-security-mode <target>
```
#### FTP brute force
```bash
hydra -L userlist.txt -P passwordlist.txt ftp://IP-Address -V
```
#### See content
```bash
ftp://IP-Address/folder
```

#### SSH brute force
```bash
hydra -L userlist.txt -P passwordlist.txt IP-Address ssh -V
```

## SQL

dsss.py

## Steganography
#### Snow
```bash
-C -p password output.txt
```
