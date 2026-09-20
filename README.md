# Linux Server Hardening Project

## Overview

This project demonstrates practical Linux security hardening on a fresh 
Ubuntu server. The goal was to reduce the attack surface, enforce least 
privilege, and establish continuous monitoring — transforming a default 
installation into a production-ready, secure system.

## Objectives

- Reduce the attack surface by disabling unnecessary services
- Enforce least privilege through proper user and group management
- Secure remote access with SSH key-based authentication
- Configure a firewall with default-deny inbound policy
- Implement continuous log monitoring with fail2ban
- Document every change with before-and-after evidence
- Create reusable automation scripts for ongoing security checks

## What I Did

### 1. Baseline Assessment
- Documented all running services, open ports, and default permissions
- Captured screenshots of the insecure default state

### 2. User and Access Hardening
- Created a dedicated non-root admin user (`deploy`)
- Disabled root SSH login entirely
- Generated and deployed SSH keys for passwordless authentication
- Disabled password authentication to prevent brute force attacks

### 3. Service Minimization
- Audited all running services
- Disabled unnecessary services (CUPS, Bluetooth, Avahi)
- Reduced running services from 25+ down to 12 essential ones

### 4. Firewall Configuration
- Set default policy: deny all incoming, allow all outgoing
- Allowed only required ports: SSH (22), HTTP (80), HTTPS (443)
- Enabled UFW and verified rules with `ufw status verbose`

### 5. Logging and Monitoring
- Installed and configured fail2ban for intrusion prevention
- Created a custom security audit script (`security_check.sh`)
- Set up automatic log review for failed login attempts

### 6. Documentation
- Wrote this README with full methodology
- Organized before/after screenshots
- Saved all scripts and configuration files

## Results

| Metric | Before | After |
|--------|--------|-------|
| Running services | 25 | 12 |
| Open ports | 5 | 3 |
| Root SSH login | Enabled | Disabled |
| Password authentication | Enabled | Disabled |
| Firewall | Inactive | Active |
| Failed login monitoring | None | fail2ban |

## Tools and Technologies Used

- **systemctl** — service management
- **UFW** — firewall configuration
- **SSH / ssh-keygen** — secure remote access
- **fail2ban** — intrusion prevention
- **tcpdump** — traffic analysis
- **ss** — network monitoring
- **Bash scripting** — automation

## Skills Demonstrated

- Linux user and group management
- SSH hardening and key-based authentication
- Service minimization and attack surface reduction
- Firewall configuration following least privilege
- Log analysis and security monitoring
- Security automation with Bash
- Technical documentation

## Lessons Learned

1. Always document your baseline before making changes
2. Test SSH key access before disabling password authentication
3. Layer security controls — no single control is enough
4. Monitor logs daily to detect suspicious activity early
5. Automation saves time and ensures consistency

## Next Steps

- Set up a home SOC lab with ELK Stack
- Learn Suricata for network intrusion detection
- Explore container security with Docker
- Pursue CompTIA Security+ certification

## How to Use This Repository

1. Clone the repository
2. Review the `before/` folder to see the baseline state
3. Review the `after/` folder to see the hardened state
4. Run `scripts/security_check.sh` on your own system
5. Adapt the configurations for your own environment

## Author

Muhammad Ashraf Rao
Aspiring SOC Analyst | CompTIA Security+ Candidate
www.linkedin.com/in/ashraf-rao | ashrafrao3@gmail.com
