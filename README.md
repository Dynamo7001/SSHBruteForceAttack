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
- _[Insert screenshot or log snippet here]_

#### Hydra Attack Logs:
- _[Insert screenshot or log snippet here]_

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
