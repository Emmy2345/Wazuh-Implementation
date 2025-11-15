# 🛡️ Home SIEM Lab: Wazuh on VMware Workstation Pro

This repository documents the setup and configuration of a Security Information and Event Management (SIEM) environment using **Wazuh** hosted on two Ubuntu Virtual Machines (VMs) within **VMware Workstation Pro**.

This project demonstrates core Blue Team skills in environment setup, log collection, centralized monitoring, and security incident response.

---

## 🚀 Project Components

The lab environment consists of two primary Virtual Machines (VMs), both running **Ubuntu 24.04 LTS**:

1.  **Wazuh Server (Admin/Manager):** This VM hosts the core Wazuh Manager and the Wazuh Indexer (for data storage and search), along with the Wazuh Dashboard (based on OpenSearch) for visualization and analysis.
2.  **Wazuh Agent (User/Target):** This VM acts as the **monitored endpoint**. It has the Wazuh Agent installed to collect system logs, file integrity monitoring (FIM) events, and security data, forwarding them to the Wazuh Server.

### Technical Stack

| Component | Role | Details |
| :--- | :--- | :--- |
| **Hypervisor** | Virtualization | VMware Workstation Pro |
| **Operating System** | Base OS for VMs | **Ubuntu 24.04 LTS** |
| **SIEM Tool** | Centralized Security | **Wazuh** (Manager, Indexer, Dashboard, Agents) |
| **Networking** | Connectivity | Internal/Host-Only Network to isolate the lab |

---

## 🛠️ Setup & Implementation Steps

The following steps were executed to bring the SIEM environment online:

### 1. Virtual Machine Provisioning

* **VM Creation:** Created two VMs using the Ubuntu ISO disk images within VMware Workstation Pro.
* **Network Configuration:** Configured both VMs to operate on a **Host-Only or Custom Internal Network** to isolate them from the main home network, ensuring security testing remains contained.
* **Resource Allocation:** Assigned sufficient resources (e.g., 4 CPU cores, 8GB+ RAM, 100GB+ disk) to the **Wazuh Server** VM to handle indexing and dashboard operations.

### 2. Wazuh Manager Installation (Admin VM)

* Installed the **Wazuh Indexer**, **Wazuh Server (Manager)**, and **Wazuh Dashboard** components on the Admin VM following the official Wazuh documentation.
* Verified the status of all services (`systemctl status wazuh-manager`, `systemctl status opensearch`, etc.) to ensure the core monitoring platform was operational.
* Accessed the Wazuh Dashboard via the browser to confirm the graphical interface was functional.

### 3. Wazuh Agent Deployment (User VM)

* Downloaded and installed the appropriate Wazuh Agent package onto the User VM.
* **Agent Enrollment:** Configured the Agent to securely connect and enroll with the Wazuh Manager using the Manager's internal IP address.
* Verified the Agent connection status within the Wazuh Dashboard (under the **Agents** section).

---

## ✅ Key Achievements & Demonstrable Skills

### A. Centralized Monitoring & Visualization
Successfully deployed the Wazuh Dashboard (based on OpenSearch) to provide a centralized view of security events and activity across the network.

### Wazuh Dashboard Overview <img width="1916" height="1075" alt="Wizah_Dashboard" src="https://github.com/user-attachments/assets/71ce4113-6977-4be7-a3e6-4809d1204e2b" />
<p align="center">Wazuh Dashboard Overview: General alerts, events, and agent status visualization.</p>

### Wazuh Secondary Dashboard View <img width="1913" height="1071" alt="Wizah_Project2" src="https://github.com/user-attachments/assets/8ea4cab3-af3b-44d1-84a3-ead8b33b094c" />
<p align="center">Wazuh Secondary Dashboard: Highlighting overall security posture and metrics.</p>

---

### B. Security Event Detection
Used Wazuh to actively monitor and detect suspicious activity on the target endpoint. This screenshot shows the detection of a high-severity event on the Ubuntu User VM.

### Wazuh Privilege Escalation Attempt Alert <img width="1910" height="1073" alt="Wizah_Project" src="https://github.com/user-attachments/assets/811f5eef-62b2-4dcb-a42e-a4f866bbd6fd" />
<p align="center">Wazuh Alert Detail: High-severity alert triggered by a privilege escalation attempt (e.g., failed `sudo` command) on the User VM.</p>

* **Log Ingestion:** Established reliable, real-time log forwarding from a target endpoint (User VM) to the centralized SIEM Server.
* **Log Analysis:** Analyzed raw log data within the platform to investigate and triage events.

### Wazuh Logs Detail View <img width="1907" height="1061" alt="Wizah_Project3" src="https://github.com/user-attachments/assets/894d259e-c18a-4283-b61e-051736b0dbdb" />
<p align="center">Raw Log Data View: Inspecting the full event log detail for forensic analysis.</p>

---

### C. Configuration and Compliance Assessment
Utilized Wazuh's capabilities to run compliance checks and assess the configuration of the monitored system, verifying security posture against established benchmarks.

### Wazuh Configuration Assessment Window <img width="1912" height="1069" alt="Wizah_ConfigurationAssessment" src="https://github.com/user-attachments/assets/1a147617-2f57-4225-9de3-fdb03b796df0" />
<p align="center">Security Configuration Assessment (SCA): Showing results of compliance checks on the monitored Ubuntu Agent.</p>

* **Environment Setup:** Successfully built and segmented a functional, multi-node virtual lab environment using enterprise-grade hypervisor software.
* **Rule Creation & Alerting:** *[Optional: Add a specific rule you created, e.g., "Created a custom rule to alert on three consecutive failed SSH login attempts."]*

---

## 👨‍💻 Future Work

* Integrate a third VM (e.g., Kali Linux) to act as an external threat source.
* Configure firewall logs (from a virtual router/firewall like pfSense) to be ingested by the Wazuh Manager.
* Develop custom automation scripts (e.g., using Python) to enhance threat hunting capabilities.
