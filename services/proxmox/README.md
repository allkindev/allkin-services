# Proxmox VE

Virtual machines, containers, nodes, storage, tasks.

## The token

**Datacenter → Permissions → API Tokens → Add**: pick the user, give the token an
id, and leave **Privilege Separation** on so the token's rights are set apart.
Then **Permissions → Add → API Token Permission** on the paths it may touch
(`/` with `PVEAuditor` for reading, `PVEVMAdmin` to act on VMs).

Enter the key as `user@realm!tokenid=secret`, in one piece, exactly as shown
once by Proxmox. The address is `https://host:8006`.

## Good to know

Proxmox ships a self-signed certificate: Allkin refuses it. Put a real one on
the node, or reach it through a reverse proxy that has one. Stopping, rebooting
and deleting ask for your confirmation.
