# Network Support Engineer Practical Lab

**Comprehensive Hands-On Lab for MikroTik CHR Firewall, Hotspot & RADIUS Automation**

This repository documents a full hands-on practical task covering:
- Setup of MikroTik CHR in VirtualBox
- Firewall configuration
- Ansible automation for RADIUS/Hotspot
- Verification via Winbox  
Each step is documented with annotated screenshots, configuration files, and structured playbooks.

---

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Repository Structure](#repository-structure)  
3. [Prerequisites](#prerequisites)  
4. [Step-by-Step Work Completed](#step-by-step-work-completed)  
   - [Phase 1: VirtualBox & CHR Setup](#phase-1-virtualbox-chr-setup)  
   - [Phase 2: Firewall Configuration](#phase-2-firewall-configuration)  
   - [Phase 3: Ansible Playbook for RADIUS](#phase-3-ansible-playbook-for-radius)  
   - [Phase 4: RADIUS Verification](#phase-4-radius-verification)  
5. [Challenges Encountered](#challenges-encountered)  
6. [References and Resources](#references-and-resources)  

---

## Project Overview

This lab demonstrates **professional network automation using Ansible**, combined with **hands-on configuration of MikroTik RouterOS CHR** using Winbox and VirtualBox. Each technical milestone is captured with:
- Configuration files (`.rsc`, playbooks)
- Inventory files (`hosts`)
- Screenshots for verification  
This README is designed so that any reviewer can:
- Understand the intent of each component
- Navigate directly to relevant artifacts
- Reproduce the environment if needed. :contentReference[oaicite:1]{index=1}

---

## Repository Structure

Below is the high-level organization of the repository:


---

## Prerequisites

Before applying any playbook or configuration:
- **Oracle VirtualBox** installed with Extension Pack
- **MikroTik CHR image**
- **WSL2 (Ubuntu 24.04)** for Ansible control
- **VS Code + Remote-WSL integration**
- **Winbox** accessible to CHR via MAC or IP

Networking requirements:
- CHR should obtain an IP from VirtualBox DHCP
- Ansible control host (WSL) must reach CHR via API/SSH

---

## Step-by-Step Work Completed

---

### Phase 1: VirtualBox & CHR Setup

Documented the virtualization setup of MikroTik CHR:
- Imported the CHR image into VirtualBox
- Configured network adapters
- Verified DHCP assignment and interfaces
- Matched MAC addresses against configured ports  
**Browse artifacts:**
- `Screenshots/`  
  - See `MikroTik CHR VM Settings.png`, `MAC & DHCP IP.png`

Refer to these assets for configuration evidence.

---

### Phase 2: Firewall Configuration

Configured firewall rules using **Winbox**:
- Blocked specific traffic (e.g., TCP 443) as per exercise
- Confirmed rule order and effect  
**Browse artifacts:**  
- `Screenshots/Firewall.png`

---

### Phase 3: Ansible Playbook for RADIUS

Developed automation using Ansible:
- Created a **hosts** inventory for CHR
- Built `RADIUS.yml` playbook to:
  - Add RADIUS client entries
  - Configure services for Hotspot authentication
- Executed playbook successfully from WSL

Artifact reference:
- `/AnsiblePlaybook/RADIUS.yml`
- `hosts` inventory

Verification screenshot:
- `Screenshots/Ansible.png`

---

### Phase 4: RADIUS Verification

After Ansible automation:
- Verified RADIUS client configuration via **Winbox**
- Confirmed attributes (server, secret, services)
- Ensured Hotspot is using the RADIUS server

Verification artifact:
- `Screenshots/RADIUS.png`

---

## Challenges Encountered

Throughout the task, the following considerations were noted:

- **Connectivity Between WSL & CHR:** Windows to WSL network integration required precise VirtualBox adapter configuration to ensure reachability from Ubuntu Ansible control node.
- **Winbox Access via MAC:** MikroTik CHR sometimes required MAC-Winbox access when direct IP access was not yet configured.
- **Ansible Modules for RouterOS:** RouterOS API versus SSH connection parameters required careful inventory settings to avoid playbook failures.  
  More on RouterOS API/Ansible here: https://docs.ansible.com/projects/ansible/latest/collections/community/routeros/index.html :contentReference[oaicite:2]{index=2}

---

## References and Resources

Resources that supported this work:
- GitHub documentation on README best practices (why clear docs matter).
- Community RouterOS modules for Ansible automation.
- MikroTik RADIUS conceptual guide from official RouterOS docs.

These helped shape the automation approach and README structure.

---


## Thanks


