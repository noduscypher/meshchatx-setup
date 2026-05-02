# Remote assist workflow

This guide is for helping another person install and configure MeshChatX remotely.

## goal

Provide a safe and repeatable workflow for remote assistance without losing track
of environment details, startup commands, or Reticulum configuration.

## before starting

Confirm the following with the other person:

- operating system and version
- terminal access available
- Python version installed
- whether MeshChatX is already installed
- whether Reticulum is already installed
- whether remote access (SSH / Tailscale / Screen Sharing) is available
- whether they can share terminal output clearly

## remote access setup

Recommended path:

1. Both parties install [Tailscale](https://tailscale.com/download/mac).
2. The remote user shares their node from the Tailscale admin panel.
3. The remote user enables **Remote Login** in System Settings → General → Sharing.
4. The operator connects via SSH using the Tailscale IP:

```bash
ssh username@100.x.x.x
```

## remote workflow

1. Identify the operating system and current state of the machine.
2. Confirm whether Python and virtual environment tools are available.
3. Create or activate the correct virtual environment.
4. Install MeshChatX and required dependencies.
5. Verify Reticulum configuration paths (`~/.reticulum/config`).
6. Build the frontend if needed (`pnpm install && pnpm run build-frontend`).
7. Launch MeshChatX in headless mode with `--no-https`.
8. Confirm that the browser interface loads correctly at `http://127.0.0.1:8787`.
9. Save or create a startup script for future use.
10. Document the final working command on the user's machine.

## good practice

Always keep a copy of:

- the final working command
- the path of the virtual environment
- the Reticulum config path
- the startup script name and location
- any machine-specific fixes applied
- the user's LXMF identity hash

## verification checklist

- [ ] Tailscale connected on both sides
- [ ] SSH access working
- [ ] Python virtual environment created
- [ ] MeshChatX installed
- [ ] Frontend built and accessible
- [ ] Reticulum interfaces configured
- [ ] Startup script created and executable
- [ ] Browser interface loads correctly
- [ ] LXMF identity generated and noted
- [ ] First contact established with another node

## support note

Remote setup is easier when changes are documented line by line and confirmed
immediately after each step. Never assume — always verify the output before
moving to the next command.

---

Licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

*walk quietly, but keep the signal alive.*

₿uilt with Love  🧡  in cooperation with Nature  🌿
