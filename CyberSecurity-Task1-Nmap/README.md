# Task 1 – Basic Network Scanning with Nmap

## Task Objective

The objective of this task is to perform a basic network scan using Nmap on an authorized local/private system, identify open ports and services, and analyze the security implications of the scan results.

## Tool Used

- Nmap 7.991
- Windows PowerShell

## What is Nmap?

Nmap (Network Mapper) is an open-source network scanning tool used to discover hosts and services on a computer network. It can identify open ports, running services, service versions, and operating system information.

## Why Network Scanning Matters

Network scanning helps security professionals:

- Identify open ports and exposed services.
- Discover unnecessary network services.
- Determine service versions.
- Identify potential security risks.
- Understand the attack surface of a system.

## Installation

Nmap was installed on the Windows system.

After installation, the installation was verified using:

```powershell
nmap --version
```

The installed version used for this task was:

**Nmap 7.991**

## Ethical Use and Authorization

Network scanning should only be performed on systems that you own or have explicit permission to test.

For this task, the scan was performed against an authorized private/local IP address. External or production systems were not scanned.

## Target

**Target IP:** `10.38.156.240`

## Scans Performed

### 1. Basic Network Scan

Command:

```powershell
nmap -Pn 10.38.156.240
```

The basic scan identified the following open TCP ports:

- **135/tcp — msrpc**
- **139/tcp — netbios-ssn**
- **445/tcp — microsoft-ds**

### 2. Service Version Detection

Command:

```powershell
nmap -Pn -sV 10.38.156.240
```

Service version detection identified:

- **135/tcp — msrpc — Microsoft Windows RPC**
- **139/tcp — netbios-ssn — Microsoft Windows netbios-ssn**
- **445/tcp — microsoft-ds**

The scan also identified the operating system family as Microsoft Windows.

### 3. Operating System Detection

Command:

```powershell
nmap -Pn -O 10.38.156.240
```

The OS detection scan identified:

- **Device type:** General purpose
- **Running:** Microsoft Windows 11
- **OS details:** Microsoft Windows 11 24H2–25H2

## Scan Findings

The Nmap scans identified three open TCP ports:

| Port | State | Service | Security Analysis |
|------|-------|---------|-------------------|
| 135/tcp | Open | MSRPC | Windows RPC can expose remote procedure call functionality and should be restricted to trusted networks. |
| 139/tcp | Open | NetBIOS-SSN | NetBIOS over TCP can expose Windows file and network-sharing functionality and should not normally be exposed to untrusted networks. |
| 445/tcp | Open | Microsoft-DS / SMB | SMB is used for Windows file and printer sharing. Unnecessary exposure can increase the attack surface and should be restricted using firewall rules and network segmentation. |

The scans also showed that most other scanned TCP ports were closed or filtered.

## Security Analysis

The three open ports identified are commonly associated with Windows networking:

### Port 135 – MSRPC

Port 135 is associated with Microsoft RPC services.

**Security concern:** If unnecessarily exposed to untrusted networks, RPC services can increase the attack surface.

**Recommended protection:**
- Restrict access using Windows Firewall.
- Allow RPC only from trusted networks or systems.
- Keep Windows fully patched.

### Port 139 – NetBIOS-SSN

Port 139 is associated with NetBIOS Session Service and legacy Windows networking.

**Security concern:** Exposure can reveal Windows networking information and increase the attack surface.

**Recommended protection:**
- Disable NetBIOS where it is not required.
- Restrict port 139 using firewall rules.
- Avoid exposing it directly to the public Internet.

### Port 445 – Microsoft-DS / SMB

Port 445 is commonly used for SMB file and printer sharing.

**Security concern:** SMB exposure has historically been associated with serious security vulnerabilities and unauthorized network access.

**Recommended protection:**
- Restrict SMB access to trusted networks.
- Keep Windows and SMB-related components patched.
- Block unnecessary inbound SMB traffic at network boundaries.

## Screenshots

The following screenshots document the scans performed:

1. `01_basic_scan.png` – Basic Nmap scan showing open ports
2. `02_service_version.png` – Service version detection
3. `03_os_detection.png` – OS detection

## Scan Results

The complete terminal results are available in:

`nmap_scan_results.txt`

## Conclusion

Nmap was successfully used to perform basic network, service-version, and OS-detection scans against an authorized private/local target.

The scan identified three open TCP ports: **135, 139, and 445**, which are associated with Windows networking services. These services should be appropriately restricted and protected because unnecessary exposure can increase the system's attack surface.

The scan also identified the target as **Microsoft Windows 11**. Network scanning is an important security assessment technique because it helps identify exposed services and understand potential security risks. Scans should always be performed with proper authorization.
