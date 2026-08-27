# Enumeration

Run only against targets in scope.

## Network discovery

```bash
nmap -sn <CIDR> -oA <OUTPUT_PREFIX>-discovery
```

## TCP service scan

```bash
nmap -p- -sC -sV -oA <OUTPUT_PREFIX>-tcp <TARGET>
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
