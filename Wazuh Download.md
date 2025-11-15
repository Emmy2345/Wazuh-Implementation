# 🚀 Wazuh Quickstart Installation Steps

This document provides the necessary terminal commands to quickly install the Wazuh Manager, Indexer, and Dashboard using the official installation assistant on your dedicated Ubuntu 24.04 VM.

---

## 1. Download and Run the Wazuh Installation Assistant

Execute the following command in your terminal. This downloads the installation script and immediately runs it with the `-a` flag, which installs all components (Manager, Indexer, and Dashboard) on a single machine.

```bash
curl -sO [https://packages.wazuh.com/4.14/wazuh-install.sh](https://packages.wazuh.com/4.14/wazuh-install.sh) && sudo bash ./wazuh-install.sh -a

## 2. Access the Wazuh Web Interface

Once the installation confirms success and all services are running, you can access the web interface from your host browser or a different VM on the same host-only network.

### Access Details:

* **URL:** Go to `https://<WAZUH_DASHBOARD_IP_ADDRESS>`
* **Username:** `admin`
* **Password:** The generated `<ADMIN_PASSWORD>` provided in the installation summary from Step 1.
