## 💻 Virtual Machine Setup Guide: Ubuntu on VMware

This guide details the provisioning steps for the two Ubuntu 24.04 Virtual Machines (VMs) required for the Wazuh SIEM Lab using VMware Workstation Pro.

---

## 📥 Prerequisites

Before starting, ensure you have downloaded the necessary software:

| Software | Download Link | Notes |
| :--- | :--- | :--- |
| **VMware Workstation Pro** | [Broadcom Knowledge Base](https://knowledge.broadcom.com/external/article?articleNumber=368734) | The primary hypervisor for the lab. |
| **Ubuntu 24.04 LTS ISO** | [Ubuntu Download Page](https://ubuntu.com/download/desktop) | Used as the Guest Operating System for both VMs. |

---

## ⚙️ Step-by-Step VM Creation

The same creation process is followed for **both** the **Wazuh Manager Server VM** and the **Wazuh Agent VM**.

| Step | Action | Configuration/Notes |
| :--- | :--- | :--- |
| **1.** | **Start VM Creation** | In VMware Workstation Pro, select **"Create a New Virtual Machine."** |
| **2.** | **Choose Installation Type** | Select **"Custom (advanced)"** and click **Next**. |
| **3.** | **Installer Disc Image** | Navigate to the **Guest Operating System Installation** tab. |
| **4.** | **Select ISO** | Choose **"Installer Disc image file (iso)"** and browse to select the downloaded **Ubuntu 24.04 LTS ISO** image. |
| **5.** | **Name and Location** | **Name the machine** (e.g., `Wazuh-Manager-VM` or `Wazuh-Agent-VM`). |
| **6.** | **Processor/Memory** | For optimal performance, assign **4 vCPUs** and **8 GB of RAM** to the **Wazuh Manager VM**. The Agent VM can use less (e.g., 2 vCPUs, 4 GB RAM). |
| **7.** | **Network Type** | Select **"Use host-only networking (VMware Network Adapter VMnet1)"** to isolate the lab from your home network. |
| **8.** | **Specify Disk Capacity** | Set the **Maximum disk size** to **100 GB** for better log storage capacity. Select **"Split virtual disk into multiple files."** |
| **9.** | **Store Disk File** | Change the location to store the disk file on your **D: drive** (or dedicated storage partition) for optimal organization and host OS performance. |
| **10.** | **Finish** | Click **"Finish"** and power on the VM. |

---

## 🖥️ OS Installation Inside the VM

After the VM is powered on, follow the standard Ubuntu installation process:

1.  **Follow the Installation Steps:** Proceed through the steps guided by the Ubuntu installer, as detailed on the official site: [Install Ubuntu Desktop](https://ubuntu.com/tutorials/install-ubuntu-desktop#5-installation-setup).
2.  **User Creation:** Set up a username and password (e.g., `wazuhadmin` for the Manager VM, and `wazuhuser` for the Agent VM).
3.  **Finish Setup:** Complete the installation and reboot the VM.

Your base Ubuntu VMs are now ready for the Wazuh software installation. The next step is to download and execute the Wazuh installation scripts via the terminal.
