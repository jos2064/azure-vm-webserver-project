# Azure VM Web Server Deployment (Fedora Linux)
## Project Overview
This project demonstrates the deployment of a Linux-based virtual machine on Microsoft Azure and configuring it as a web server accessible over the internet.

## Architecture
Azure Virtual Machine (Fedora Linux)
Virtual Network (VNet) & Subnet
Network Security Group (NSG)
Public IP Address
Apache Web Server (httpd)
## Steps Performed
1. VM Deployment
Created a Fedora Linux VM in Azure
Configured SSH access using public IP
2. Networking Setup
Created Virtual Network and Subnet
Configured NSG rules:
Allowed SSH (Port 22)
Allowed HTTP (Port 80)
3. Web Server Setup
Installed Apache (httpd)
Started and enabled the service
```
sudo dnf install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd
```
4. Firewall Configuration
```
sudo firewall-cmd --permanent --add-service=http
sudo firewall-cmd --reload
```
6. Troubleshooting
- Encountered memory issue (“Killed” error)
- Resolved by adding swap memory:
```
sudo fallocate -l 1G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
```
## Output
Successfully hosted a webpage accessible via public IP
## Screenshots
- VM running
- NSG rules
- SSH connection
- Website output
## Key Learnings
- Azure VM provisioning
- SSH-based remote access
- Network security (NSG + firewall)
- Linux service management
- Troubleshooting low-memory issues using swap
- Hosting a web server on cloud infrastructure
