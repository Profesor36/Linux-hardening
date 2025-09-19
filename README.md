# Linux Hardening

This repository documents my hands-on learning in securing Linux systems.  
It contains basic but essential configurations I use to harden servers and improve their security posture.

---

## Firewall with UFW
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install UFW
sudo apt install ufw -y

# Default policies
sudo ufw default deny incoming
sudo ufw default allow outgoing

# Allow only SSH
sudo ufw allow 22/tcp

# Enable firewall
sudo ufw enable
sudo ufw status verbose

## Fail2Ban (basic intrusion prevention)
sudo apt install fail2ban -y
sudo systemctl enable fail2ban
sudo systemctl start fail2ban

## Automatic Security Updates
sudo apt install unattended-upgrades -y
sudo dpkg-reconfigure --priority=low unattended-upgrades
