+++
date = '2026-11-06T20:45:23-06:00'
draft = false
title = 'Lab'
hidemeta = true
+++

My home lab is where I practice the skills behind a SOC analyst role: building systems, monitoring them, breaking them on purpose, and writing up what I find.

## Hardware

| Machine | Role | Status |
|---|---|---|
| Dell OptiPlex 7060 SFF | Primary Proxmox VE host | Running |
| Dell Precision T7810 (Xeon E5-2620 v3, 32 GB RAM, SATA SSD) | Secondary host for heavier workloads | Planned |
| Dell OptiPlex 3060 Micro | Small utility node (RAM and NVMe upgrade) | In progress |

## Platform

- **Hypervisor:** Proxmox VE on the OptiPlex 7060, managed over SSH and the web UI
- **Virtual machines:** Ubuntu VM for general testing
- **Containers:** a Jellyfin LXC with Intel Quick Sync passthrough (in progress)

## Security lab (in progress)

I'm building a Wazuh SIEM environment to practice detection and log analysis:

- A Wazuh server VM (Ubuntu)
- Linux and Windows agent VMs that generate and forward logs
- Planned work: simulate common attacker techniques, detect them, map each detection to MITRE ATT&CK, and write up the results

Each step will be published as a write-up on this site.

## Planned services

Pi-hole, Vaultwarden, Gitea, Nextcloud, and a local LLM setup, each hardened and documented as I add it.

## Architecture (planned)

```
Proxmox host
 ├── wazuh-server (Ubuntu)   <- collects and analyzes logs
 ├── linux-agent  (Linux)    -> sends logs
 └── windows-agent (Windows) -> sends logs
```

I'll replace this with a proper diagram once the build is finished.