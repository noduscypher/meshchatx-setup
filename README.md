Setup notes, scripts, and documentation for MeshChatX on macOS and Reticulum-based environments.

These instructions are designed to integrate with a broader off-grid communication stack (Reticulum, NomadNet, LXMF and rawmesh-node), focusing on reproducible installs and low-friction daily use.

# meshchatx-setup

Setup notes, scripts, and documentation for MeshChatX on macOS and Reticulum-based environments.

This repository documents installation, startup, configuration, and daily workflow for MeshChatX in resilient communication setups.

## scope

- local installation on macOS
- startup scripts for headless mode
- configuration notes for Reticulum
- workflow verification
- troubleshooting references

## stack

- MeshChatX (reticulum-meshchatx)
- Reticulum Network Stack
- LXMF
- macOS (Apple Silicon)
- Python 3.11+ virtual environment

## requirements

- macOS 12+ on Apple Silicon (Intel may require adjustments)
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

## typical startup

Use a dedicated Python environment, start MeshChatX in headless mode, and verify access through the local browser interface.

```bash
#!/bin/bash
ulimit -n 4096
source "$HOME/meshchatx-venv/bin/activate"
meshchatx --headless --host 127.0.0.1 --port 8787 --no-https \
  --reticulum-config-dir "$HOME/.reticulum" \
  --public-dir "$HOME/meshchatx-src/meshchatx/public"
```

Open browser at `http://127.0.0.1:8787`

## notes

This repository is written for practical use, repeatability, and low-friction deployment.

For remote assistance workflows, see [REMOTE-ASSIST.md](./REMOTE-ASSIST.md).

---

## related repositories

- `rawmesh-node` – Reticulum mesh node setup on Raspberry Pi 4 (NomadNet, LXMF, off-grid ready).  
  https://github.com/noduscypher/rawmesh-node

- `mesh-guides` – Meshtastic EU868 documentation (PT/EN/ES) for presets, roles and regulation-aware operation.  
  https://github.com/noduscypher/mesh-guides

  

Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

*walk quietly, but keep the signal alive.*

₿uilt with Love  🧡  in cooperation with Nature  🌿
