---
title: "AWS Network Security & Architecture Workshop"
date: "`r Sys.Date()`"
weight: 4
chapter: false
pre: " <b> 4.4.</b> "
---
### Event Objectives

- Understand the differences between MFA technologies (TOTP vs. FIDO2).
- Identify common network attack vectors (Ingress, Egress, and Inside attacks).
- Learn how to implement multilayer security using AWS services like WAF, Shield, Network Firewall, and Security Groups.
- Design "Good" traffic flows using Transit Gateways and centralized egress points.

### Speakers

### Key Highlights

#### Multi-Factor Authentication (MFA) Evolution

- **TOTP (Time-based One-Time Password)**: Relies on a shared secret and requires manually typing a 6-digit code. It is free and offers flexible backups.
- **FIDO2**: Utilizes public-key cryptography and requires a simple touch or biometric scan. It supports variable authenticators and enforces strict backups.

#### Understanding Attack Vectors

- **Ingress Attacks**: Threats entering from the internet, such as DDoS attacks, Application attacks (SQL injection, XSS), and Bot activities.
- **Inside Attacks**: Threats within the network, including lateral movement between services and malware spread.
- **Egress Attacks**: Threats attempting to leave the network, such as DNS tunneling or data exfiltration.

#### Defense in Depth (Multilayer Security)

- **Edge Protection**: Use **CloudFront, WAF, and Shield** for DDoS prevention, application firewalls, bot control, and fraud detection.
- **Network & Resource Control**: Implement **Security Groups & NACLs** for resource-level and network-level control against lateral movement.
- **East-West Traffic**: Use **Network Firewalls** (IPS/IDS) to control traffic flow between VPCs.
- **DNS Security**: Implement **Route 53 DNS Firewall** for domain filtering and blocking malicious site access.

#### Architecture & Traffic Flow

- **Traffic Routing**: Utilizing **Transit Gateway** with routing segments to manage complex connections between Production and Project VPCs.
- **Centralized Egress**: establishing a "Central Internet Egress" VPC to filter and monitor all outbound traffic via a Web Proxy or Firewall.
- **Segmentation**: Separating environments (e.g., Prod, Project A, Project B) into distinct subnets (Web/App, DB) to contain potential breaches.

### Key Takeaways

#### Security Strategy

- **Layered Defense**: Security must be applied at multiple layers—Edge, Network, and Host—to effectively mitigate different types of attack vectors.
- **Identity First**: Move towards stronger authentication methods like FIDO2 for better security and user experience compared to traditional TOTP.

#### Architectural Best Practices

- **Centralization**: Use Transit Gateways to centralize routing and simplify network management across multiple VPCs.
- **Visibility**: Implementing specific controls like DNS Firewalls and Network Firewalls provides visibility into internal (East-West) and outbound traffic, not just incoming requests.

### Applying to Work

- **Review MFA Policy**: Evaluate the feasibility of moving from TOTP to FIDO2 hardware keys or biometrics for privileged accounts.
- **Audit Security Groups**: Review current Security Groups and NACLs to ensure they are strictly defined to prevent lateral movement.
- **Implement WAF**: Deploy AWS WAF on public-facing Application Load Balancers (ALB) or API Gateways to block common web exploits.
- **Network Segmentation**: Assess the current VPC architecture and consider implementing a Transit Gateway if managing multiple VPCs to ensure "good" traffic flow.

### Event Experience

Attending the **“AWS Network Security & Architecture”** workshop provided a clear visual guide to securing cloud infrastructure. Key experiences included:

#### Visualizing Security Layers

- The diagrams clearly illustrated how different AWS services (WAF, Shield, Network Firewall) map to specific attack vectors like DDoS or SQL injection.
- It was valuable to see the distinction between guarding against "Ingress" attacks versus "Inside" lateral movements.

#### Understanding Modern Auth

- The direct comparison between TOTP and FIDO2 highlighted the trade-offs between convenience (touch/biometric) and traditional methods (typing codes).

#### Architecture Deep Dive

- Seeing the "Good Traffic Flows" diagram helped clarify how to architect a production-grade network using Transit Gateways and centralized internet egress points.

