# Risk Register

Covers both lab projects. Each risk gets a likelihood and impact score from 1 (low) to 3 (high). Score = likelihood x impact. I review this register each time I change either project.

Treatment options: **Mitigate** (reduce the risk), **Accept** (live with the risk and document why), **Transfer** (hand the risk to a third party), **Avoid** (stop the activity).

| ID | Asset | Risk | L | I | Score | Treatment | Action | Status |
|----|-------|------|---|---|-------|-----------|--------|--------|
| R-01 | This repo | Keys, public IPs, or hostnames get pushed to a public repo | 2 | 3 | 6 | Mitigate | `.gitignore` blocks secrets and backups. Grep check before every push. Placeholders in all config examples | Mitigated |
| R-02 | Home upstream router | SPI firewall on the upstream router is off, so the router does less inspection of inbound traffic | 2 | 2 | 4 | Mitigate | Turn SPI back on, confirm the tunnel still connects, and test from cellular | Open |
| R-03 | Home VPN server | Server router hangs while I'm away, with nobody home to reboot the hardware | 2 | 3 | 6 | Mitigate | Smart plug on the ISP gateway's Wi-Fi for remote power cycling. Tailscale fallback guide in the meantime | Open |
| R-04 | Homelab server | Single 256 GB NVMe, no backups. One disk failure loses configs, workflows, and media | 2 | 3 | 6 | Mitigate | 3-2-1 backup plan for `~/docker` configs and n8n workflows, then a documented test restore | Open (roadmap) |
| R-05 | Homelab server | Static IP set on the host while the ISP router hands out leases I cannot see. Another device takes the same address | 1 | 2 | 2 | Accept | No router admin access. Uptime Kuma alerts me if the server drops off the network | Accepted |
| R-06 | Homelab server | Debian packages and container images fall behind on security patches | 2 | 2 | 4 | Mitigate | Written patch schedule: monthly `apt upgrade` and image pulls, logged in this repo | Open (roadmap) |
| R-07 | Travel VPN client | Weak or crowded venue Wi-Fi adds jitter and drops the tunnel during calls | 3 | 1 | 3 | Mitigate | Use a wired Ethernet port at the venue when one exists. Keep a phone hotspot as the backup uplink for the travel router | Open |
| R-08 | Homelab services | Web admin panels for AdGuard, Jellyfin, n8n, and Uptime Kuma are reachable from any device on the home LAN | 2 | 2 | 4 | Mitigate | Strong unique passwords on every panel, review exposed ports, run a Lynis audit and publish results | Open (roadmap) |
| R-09 | Travel VPN client | Traffic leaks onto public Wi-Fi through IPv6 or a dropped tunnel | 1 | 3 | 3 | Mitigate | Kill switch on, IPv6 off, IPv6 endpoint removed. Verified with a cellular test | Mitigated |

## Change log

| Date | Change |
|------|--------|
| 2026-10 | First version of the register, covering Projects 01 and 02 |
