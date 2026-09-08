# Common Network Security Threats

## Introduction

Network security threats are malicious activities or attacks that can compromise the confidentiality, integrity, or availability of systems, networks, and data. As organizations increasingly depend on connected systems and online services, protecting networks from common threats is an important part of cybersecurity.

Network attacks can target communication channels, network infrastructure, services, or users. Understanding how these attacks work, their potential impact, and the appropriate security controls helps organizations reduce their exposure to cyber risks.

This report focuses on three common network security threats:

- Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS)
- Man-in-the-Middle (MITM) attacks
- IP Spoofing

DNS Poisoning/Spoofing is also discussed as an additional network security threat.
## 1. Denial-of-Service (DoS) and Distributed Denial-of-Service (DDoS)

### How It Works

A Denial-of-Service (DoS) attack attempts to make a system, server, or network service unavailable to legitimate users by overwhelming it with excessive requests or traffic. A Distributed Denial-of-Service (DDoS) attack uses multiple compromised devices, often called a botnet, to generate traffic from many sources simultaneously.

The large volume of requests or traffic can consume network bandwidth, processing power, memory, or other system resources. As a result, legitimate users may experience slow performance or complete service unavailability.

### Real-World Example

A well-known example of a DDoS attack is the 2016 Mirai botnet attack. Mirai compromised vulnerable Internet of Things (IoT) devices such as cameras and routers and used them to generate large-scale traffic against targeted services. The attack demonstrated how insecure connected devices can be combined to create a powerful distributed attack.

### Impact

DoS and DDoS attacks can have several negative effects:

- Website and service downtime.
- Loss of availability for legitimate users.
- Business and financial losses.
- Damage to an organization's reputation.
- Increased operational and incident-response costs.

### Mitigation Techniques

Organizations can reduce the risk and impact of DoS/DDoS attacks through the following measures:

1. **Traffic filtering:** Use firewalls, access-control rules, and filtering systems to identify and block malicious or abnormal traffic.
2. **Rate limiting:** Limit the number of requests accepted from individual sources to prevent resource exhaustion.
3. **DDoS protection services:** Use traffic-monitoring and mitigation services designed to detect and absorb large-scale malicious traffic before it reaches critical systems.
## 2. Man-in-the-Middle (MITM) Attack

### How It Works

A Man-in-the-Middle (MITM) attack occurs when an attacker secretly intercepts communication between two parties. The attacker may monitor, modify, or redirect the communication while making the participants believe they are communicating directly with each other.

MITM attacks can occur on insecure or compromised networks, particularly when communication is not properly encrypted or when users connect to untrusted Wi-Fi networks.

### Real-World Example

A common example is an attacker creating or compromising a public Wi-Fi network and intercepting users' network traffic. If a user accesses services without adequate encryption or certificate validation, sensitive information such as login credentials or session data may be exposed.

### Impact

MITM attacks can result in:

- Theft of login credentials and sensitive information.
- Interception of confidential communications.
- Modification of data during transmission.
- Session hijacking.
- Privacy and financial losses.

### Mitigation Techniques

1. **Use encrypted communication:** Use HTTPS, TLS, and other secure protocols to protect data while it is being transmitted.
2. **Use secure networks:** Avoid connecting to unknown or untrusted Wi-Fi networks and use a trusted VPN when appropriate.
3. **Verify certificates and authentication:** Proper certificate validation and strong authentication mechanisms help prevent attackers from impersonating legitimate services.
