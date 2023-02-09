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

## Service brute force
#### FTP brute force
```bash
hydra -L userlist.txt -P passwordlist.txt ftp://IP-Address -V
```#### See content
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
