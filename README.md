## VAGRANT-AND-LINUX-SERVERS


Welcome to our project showcasing the deployment of an HTML template on CentOS and a WordPress site on a LAMP stack running on Ubuntu. This repository demonstrates two distinct approaches: manual setup and automated provisioning using Vagrant.

## Project Overview

### Manual Setup
In the manual setup, we utilized Vagrant to create and manage our virtual machines. Here are the key steps:

- **Virtual Machine Setup:** Vagrant was used to set up the CentOS and Ubuntu virtual machines.
- **Network Configuration:** Assigned different static IP addresses to avoid collisions.
- **Manual Deployment:**
  - **CentOS (Finance):** Hosted an HTML template.
  - **Ubuntu (WordPress):** Deployed a WordPress site on a LAMP stack.
- **Execution:** Majority of the setup instructions were executed using Git Bash.

### Automated Provisioning with Vagrant
For a streamlined setup, we leveraged Vagrant’s automation capabilities. Key steps included:

- **Vagrant Configuration:** Modified Vagrant files to set up static IP addresses.
- **Provisioning Scripts:** Added provisioning commands to automate the deployment.
  - **CentOS (FinanceAutomated):** Automated setup for hosting the HTML template.
  - **Ubuntu (WordPressIAC):** Automated setup for the WordPress site.

## Repository Structure
- `CentOS/`: Default Vagrant configuration with modified IP addresses for CentOS.
- `Ubuntu/`: Default Vagrant configuration with modified IP addresses for Ubuntu.
- `Finance/`: Manual setup for CentOS.
- `WordPress/`: Manual setup for Ubuntu.
- `FinanceAutomated/`: Automated setup for CentOS.
- `WordPressIAC/`: Automated setup for Ubuntu.

## Key Highlights
- **Static IP Addresses:** Configured unique IPs for each VM to avoid conflicts.
- **Vagrant Power:** Demonstrated Vagrant's capabilities in setting up and managing virtual environments.
- **Manual vs. Automated Setup:** Compared manual setup with automated provisioning for deploying web services.
- **Provisioning with Vagrant:** Leveraged Vagrant’s provisioning features with Ruby-based configuration and Linux commands.

## How to Get Started

### Clone the Repository:
```sh
git clone https://github.com/chlakhal/VAGRANT-AND-LINUX-SERVERS.git
cd VAGRANT-AND-LINUX-SERVERS
```

### Manual Setup:
#### CentOS (Finance): 
Follow these instructions below. Majority of the setup steps were executed using Git Bash.
```sh
vagrant up
vagrant ssh
sudo -i
yum install httpd wget zip unzip -y
systemctl start httpd
systemctl enable httpd
mkdir -p /tmp/finance
cd /tmp/finance
wget https://www.tooplate.com/zip-templates/2135_mini_finance.zip
unzip -o 2135_mini_finance.zip
cp -r 2135_mini_finance/* /var/www/html/
systemctl restart httpd
cd /tmp
rm -rf /tmp/finance
```

#### Ubuntu (WordPress):
Follow the official [Ubuntu documentation](https://ubuntu.com/tutorials/install-and-configure-wordpress#1-overview) to install and configure WordPress. Majority of the setup steps were executed using Git Bash.

### Automated Provisioning:
#### CentOS (FinanceAutomated):
Navigate to the `FinanceAutomated/` directory and run:
```sh
vagrant up
```

#### Ubuntu (WordPressIAC):
Navigate to the `WordPressIAC/` directory and run:
```sh
vagrant up
```

## Testing the Setup

1. **Copy the IP Address:**
   - Open the relevant Vagrant file and copy the static IP address assigned to the VM.

2. **Access the VMs:**
   - Use the copied IP address in your web browser to access the deployed services.
   - Alternatively, use `vagrant ssh` to log into the VM and verify the setup manually.
   ```sh
   vagrant ssh
   ```

## Conclusion
This project illustrates the flexibility and efficiency of using Vagrant to manage multi-environment web hosting. Whether through manual setup or automated provisioning, this repository provides a robust foundation for hosting web services on CentOS and Ubuntu.

---

