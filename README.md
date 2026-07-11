# Red Hat Enterprise Linux (RHEL 9.3) Core Competency: Secure Remote Access Engineering & System Configuration Baseline

## 🎯Project Overview
This project validates technical competencies in secure network access design, host hardening policies, package management systems, and system environment provisioning within Red Hat Enterprise Linux 9.3. The objective is to deploy cryptographic SSH key authentications across distinct server nodes, harden the local OpenSSH daemon against brute-force entry attempts, manage applications via the DNF subsystem, and re-synchronize local time tracking infrastructure metrics.

## 💻Environments and Technologies Used
**Operating System Environment**: Red Hat Enterprise Linux 9.3 (RHEL)
**Core Utilities Demanded*v: `ssh-keygen`, `ssh-copy-id`, OpenSSH Server (`sshd`), `dnf`, `timedatectl`, `systemctl`

## 📋Objectives and Scenario
The scenario models an infrastructure environment requiring secure multi-node communication, system daemon perimeter defense adjustments, software deployment, and clock synchronization baseline changes.

### Technical Specification Requirements:
* **Key Generation Routing**: Provision an unpassphrased SSH key pair explicitly mapped to file path `/home/student/.ssh/review3_key`. 

* **Cross-Node Trust Interconnection**: Authorize cross-node authentication paths to permit passwordless access from `serverb` into `servera`.  

* **Daemon Hardening Execution**: Modify OpenSSH directives to entirely bar administrative `root` connections and block all raw text password-based authentications on `serverb`. 

* **Software Provisioning**: Deploy the standard `zsh` package profile across the local environment.

* **Localization Realignment**: Enforce a geographic time zone shift updating the host context to `Asia/Kolkata`.

## 🛠️ High-Level Deployment and Configuration Steps

**Step 1: Cryptographic Key Infrastructure & Node Trust Establishment**


Generate localized cryptographic keys matching strict structural namespace criteria and copy the public authentication signature block out to the target peer node.

* Generate custom key architectures skipping the passphrase allocation loop
   * `ssh-keygen -t rsa -f /home/student/.ssh/review3_key -N ""`

* Append public keys into the target remote node authorization ledger
   * `ssh-copy-id -i /home/student/.ssh/review3_key.pub student@servera`

<img width="896" height="763" alt="image" src="https://github.com/user-attachments/assets/0cfe1ce8-51bc-4ffd-8e06-37db9935a8dc" />


**Step 2: OpenSSH Daemon Access Hardening**


Modify persistent daemon configuration files to drop obsolete authentication paths and tighten the perimeter security posture of the node.

* Escalate privileges to root context
   * `sudo -i`

* Hot-patch the active configuration directives inside the secure file location
   * `vi /etc/ssh/sshd_config`
      * Directives adjustments written inside configurations:
         * `PermitRootLogin no`
         * `PasswordAuthentication no`
     
## 📊 Verification and Testing
