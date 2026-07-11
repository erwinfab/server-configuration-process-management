# Red Hat Enterprise Linux (RHEL 9.3) Core Competency: Secure Remote Access Engineering & System Configuration Baseline

## 🎯Project Overview
This project validates technical competencies in secure network access design, host hardening policies, package management systems, and system environment provisioning within Red Hat Enterprise Linux 9.3. The objective is to deploy cryptographic SSH key authentications across distinct server nodes, harden the local OpenSSH daemon against brute-force entry attempts, manage applications via the DNF subsystem, and re-synchronize local time tracking infrastructure metrics.

## 💻Environments and Technologies Used
**Operating System Environment**: Red Hat Enterprise Linux 9.3 (RHEL)

**Core Utilities Demanded**: `ssh-keygen`, `ssh-copy-id`, OpenSSH Server (`sshd`), `dnf`, `timedatectl`, `systemctl`

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

---

**Step 2: OpenSSH Daemon Access Hardening**


Modify persistent daemon configuration files to drop obsolete authentication paths and tighten the perimeter security posture of the node.

* Escalate privileges to root context
   * `sudo -i`

* Hot-patch the active configuration directives inside the secure file location
   * `vi /etc/ssh/sshd_config`
      * Directives adjustments written inside configurations:
         * `PermitRootLogin no`
         * `PasswordAuthentication no`

<img width="536" height="61" alt="image" src="https://github.com/user-attachments/assets/5076bffd-6903-45b3-9fbc-c52dbfb80420" />


<img width="558" height="135" alt="image" src="https://github.com/user-attachments/assets/1c8a2969-648d-423d-9f39-191f3761e523" />


* Enforce runtime state synchronization across the active server layer
   * `systemctl restart sshd`


<img width="615" height="92" alt="image" src="https://github.com/user-attachments/assets/c59ca524-5c91-486b-a974-264ffcfe3e15" />

---

**Step 3: Software Provisioning & Localization Engineering**


Leverage the package distribution engine to deploy active system binaries and realign timekeeper baselines.

* Provision application packages from upstream software repositories
   * `dnf install -y zsh`


<img width="884" height="691" alt="image" src="https://github.com/user-attachments/assets/1a62a659-d545-41da-b762-e70d691e6e46" />


* Realignment of local time tracking infrastructure metrics
   * `timedatectl set-timezone Asia/Kolkata`


<img width="894" height="221" alt="image" src="https://github.com/user-attachments/assets/14b4f0ce-a6b2-4d9b-a6a5-2ca766138e40" />
  
## 📊 Verification and Testing

**Step 1: Laboratory Compliance Execution**


Return to the workstation context and trigger the programmatic laboratory script to evaluate configuration alignment against technical constraints.  


<img width="807" height="461" alt="image" src="https://github.com/user-attachments/assets/6303d2b9-6892-4d8d-b95a-bf66c1952976" />

---

**Step 2: Sandbox Environment Teardown**


De-provision local tracking mechanisms to return the deployment sandbox back to baseline conditions.  


<img width="816" height="255" alt="image" src="https://github.com/user-attachments/assets/ff71562f-52a7-4e5c-8962-5023f9e7cef9" />

