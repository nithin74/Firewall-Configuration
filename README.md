# Firewall-Configuration
Task 4 – Firewall Configuration and Testing (Linux &amp; Windows)

🎯 Objective
To configure and test basic firewall rules that control network traffic using UFW on Linux and Windows Defender Firewall on Windows. 
This helps protect the system by filtering incoming and outgoing traffic based on defined rules.

🖥️ Environment Used

| Component     | Details                                                                        |
| ------------- | ------------------------------------------------------------------------------ |
| OS            | Parrot Security OS (Linux), Windows 7 (VM), Windows 11                         |
| Tools         | UFW (Uncomplicated Firewall), Windows Defender Firewall with Advanced Security |
| Testing Tools | Nmap, SSH, PowerShell                                                          |


🐧 Linux: UFW Firewall Configuration (Parrot OS)

⚙️ Steps Performed
Enable UFW
  
  sudo ufw enable


View Current Rules

sudo ufw status

sudo ufw status numbered


✅ 3. Blocked Inbound Traffic on Port 22 (SSH)
sudo ufw deny 22
✅ 4. Tested the Block Rule
nmap -p 22 localhost
✅ 5. Removed the test rule
sudo ufw delete deny 23
✅ 6. Allowed SSH (port 22)
sudo ufw allow 22
✅ 7. To Start and Stop SSH Service & Check the Status
sudo systemctl start ssh
sudo systemctl status ssh
sudo systemctl stop ssh
In Windows
⚙️ Steps Performed
✅ 1. Opened Firewall Configuration
Opened Windows Defender Firewall with Advanced Security from Start Menu.
✅ 2. Listed Current Inbound Rules
Navigated to Inbound Rules in the left pane to view existing rules.
✅ 3. Blocked Inbound Traffic on Port 22 (SSH)
Clicked on New Rule > Port > TCP > Specific local ports: 23
Selected Block the connection
Applied to all profiles (Domain, Private, Public)
Named the rule: Block_SSH_Port_22
✅ 4. Tested the Block Rule
Used ssh your_username@192.168.1.72  to test connectivity.

Also verified using nmap from another machine:

nmap -p 22 <Windows-IP>
✅ 5. Removed the Test Block Rule
Went back to Inbound Rules.
Right-click on Block_SSH_Port_22 and selected Delete.
