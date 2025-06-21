 # 🔁 Remote Access Project with RDP (Remmina) and TeamViewer (VirtualBox Lab)

## 🎯 Objective

Showcase the use of **Remmina** on Linux to connect to remote systems, while also configuring:
- RDP (Linux to Windows)
- TeamViewer (both directions)

All within a VirtualBox lab using Windows 10 and Ubuntu Desktop 22.04.

---

## 🧰 Tools & Environment

| Component     | Description                            |
|--------------|----------------------------------------|
| Virtualization | VirtualBox                            |
| Windows Client | Windows 10 VM                         |
| Linux Client   | Ubuntu Desktop 22.04 VM               |
| Networking     | Bridged Adapter   |
| Remote Tools   | Remmina, TeamViewer   |

---

## ⚙️ Step-by-Step Setup

### ✅ Step 1: Install Remmina on Ubuntu

```bash
sudo apt update
sudo apt install remmina -y
````

Launch it:

```bash
remmina
```

Use it to create and manage remote connections via RDP, VNC, or SSH.
<img width="905" alt="01-lauch remmina" src="https://github.com/user-attachments/assets/8d390c44-32a5-481f-9476-48ef365ef5d2" />

---

## 🖥️ Step 2: Enable RDP on Windows 10 VM

1. Open **System > Remote Desktop**
   <img width="833" alt="03-Remote" src="https://github.com/user-attachments/assets/19913c86-d599-4cf4-8caa-4014e7b0e121" />

2. Enable **Remote Desktop**

 <img width="833" alt="04-enable remote" src="https://github.com/user-attachments/assets/215d84d0-1546-4f91-9b45-94937b2c89f2" />

3. Note the IP:

   ```powershell
   ipconfig
   ```
<img width="815" alt="02-IPconfig" src="https://github.com/user-attachments/assets/6b490186-f1aa-41ef-87c3-323e45f39dd3" />


🔗 From Terminal:
* Allow RDP through the firewall : sudo ufw allow 3389/tcp in bash
  <img width="878" alt="07-allow RDP" src="https://github.com/user-attachments/assets/9d617410-1f06-4517-a6c2-ab65a88537fd" />

🔗 From Remmina:
<img width="944" alt="10-RDP-Remmina" src="https://github.com/user-attachments/assets/4cee9770-490c-4844-94e6-dba5fb51df58" />

* Protocol: RDP & IP: Windows VM IP: 192.168.0.199
  <img width="944" alt="10-RDP-Remmina" src="https://github.com/user-attachments/assets/59f232e2-98b3-44bc-829c-9b062152d8ac" />

* Username/Password: Windows login credentials
<img width="875" alt="11-Username-Passwd" src="https://github.com/user-attachments/assets/6f78dc44-1da4-454e-a31d-221f238ab952" />

* RDP Connection Established
<img width="946" alt="12-RDP Connected" src="https://github.com/user-attachments/assets/55a363b4-3cd0-43ca-a0af-285f9624f4aa" />

---

## 🤝 Step 3: TeamViewer on Both Systems

### On Linux:

```bash
wget https://download.teamviewer.com/download/linux/teamviewer_amd64.deb
sudo apt install ./teamviewer_amd64.deb
```

### On Windows:

Install TeamViewer and share the ID and password.

🟢 Either OS can connect to the other using TeamViewer ID.

-  **Screenshots:**
-  Launch Teamviewer in Linux
- <img width="1014" alt="15-Launch Teamvier Linux" src="https://github.com/user-attachments/assets/51caa91b-f3d4-4ceb-ae10-1cf8f4075ed4" />

- ID and Passowrd generated
- <img width="709" alt="16-ID Pass Linux" src="https://github.com/user-attachments/assets/474dac2b-538a-4e65-87dc-2b1563c4ea57" />

- Copy Windows ID
- <img width="1015" alt="17-copy windows ID" src="https://github.com/user-attachments/assets/59423d38-81e6-4bc9-99cc-d6dcb3e976e3" />

- Authenticate with Windows password
- <img width="710" alt="18-Authenticate" src="https://github.com/user-attachments/assets/f3c6ff68-ca62-4d4a-8847-5e54b2b13877" />

- Connection Established. 
- <img width="1121" alt="19-Connection established " src="https://github.com/user-attachments/assets/d4056098-4f37-48cb-8fbc-7988428bfb68" />


---

## 🔐 Firewall & Port Notes

| Tool       | Port     | Protocol |
| ---------- | -------- | -------- |
| RDP        | 3389     | TCP      |
| TeamViewer | 443/5938 | TCP      |

Use `ufw allow` and `netstat -tuln` as needed to open/check ports.

---

## 🧠 Skills Demonstrated

* Installation and configuration of remote access software
* Use of Remmina to manage RDP, SSH from Linux
* Understanding of ports, security, and user credentials
* Testing remote access from both directions (Windows ↔ Linux)
* Secure communication over LAN and internet

---

## ✅ Outcome

With this setup:

* Remmina manages **RDP/SSH sessions** easily from Linux
* Windows RDP is accessible from Linux
* TeamViewer provides a cloud-based alternative

---

## 📌 Notes

* Ensure both VMs are powered and reachable (use `ping`)
* TeamViewer requires internet; RDP is local unless port forwarded



