# T1016 – Network Configuration Discovery
Collect network interface, routing, and DNS information to map environment.

### 🧰 Commands
`ipconfig /all`, `route print`, `arp ‑a`, `Get-NetIPConfiguration`
or in Linux: `ifconfig -a`, `ip addr`, `netstat ‑rn`

### ✅ Checklist
1. Gather local IP ranges and gateways.  
2. Identify DNS servers, DHCP ranges.  
3. Discover proxy configs and split tunnels.  
4. Save for pivot / routing planning.

### ⚕ Detection
| Source | Indicator |
|---------|-----------|
| Sysmon 1 | unusual script collecting `ipconfig` |
| Sigma | `network_enum_script.yml` |


Author : yasinabedini
GitHub : https://github.com/yasinabedini

