# Jordens | Cybersecurity Lab Portfolio

I am moving into cybersecurity, with a focus on Governance, Risk, and Compliance (GRC). I am studying for CompTIA Security+ (SY0-701) and plan to sit the exam by the end of November 2026.

This repo documents infrastructure I built and run myself. Each project covers what I built, the steps I took, the problems I hit, and how the work maps to NIST CSF 2.0 and CIS Controls v8. The mappings and the risk register are the GRC side of the work. Following a tutorial shows you followed a tutorial. Mapping each setting to a control shows you know why the setting exists.

## Projects

| # | Project | What I built | Status |
|---|---------|--------------|--------|
| 01 | [Self-hosted WireGuard VPN](01-wireguard-travel-vpn/README.md) | Travel router and home server router that encrypt my traffic on coffee shop and coworking Wi-Fi | Running |
| 02 | [Homelab server](02-homelab-server/README.md) | Debian 13 server running Docker services for DNS filtering, media, automation, and uptime monitoring | Running |
| GRC | [Risk register](docs/risk-register.md) | Risks across both projects, with likelihood, impact, treatment, and status | Living document |

## Skills shown

- Networking: public Wi-Fi protection, port forwarding, NAT and IP masquerading, dynamic DNS, firewall zones, UDP versus TCP testing, IPv6 leak prevention
- Linux administration: Debian 13, static addressing, SSH, Samba file sharing
- Containers: Docker Compose, one folder per service
- Monitoring and alerting: Uptime Kuma with push alerts through ntfy
- Automation: n8n workflows
- GRC: asset documentation, control mapping (NIST CSF 2.0, CIS Controls v8), risk register, gap tracking

## What I removed before publishing

Public IP addresses, DDNS hostnames, MAC addresses, WireGuard keys, passwords, and usernames are out of this repo. Private addresses in config examples are placeholders. The `.gitignore` blocks key files, `.env` files, router backups, and my private reference documents.

Before every push I run this check and review each hit:

```bash
grep -rniE "privatekey|presharedkey|password|passwd|glddns|token|([0-9]{1,3}\.){3}[0-9]{1,3}" .
```

## Roadmap

- [ ] CompTIA Security+ (SY0-701), target end of November 2026
- [ ] Run a Lynis audit on the homelab server, fix findings, and publish before and after results
- [ ] Build a 3-2-1 backup plan for the homelab and document a test restore
- [ ] Write a policy set for my home network: acceptable use, access control, patch management
- [ ] Complete a NIST CSF 2.0 self-assessment of the full home network, with a current profile, target profile, and gap list

## Contact

LinkedIn: https://www.linkedin.com/in/jrena/
