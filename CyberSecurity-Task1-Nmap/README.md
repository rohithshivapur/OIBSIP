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

Purpose:

The basic scan was used to check the target for commonly scanned TCP ports.

### 2. Service Version Detection

Command:

```powershell
nmap -Pn -sV 10.38.156.240
```

Purpose:

The `-sV` option attempts to identify the services and their versions running on open ports.

### 3. Operating System Detection

Command:

```powershell
nmap -Pn -O 10.38.156.240
```

Purpose:

The `-O` option attempts to identify the operating system of the target host.

## Scan Findings

The scans produced the following results:

- Target host was detected as up.
- 1000 TCP ports were scanned.
- No open TCP ports were identified in the scanned ports.
- Most ports were filtered and did not respond.
- Service version detection did not identify any exposed TCP services.
- OS detection was inconclusive because Nmap received insufficient information to provide a specific operating-system fingerprint.

### Port and Service Analysis

| Port | State | Service | Security Analysis |
|------|-------|---------|-------------------|
| No open ports identified | — | No exposed TCP service detected | No directly exposed TCP service was observed during the scan |

Since no open TCP ports were identified, there were no exposed services that could be individually assessed for service-specific vulnerabilities.

## Security Analysis

The scan did not identify any open TCP ports on the target within the scanned port range.

This reduces the directly observable TCP attack surface from the perspective of this scan. However, security cannot be determined from a single Nmap scan alone.

Possible reasons for the filtered results include:

- Firewall rules.
- Network filtering.
- Host-based security controls.
- Services not listening on the scanned TCP ports.

The OS detection result was inconclusive, so no specific operating system was assumed from the scan.

## Screenshots

The following screenshots document the scans performed:

1. `01_basic_scan.png` – Basic Nmap scan
2. `02_service_version.png` – Service version detection
3. `03_os_detection.png` – OS detection

## Scan Results

The complete terminal results are available in:

`nmap_scan_results.txt`

## Conclusion

Nmap was successfully used to perform basic network, service-version, and OS-detection scans against an authorized private/local target.

The scan identified no open TCP ports in the scanned range and therefore no exposed TCP services requiring service-specific security analysis.

Network scanning is an important security assessment technique because it helps identify exposed services and understand a system's attack surface. However, scans should always be performed with proper authorization and should be combined with other security assessment techniques for a complete security evaluation.
