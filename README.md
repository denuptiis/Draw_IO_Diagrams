# Draw.io Network Diagrams

A collection of [draw.io / diagrams.net](https://www.diagrams.net/) diagrams covering
home-lab and small-business infrastructure: pfSense and OPNsense firewalls, VLAN
segmentation, UniFi, overlay VPNs (Tailscale, WireGuard, OpenVPN, IPsec), XCP-ng and
Xen Orchestra, ZFS and TrueNAS storage, and a few workflow diagrams.

All files are stored as uncompressed `.drawio` XML so that diffs are readable in Git.

## Opening and editing

- **Desktop app**: install [draw.io Desktop](https://github.com/jgraph/drawio-desktop/releases)
  and open any `.drawio` file directly.
- **Browser**: go to <https://app.diagrams.net>, choose *Open Existing Diagram* and point it at
  GitHub, or drag a downloaded file into the page.
- **VS Code**: the [Draw.io Integration](https://marketplace.visualstudio.com/items?itemName=hediet.vscode-drawio)
  extension renders and edits `.drawio` files in the editor.

To keep diffs useful, leave *File > Properties > Compressed* unchecked when saving.

## Diagram index

| File | Pages | What it shows |
| --- | ---: | --- |
| [`Bitwarden_Layout.drawio`](Bitwarden_Layout.drawio) | 2 | How Bitwarden objects relate: users, personal vaults, folders, items, organizations, collections, and groups. |
| [`DNS_Cert_Troubleshooting.drawio`](DNS_Cert_Troubleshooting.drawio) | 3 | Name resolution and certificate path for a service behind pfSense HAProxy, split into internal-IP and external views, with the TLD / domain / subdomain breakdown. |
| [`Dual_WAN_Routing.drawio`](Dual_WAN_Routing.drawio) | 1 | pfSense with two ISPs on WAN and WAN2 and a LAN client, used to explain multi-WAN routing and how to check the egress IP. |
| [`Editing_Workflow.drawio`](Editing_Workflow.drawio) | 1 | 2023 content production workflow: cameras, OBS studio machine, TrueNAS storage, and the DaVinci Resolve editing workstation. |
| [`GrayLog.drawio`](GrayLog.drawio) | 1 | Graylog message pipeline: input port and type, extractors, parsed fields, stream rules, and index routing. |
| [`HA_Proxy_pfsense.drawio`](HA_Proxy_pfsense.drawio) | 12 | pfSense HAProxy reverse proxy publishing TrueNAS and Uptime Kuma on port 443, with public and private DNS variants. Also carries the full set of traditional VPN vs. overlay network pages (see TailScale_Demo). |
| [`OPNsense_Captive_Portal.drawio`](OPNsense_Captive_Portal.drawio) | 2 | OPNsense guest network with a captive portal on an isolated VLAN: topology with firewall rules per zone, and the client authentication flow from SSID join through redirect, login, session, and timeout. Includes a setup checklist. |
| [`Storage_Design_2023.drawio`](Storage_Design_2023.drawio) | 7 | Storage architecture options: Xen Orchestra with local NAS, Windows Server file services with and without a NAS, virtualized AD with a separate storage network, iSCSI to a Windows hypervisor, and iSCSI / NFS to Docker or VMs. |
| [`TailScale_Demo.drawio`](TailScale_Demo.drawio) | 9 | Traditional VPN (OpenVPN, IPsec, WireGuard) compared with overlay networks. Step-by-step pages on how a coordination server brokers connections, Tailscale on pfSense, TrueNAS Scale on Tailscale, and a lab with cloud and local Debian nodes. |
| [`UniFI_Magic_site-site-july-2023.drawio`](UniFI_Magic_site-site-july-2023.drawio) | 2 | UniFi Site Magic site-to-site VPN between a UniFi gateway and another firewall, each with its own network, coordinated through the UniFi cloud portal. |
| [`UniFi_Managemend_VLAN_Demo.drawio`](UniFi_Managemend_VLAN_Demo.drawio) | 2 | Dedicated UniFi management VLAN (VLAN 777) with a remotely hosted controller, SSID to VLAN tagging, switch port profiles, and a threats page showing what a flat network exposes. |
| [`Untitled Diagram.drawio`](Untitled%20Diagram.drawio) | 1 | The stock draw.io Azure template with placeholder text. Committed as part of a GitHub workflow demo, not an infrastructure design. |
| [`VLAN_Security_2022.drawio`](VLAN_Security_2022.drawio) | 16 | VLAN security walkthrough on pfSense and UniFi: tagged SSIDs, port profiles, the threat model, plus XCP-ng storage and backup pages and a side-by-side of Tailscale, WireGuard, OpenVPN, and IPsec for devices and site-to-site. |
| [`Xen_Orchestra_Backups.drawio`](Xen_Orchestra_Backups.drawio) | 6 | Xen Orchestra backup architecture: pools and hosts, NFS and S3 remotes, shared storage for HA pools, XO Proxy for off-site hosts over VPN, and backup data flow between two sites. |
| [`ZFS_Layout.drawio`](ZFS_Layout.drawio) | 4 | ZFS pool anatomy: data VDEVs (RAIDZ1/2/3 and mirrors), LOG, cache, dedup, metadata special VDEVs, hot spares, datasets and ZVOLs, with a storage efficiency comparison. |
| [`pfsense_UniFi_VLAN_2022.drawio`](pfsense_UniFi_VLAN_2022.drawio) | 4 | pfSense and UniFi VLAN demo: before (flat network) and after (VLAN 60 and VLAN 777) with switch port profiles across two switches. |

## Conventions used in these diagrams

- Dark teal page background (`#114B5F`) with white or light green text.
- Red links for WAN, green for trusted LAN, orange for guest or restricted segments.
- Network shapes come from the built-in `mxgraph.networks` and Cisco stencil libraries.
- Multi-page files use one page per scenario so a single file can tell a before/after story.
