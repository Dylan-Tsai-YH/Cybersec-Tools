## Python virtual environment
```bash
python3 -m venv .venv
source .venv/bin/activate
```
```bash
deactivate
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