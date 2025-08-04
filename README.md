# Detecting SSH Brute Force Attacks with Wazuh SIEM

## 📝 Project Overview
This project demonstrates how Wazuh can be used to detect, alert, and mitigate SSH brute-force attacks within a monitored environment.

## 💻 Environment Setup
- **Target machine:** Ubuntu Server (`Ubuntu-N`)
- **Attacker machine:** Kali Linux (`Kali-Hammed`)
- **Monitoring solution:** Wazuh Server with agent on the target system

## 🚨 Attack Simulation
Brute-force attack was executed using **THC Hydra** from the Kali Linux VM:

_hydra -l admin -P password.txt 192.168.36.135 ssh_

<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/490c480a-57d5-42a8-89f2-970deaf1dbf8" />

# SSH Brute Force Detection Using Wazuh

The attacker attempted multiple SSH login attempts using a password list.

This activity was monitored live in **Wazuh**.

---

## 🎯 Detection Results

Wazuh generated real-time alerts including:

- `sshd`: Attempt to login using a non-existent user  
- `PAM`: User login failed  
- Multiple failed logins in a small period of time  

### Example Alert Details:

- **Agent:** `Kali-Hammed`  
- **Rule IDs:** `5710`, `5503`, `5551`  
- **Rule Levels:** `5`, `10 (Critical)`

#### Wazuh Dashboard Logs:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2a5f0acc-e12f-4905-8c82-904dbb54a42f" />


#### Hydra Attack Logs:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/400a36fa-5bbb-4167-b591-0d9be20c0679" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/312bda8e-bda4-441b-9832-d5d69d2280d0" />


---
[![Watch the video](https://img.youtube.com/vi/veRJaT8X42c/0.jpg)](https://youtu.be/veRJaT8X42c)


## 🔐 Mitigation Process

- Locked down targeted user accounts.
- Set `MaxAuthTries` in `/etc/ssh/sshd_config` to limit SSH attempts.
- Deployed `fail2ban` to automatically block IPs with repeated failures.
- Enabled **Multi-Factor Authentication (MFA)** for SSH access.
- Enhanced Wazuh rule thresholds for faster alerting.

---

## 🛠️ Skills Applied

- Security Monitoring and Incident Response  
- Wazuh SIEM Deployment and Configuration  
- Linux System Hardening  
- Threat Simulation and Detection  
- SSH Service Hardening  

---

## ✅ Conclusion

This lab exercise successfully showed how **Wazuh** can detect SSH brute-force attempts and provide actionable alerts for incident response.

**Wazuh** remains an essential tool in my cybersecurity toolkit for both academic and professional threat hunting tasks.

---

## 👤 Author

**Hammed Oluwole**  
Cybersecurity Student | Threat Hunter | Security Operations Enthusiast
