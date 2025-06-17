# 🛠️ FortiGate Firewall Setup Guide (GUI-based in EVE-NG)

This guide walks through configuring a Fortinet FortiGate firewall in a local virtual lab using EVE-NG. The lab demonstrates how to enable internet access for an internal Windows Server through proper interface configuration, DNS setup, and firewall policies via the GUI.

---

## 🔍 Project Overview

This is a GUI-based lab built in **EVE-NG** to simulate a realistic enterprise firewall deployment using FortiGate.

### ⚙️ Technologies Used

- **Fortinet FortiGate VM**
- **EVE-NG** (Emulated Virtual Environment)
- **Windows Server 2016/2019** as the test host
- **No router, no Wireshark, local-only deployment**

---

## 🖥️ Network Topology

+---------------+        +-----------------+      +--------------+
| Windows Server| <----> | FortiGate       |<---->| EVE-NG NAT   |
| 192.168.1.10  | <----> | port2 port1     |<---->| DHCP/Internet|
+---------------+        +-----------------+      +--------------+


---

## 🎯 Purpose

- Configure FortiGate interfaces using GUI
- Allow LAN traffic (Windows Server) to access the internet via NAT
- Verify with ping tests
- Learn basic enterprise-level firewall management

---

## 🪜 Setup Steps

### Step 1: Login to FortiGate GUI  
📷 `01-login.png`  
Go to the FortiGate IP (e.g., `https://192.168.x.x`) in your browser and log in.

---

### Step 2: Dashboard Overview  
📷 `02-dashboard.png`  
Get an overview of system status and interfaces.

---

### Step 3: Open Initial Setup  
📷 `03-initial-setup.png`  
Navigate to **Network > Interfaces** to start interface configuration.

---

### Step 4: Configure Interfaces  
📷 `04-interfaces.png`  
You'll see `port1`, `port2`, etc.

---

### Step 5: Set port1 to DHCP (WAN)  
📷 `05-port1-dhcp.png`  
This will connect FortiGate to the internet through EVE-NG’s NAT cloud.

---

### Step 6: Set port2 to Static IP (LAN)  
📷 `06-port2-static.png`  
Set to:  

IP: 192.168.1.1/24


---

### Step 7: Save Interface Settings  
📷 `07-apply-interfaces.png`  
Click **Apply/OK** to confirm.

---

### Step 8: Configure DNS  
📷 `08-dns.png`  
Go to **Network > DNS**.

---

### Step 9: Set Primary DNS  
📷 `09-set-dns.png`  
Use:

8.8.8.8 (Google DNS)


---

### Step 10: Open Firewall Policies  
📷 `10-policy-menu.png`  
Go to **Policy & Objects > Firewall Policy**.

---

### Step 11: Create New Firewall Rule  
📷 `11-create-policy.png`  
Click **Create New**.

---

### Step 12: Configure Rule Details  
📷 `12-rule-details.png`  
Set:

Source Interface: port2
Destination Interface: port1
Source: all
Destination: all


---

### Step 13: Enable NAT  
📷 `13-enable-nat.png`  
Check the **NAT** option to translate private IPs to public.

---

### Step 14: Save the Policy  
📷 `14-save-policy.png`  
Click **OK** to finish.

---

### Step 15: Configure Windows Server  
📷 `15-windows-network.png`  
In the Windows Server VM:

IP: 192.168.1.10
Gateway: 192.168.1.1
DNS: 8.8.8.8


---

### Step 16: Test Internet Access  
📷 `16-ping.png`  
Run in CMD:

ping 8.8.8.8


✅ If you get replies — the firewall is successfully routing traffic!

---

## ✅ Final Verification Output

Reply from 8.8.8.8: bytes=32 time=15ms TTL=118
Reply from 8.8.8.8: bytes=32 time=15ms TTL=118


---

## 📁 File Structure

/configs
├── screenshots/
│ ├── 01-login.png
│ ├── 02-dashboard.png
│ └── ...
└── firewall.conf
/docs
└── setup_guide.md (this file)


---

## 🙌 Author

Created by **[Your Name]**  
For portfolio/demo/recruiter use — June 2025  