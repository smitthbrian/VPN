# Remote Access VPN & Network Defense with pfSense

This project demonstrates how to implement a secure remote access VPN using **pfSense** and **OpenVPN**, with layered internal and external access control policies to enhance overall network security. Designed as part of an Ethical Hacking & Countermeasures curriculum, the project integrates defense-in-depth strategies for both endpoint and network protection.

## 🛡️ Objectives

- Deploy a secure Remote Access VPN.
- Implement layered access control mechanisms to limit internal lateral movement.
- Configure firewall rules, subnet design, certificate-based authentication, and client VPN access.
- Demonstrate protected resource access pre- and post-VPN connection.

## 🧱 Technologies Used

- **pfSense**
- **OpenVPN**
- **802.1X / MAC Filtering / VLANs**
- **RBAC (Role-Based Access Control)**
- **IDS/IPS / Next-Gen Firewall**
- **Azure VM (for remote simulation)**

## 🔐 Key Features

- **VPN Gateway Setup**: Configured OpenVPN on pfSense with TLS authentication and per-user certificates.
- **Access Control Design**:
  - Internal: VLANs, ACLs, MAC filtering, RBAC.
  - External: Firewall rules, IDS/IPS, DDoS mitigation.
- **Certificate Authority**: Created self-signed CA to issue and manage user-specific certs.
- **Client Export**: Enabled users to connect remotely via exported OpenVPN config with cert binding.
- **Shared Resource Demo**: Demonstrated secure access to internal file shares only while VPN is active.

## 📸 Demo Snapshots

| Feature                            | Screenshot Description                         |
|-----------------------------------|------------------------------------------------|
| VPN User Creation                 | Cert-bound OpenVPN user (e.g., johndoe)        |
| pfSense Firewall Rules            | Rules for VPN (1194 UDP) and local LAN access  |
| Shared Folder Access (No VPN)     | Port 445 blocked, access denied                |
| Shared Folder Access (With VPN)   | Access to `\\192.168.1.10\cis` granted         |

## 🔄 Policy Enforcement

- **Network Access Control (NAC)** used to enforce posture validation and endpoint compliance.
- **Dynamic Policy Application** via firewall and pfSense role bindings.
- **Split Tunneling** selectively routes traffic based on internal needs.

## ✅ Outcomes

- Hardened internal network segmentation.
- Prevented unauthorized lateral movement.
- Enabled secure off-site resource access.
- Enforced user/device validation before connection.

---

📁 _Project completed as part of Appalachian State University's Ethical Hacking course._

