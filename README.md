# NetBox Sync Ops

Agent skill for operating and safely extending [netbox-proxmox-sync](https://github.com/eddygk/netbox-proxmox-sync), an idempotent, cron-driven sync that models Proxmox VE and UniFi into NetBox DCIM/IPAM.

This repo is the operator runbook for agents (OpenClaw, Claude Code, Codex and other `SKILL.md`-based agents). The sync tool itself, with its install and configuration docs, lives in the netbox-proxmox-sync repo.

**Published skill:** https://clawhub.ai/eddygk/netbox-sync-ops

## What it covers

- Deploying the sync and running it on a schedule
- Adding a sync phase without breaking idempotency
- Tuning the VM removal lifecycle (the reaper)
- Enabling iDRAC/Redfish node enrichment
- Debugging churn and resolving NetBox API HTTP 400s
- Safety rules: NetBox is written only through its REST API, Proxmox and UniFi are read-only, and destructive tests never touch production records

## Files

- [`SKILL.md`](SKILL.md): the skill (safe operating procedure)
- [`references/gotchas.md`](references/gotchas.md): NetBox and UniFi API gotchas
- [`references/extending.md`](references/extending.md): how to add a phase
- [`agents/openai.yaml`](agents/openai.yaml): agent metadata for OpenAI Codex
- [`skill-card.md`](skill-card.md): ClawHub skill card

## Requirements

`python3`, plus `NETBOX_URL`, `NETBOX_TOKEN`, `PROXMOX_HOST`, `PROXMOX_TOKEN_ID` and `PROXMOX_TOKEN_SECRET` in the environment (see `SKILL.md`).

## License

MIT, see [LICENSE](LICENSE).
