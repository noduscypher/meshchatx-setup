# meshchatx-setup

MeshChatX installation and startup scripts for macOS — Reticulum mesh communication over LXMF.

## about

This repository documents the installation and configuration of MeshChatX
on macOS, connecting to a Reticulum mesh network with NomadNet and LXMF support.

## stack

- MeshChatX (reticulum-meshchatx)
- Reticulum Network Stack
- LXMF
- macOS (Apple Silicon)
- Python 3.11 virtual environment

## requirements

- macOS 12+
- Python 3.11+
- Node.js 20+
- pnpm
- git

## installation

```bash
# clone MeshChatX source
git clone https://git.quad4.io/RNS-Things/MeshChatX.git meshchatx-src
cd meshchatx-src

# create virtual environment
python3 -m venv ~/meshchatx-venv
source ~/meshchatx-venv/bin/activate

# install dependencies
pip install git+https://git.quad4.io/RNS-Things/MeshChatX.git

# build frontend
pnpm install && pnpm run build-frontend
```

## startup

```bash
#!/bin/bash
ulimit -n 4096
source "$HOME/meshchatx-venv/bin/activate"
meshchatx --headless --host 127.0.0.1 --port 8787 --no-https \
  --reticulum-config-dir "$HOME/.reticulum" \
  --public-dir "$HOME/meshchatx-src/meshchatx/public"
```

Open browser at `http://127.0.0.1:8787`

## license

Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

---

*walk quietly, but keep the signal alive.*

₿uilt with Love  🧡  in cooperation with Nature  🌿
