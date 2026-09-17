# Recon

## Host discovery

Find live hosts in an authorized network range.

```bash
nmap -oA network-discovery -sn <CIDR>
```

## Fast TCP triage

Identify common TCP services before deeper scanning.

```bash
nmap --top-ports 1000 -sV -oA tcp-triage <TARGET>
```

## Full TCP service scan

Scan every TCP port and run default scripts against discovered services.

```bash
nmap -p- -sC -sV -oA tcp-scan <TARGET>
```

## Limited UDP follow-up

Check the most common UDP ports when the scope permits it.

```bash
nmap -sU --top-ports 20 -sV -oA udp-scan <TARGET>
```
