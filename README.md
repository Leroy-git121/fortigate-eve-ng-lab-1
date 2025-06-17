# fortigate-eve-ng-lab-1
A beginner-friendly Fortinet FortiGate firewall lab built in EVE-NG. Demonstrates basic GUI-based configuration for NAT, firewall rules, and internet access using a Windows Server test host — all running locally with no external router required.


# 🧰 Tools Used

- EVE-NG (Community Edition)
- Fortinet FortiGate VM (KVM/QEMU)
- Windows Server (Test Host)
- EVE-NG NAT Cloud (for internet access)

---

## 🌐 Topology

```
Windows Server ↔ FortiGate ↔ NAT Cloud ↔ Internet
```

---

## ✅ Key Features

- Internet access from internal Windows Server
- Basic FortiGate NAT and firewall policy
- GUI-based configuration
- Fully local setup (no router, no Wireshark, no physical interfaces)

---

## 📁 Folder Structure

```
fortigate-eve-ng-lab/
├── README.md
├── configs/
│   └── screenshots/
│       ├── 1.png
│       ├── 2.png
│       └── ... up to 33.png
└── docs/
    └── setup_guide.md
```

---

## 🖥️ FortiGate GUI Configuration

All FortiGate configuration is done through the GUI. Refer to the full walkthrough in [`docs/setup_guide.md`](docs/setup_guide.md).

---

## 🚀 To Do

- Add FortiCloud logging
- Demonstrate SSL inspection
- Simulate attacks to test firewall rules
- Add VPN or VLAN segmentation examples

---

## 🧠 Author

This project was created as a self-study and demonstration of virtual firewall setup and configuration using FortiGate on EVE-NG.
