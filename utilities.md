# Utilities

## Create Python virtual environment

Create and activate an isolated Python environment.

```bash
python3 -m venv .venv
source .venv/bin/activate
```

## Deactivate virtual environment

Leave the active Python virtual environment.

```bash
deactivate
```

## Serve files over HTTP

Serve the current directory for a simple authorized file transfer.

```bash
python3 -m http.server <LPORT>
```

## Download over HTTP

Download a file from a temporary HTTP server.

```bash
wget http://<LHOST>:<LPORT>/<FILE>
```
