# Linux Server Hardening Project

A hands-on demonstration of professional Linux security hardening on Ubuntu 24.04.

## Overview

This project transforms a default Ubuntu installation into a hardened, production-ready server by applying industry-standard security practices. It covers user management, SSH hardening, service minimization, firewall configuration, and continuous monitoring.

## Objectives

- Reduce attack surface by disabling unnecessary services
- Enforce least privilege through proper user and group management
- Secure remote access with SSH keys only
- Configure firewall with default-deny policy
- Implement continuous log monitoring with fail2ban
- Document every change with before/after evidence

## Quick Results

| Metric | Before | After |
|--------|--------|-------|
| Running services | 14 | 13 |
| Open firewall ports | 10 | 2 (SSH IPv4 + IPv6) |
| Root SSH login | Allowed | Disabled |
| Password authentication | Enabled | Disabled |
| Brute-force protection | None | fail2ban active |
| Security audit script | None | Custom script |

## Project Structure

- `before/` - Baseline assessment files
- `after/` - Hardened state files
  - `services/` - Service comparisons
  - `monitoring/` - Log analysis and fail2ban status
- `configs/` - Documentation of all changes
- `scripts/` - Automation scripts
- `screenshots/` - Visual evidence (32 screenshots)

## What Was Done

### Phase 3: SSH Hardening
- Created dedicated admin user (secadmin)
- Generated 4096-bit RSA SSH keys
- Disabled password authentication
- Disabled root SSH login

### Phase 4: Service Minimization
- Audited all running services
- Disabled Docker and containerd
- Reduced attack surface

### Phase 5: Firewall Configuration
- Verified UFW default-deny policy
- Confirmed only SSH exposed
- Tested blocked ports

### Phase 6: Logging & Monitoring
- Analyzed authentication logs
- Installed fail2ban
- Created custom security audit script

## Tools Used

- systemctl, UFW, SSH, fail2ban, tcpdump, ss, Bash, Git

## Skills Demonstrated

- Linux user and group management
- SSH key authentication
- Service minimization
- Firewall configuration
- Log analysis
- Security automation with Bash
- Technical documentation

## Key Security Principles

- Principle of Least Privilege
- Defense in Depth
- Separation of Duties
- Attack Surface Reduction

## Lessons Learned

1. Document baseline before changes
2. Test SSH keys before disabling passwords
3. Redirects run in the shell, not via sudo
4. SSH uses the key of the user running the command
5. Logs may appear binary in WSL - use grep -a

## Reversibility

**Re-enable Docker:**
sudo systemctl enable --now docker.socket docker.service containerd.service

**Re-enable password auth:**
sudo sed -i 's/^PasswordAuthentication no/PasswordAuthentication yes/' /etc/ssh/sshd_config

**Backup:** /etc/ssh/sshd_config.backup

## Author

Ashraf Rao
Aspiring SOC Analyst | CompTIA Security+ Candidate

## License

Educational and portfolio purposes.
