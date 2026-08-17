# 🔥 Iran Firewall Manager

<!-- repo-badges:start -->
<p align="center">
  <a href="https://hits.sh/github.com/power0matin/Iran-Firewall-Manager/"><img src="https://hits.sh/github.com/power0matin/Iran-Firewall-Manager.svg?style=flat-square&amp;label=Views&amp;labelColor=18181B&amp;color=0EA5E9&amp;logo=github" alt="Repository Views"/></a>
  <a href="https://github.com/power0matin/Iran-Firewall-Manager/stargazers"><img src="https://img.shields.io/github/stars/power0matin/Iran-Firewall-Manager?style=flat-square&amp;label=Stars&amp;labelColor=18181B&amp;color=F59E0B&amp;logo=github&amp;logoColor=white" alt="GitHub Stars"/></a>
  <a href="https://github.com/power0matin/Iran-Firewall-Manager/forks"><img src="https://img.shields.io/github/forks/power0matin/Iran-Firewall-Manager?style=flat-square&amp;label=Forks&amp;labelColor=18181B&amp;color=6366F1&amp;logo=github&amp;logoColor=white" alt="GitHub Forks"/></a>
  <a href="https://github.com/power0matin/Iran-Firewall-Manager/issues"><img src="https://img.shields.io/github/issues/power0matin/Iran-Firewall-Manager?style=flat-square&amp;label=Issues&amp;labelColor=18181B&amp;color=22C55E&amp;logo=github&amp;logoColor=white" alt="GitHub Issues"/></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/power0matin/Iran-Firewall-Manager?style=flat-square&amp;label=License&amp;labelColor=18181B&amp;color=EF4444&amp;logo=github&amp;logoColor=white" alt="GitHub License"/></a>
</p>
<!-- repo-badges:end -->

## [🇮🇷 مشاهده نسخه فارسی](README.fa.md)

An **interactive and secure Bash script** to harden Iranian servers by strictly controlling which IPs and ports are allowed — ideal for tunneling setups.

> ✅ Tailored for tunnels like **Rathole v2**, **Backhaul**, **Xray**, or private proxy systems.


## 🛡️ Key Features

* ❌ Block all traffic (inbound & outbound) by default
* 🌍 Allow only specific ports from a **foreign (non-Iranian)** server IP
* 🔕 Disable ICMP (ping) to avoid discovery
* 💾 Auto-save rules via `iptables-persistent`
* 🔁 One-click **reset** to default open state
* 📱 Interactive emoji-powered menu — no manual editing
* 🔐 TCP / UDP / Both rule support
* 🧠 Remembers last used IP & ports
* 🧪 Ping test to verify foreign IP reachability
* 📋 View open ports and allowed IPs
* ✅ All interactive — no manual iptables usage required


## 🚀 One-Line Install & Run

Install the **latest enhanced version (v2)**:

```bash
bash <(curl -Ls https://raw.githubusercontent.com/power0matin/Iran-Firewall-Manager/main/firewall-manager-v2.sh)
```

> ✅ Includes full menu, UDP support, persistent config, and port visibility.

### 🧪 Legacy Version (Minimal)

For the original minimal script:

```bash
bash <(curl -Ls https://raw.githubusercontent.com/power0matin/Iran-Firewall-Manager/main/firewall-manager.sh)
```

> ⚠️ No menu, memory, or advanced options.


## 📦 Example Output

```bash
[*] Installing iptables-persistent...
[*] Flushing existing firewall rules...
[*] Allowing localhost traffic...
[*] Allowing SSH on port 22...
[*] Applying rules for IP 1.2.3.4 and allowed ports...
  - Allowing TCP port 443 from 1.2.3.4
  - Allowing UDP port 443 from 1.2.3.4
[*] Setting default policy to DROP...
[*] Disabling ICMP echo (ping)...
[*] Saving iptables rules...
[✅] Firewall rules applied successfully.
```


## 📋 Menu Options

```
====== Firewall Management Menu ======
1) Apply secure firewall restrictions
2) Reset firewall to open state
3) Show currently open ports
4) Enable secure mode (allow only selected IP and ports)
0) Exit
```


## ⚠️ Warnings

> 🛑 **Double-check the IP** before applying rules — wrong IP may **lock you out via SSH**.
> 🧠 If you need DNS/NTP or other system ports, add them manually:

```bash
iptables -A OUTPUT -p udp --dport 53 -j ACCEPT  # DNS
iptables -A OUTPUT -p udp --dport 123 -j ACCEPT # NTP
```

> 📡 UDP is fully supported in interactive mode. Choose `TCP`, `UDP`, or `Both`.


## 🧱 Project Roadmap

| Phase          | Status      | 🔧 Planned Features                                                         | ✅ Details                                                     |
| -------------- | ----------- | --------------------------------------------------------------------------- | ------------------------------------------------------------- |
| 🟢 **Phase 1** | ✅ Complete  | 🔒 Basic TCP rules<br>🌐 IP allowlist<br>🚫 Default deny                    | Base implementation, save support, basic menu                 |
| 🟡 **Phase 2** | 🔛 Current  | 📱 Menu rework<br>📦 UDP support<br>🧠 Config memory<br>🖥️ Port visibility | Full rework with usability in mind                            |
| 🟠 **Phase 3** | 🔜 Soon     | ⏱️ Auto-revert fail-safe<br>🧪 Config profiles<br>🌗 Day/Night modes        | Prevent lockout, switch between profiles, time-based policies |
| 🔵 **Phase 4** | ⏳ Planned   | 🌍 GeoIP blocking<br>📅 Cron apply/reset<br>💬 Language menu (EN/FA)        | Auto-rules by schedule and region, multilingual               |
| 🟣 **Phase 5** | 🧠 Advanced | 📊 Traffic monitor<br>🚨 Telegram alerts<br>📥 External logging             | Monitor usage, notify intrusions, log centralization          |
| 🟤 **Phase 6** | 🧪 Future   | 🐳 Docker-aware firewall<br>🔗 API interface<br>👥 Multi-admin logs/audits  | Integration with containers and dashboards                    |

> 🔧 **Current Phase:** `Phase 2` — usability improvements, UDP support, and config memory.
> 💡 Got a feature idea? [Open an Issue](https://github.com/power0matin/Iran-Firewall-Manager/issues)


## ⚙️ Requirements

* ✅ Ubuntu or Debian-based system
* 🧑‍💻 Root privileges
* 📦 `iptables`, `iptables-persistent` (auto-installed)


## ✅ Tested On

* Ubuntu 20.04 / 22.04
* Debian 11 / 12
* VPS: KVM, NAT, OpenVZ (IPv4 only)


## 📄 License

[MIT License](LICENSE) — free for personal and commercial use.


## ✨ Author

Built with ❤️ by [**power0matin**](https://github.com/power0matin)
⭐ If you find it useful, please star the repo and share it 🙌

## 📬 Contact

**Matin Shahabadi (متین شاه‌آبادی / متین شاه آبادی)**

* Website: [matinshahabadi.ir](https://matinshahabadi.ir)
* Email: [me@matinshahabadi.ir](mailto:me@matinshahabadi.ir)
* GitHub: [power0matin](https://github.com/power0matin)
* LinkedIn: [matin-shahabadi](https://www.linkedin.com/in/matin-shahabadi)
