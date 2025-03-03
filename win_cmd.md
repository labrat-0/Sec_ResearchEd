# 🖥️ Windows Command Prompt & Report Generation Cheat Sheet

> **A comprehensive guide to Windows commands and their corresponding reports for troubleshooting and system analysis.**

---

## 🔧 **Windows Commands**

| **Command** | **Example Use Case** | **Icon** |
|-------------|----------------------|----------|
| `ipconfig` | Display basic IP configuration | 🌐 |
| `ipconfig /all` | Show detailed network adapter information | 📡 |
| `findstr` | Search for a string in output or a file | 🔍 |
| `ipconfig /release` | Release current IP address | 🔄 |
| `ipconfig /renew` | Request a new IP address | 🔄 |
| `ipconfig /displaydns` | Show DNS cache entries | 📜 |
| `clip` | Copy output to clipboard | 📋 |
| `ipconfig /flushdns` | Clear DNS resolver cache | 🧹 |
| `nslookup` | Query DNS records | 📖 |
| `cls` | Clear the command prompt screen | ❌ |
| `getmac /v` | Display MAC addresses with details | 🖥️ |
| `powercfg /energy` | Generate an energy report | ⚡ |
| `powercfg /batteryreport` | Generate a battery health report | 🔋 |
| `assoc` | Display or change file associations | 📂 |
| `chkdsk /f` | Check disk for errors and fix them | 🛠️ |
| `chkdsk /r` | Check for bad sectors and recover readable data | 🔍 |
| `sfc /scannow` | Scan and repair system files | 🔧 |
| `DISM /Online /Cleanup-Image /CheckHealth` | Check Windows image health | 🏗️ |
| `tasklist` | List running processes | 📋 |
| `taskkill` | Terminate a process by PID or name | ❌ |
| `ping` | Test network connectivity | 🌐 |
| `tracert` | Trace network route to a host | 🛤️ |
| `shutdown /r /fw /f /t 0` | Restart the PC and enter firmware settings | 🔄 |

---

## 📊 **Windows Reports for Troubleshooting**

| **Command** | **Report Type** | **File Output** | **Icon** |
|-------------|------------------|------------------|----------|
| `powercfg /energy` | ⚡ Power efficiency & issues | `energy-report.html` | ⚡ |
| `powercfg /batteryreport` | 🔋 Battery health & usage | `battery-report.html` | 🔋 |
| `netsh wlan show wlanreport` | 📡 Wi-Fi connectivity analysis | `wlan-report.html` | 📡 |
| `chkdsk /f` | 🛠 Disk health check | `chkdsk-report.html` | 🛠️ |
| `sfc /scannow` | 🔧 System file integrity check | Event Log | 🔧 |
| `DISM /Online /Cleanup-Image /ScanHealth` | 🏗 Windows image health | Event Log | 🏗️ |
| `tasklist` | 🏗 Running processes | `tasklist.html` | 📋 |
| `wevtutil qe Security /c:1000 /rd:true /f:html > security-log.html` | 🔐 Security event logs | `security-log.html` | 🔐 |

---

## 🚀 **Automate Report Generation (PowerShell)**

> **Generate multiple reports at once and save them to a folder.**

```powershell
$OutputPath = "C:\Reports"
New-Item -ItemType Directory -Path $OutputPath -Force

powercfg /energy /output "$OutputPath\energy-report.html"
powercfg /batteryreport /output "$OutputPath\battery-report.html"
netsh wlan show wlanreport > "$OutputPath\wlan-report.html"
wmic diskdrive get model, status > "$OutputPath\disk-health.html"

Write-Host "Reports saved in $OutputPath"
```

--- 
