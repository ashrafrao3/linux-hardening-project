=====================================
  LINUX SERVER HARDENING PROJECT
=====================================

A hands-on demonstration of professional
Linux security hardening on Ubuntu 24.04.

-------------------------------------
  QUICK RESULTS
-------------------------------------

Metric                  Before    After
------                  ------    -----
Running services        14        13
Open firewall ports     10        2 (SSH)
Root SSH login          Allowed   Disabled
Password auth           Enabled   Disabled
Brute-force protection  None      fail2ban
Security audit script   None      Custom

-------------------------------------
  WHAT WAS DONE
-------------------------------------

Phase 3: SSH Hardening
  - Dedicated admin user (secadmin)
  - 4096-bit RSA SSH keys
  - Password auth disabled
  - Root SSH disabled

Phase 4: Service Minimization
  - Docker and containerd disabled
  - Reduced attack surface

Phase 5: Firewall Configuration
  - UFW default-deny policy
  - Only SSH exposed

Phase 6: Logging & Monitoring
  - fail2ban installed
  - Custom security audit script

-------------------------------------
  SKILLS DEMONSTRATED
-------------------------------------

- Linux user and group management
- SSH key authentication
- Service minimization
- Firewall configuration
- Log analysis
- Security automation with Bash
- Technical documentation

-------------------------------------
  TOOLS USED
-------------------------------------

systemctl, UFW, SSH, fail2ban,
tcpdump, ss, Bash, Git

-------------------------------------
  PROJECT STATS
-------------------------------------

- Duration: 6 weeks
- Phases: 7 complete
- Screenshots: 32
- Documentation files: 8+

=====================================
  Ashraf Rao
  Aspiring SOC Analyst
  CompTIA Security+ Candidate
=====================================
