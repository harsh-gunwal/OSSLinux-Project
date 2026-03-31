# oss-audit-24bce11210

This is my Open Source Software lab repo for auditing Git on Arch Linux.

I'm harsh (`harsh`, reg no `24bce11210`). I wrote a few small shell scripts to pull basic system info, check package info, audit a couple of directories, and scan a log file for keyword matches.

## What's inside

- script1.sh - System Identity Report (kernel, distro, uptime, etc.)
- script2.sh - FOSS Package Inspector for git
- script3.sh - Disk and Permission Auditor for a few common folders
- script4.sh - Log file analyzer (counts keyword matches)
- script5.sh - Open Source Manifesto Generator (interactive)
- manifesto_jashwin.txt - Example output from the manifesto generator

## How to run the scripts

From the repo directory (`/home/harsh/oss-audit-24bce11210`):

1. Make them executable (one-time):
   - chmod +x script1.sh script2.sh script3.sh script4.sh script5.sh

2. Run them:
   - ./script1.sh
   - ./script2.sh
   - ./script3.sh
   - sudo ./script4.sh /var/log/journal error
     - If you don't pass the keyword, it defaults to error.
   - ./script5.sh
     - It asks 3 questions and writes manifesto_<username>.txt

## Notes (things I ran into)

- For script2.sh, the lab manual mentions rpm, but Arch uses pacman, so I used pacman -Qi git to check whether git is installed.
- script4.sh needs sudo when pointed at /var/log/journal since Arch uses systemd-journald instead of a plain syslog file. You can also use journalctl -k --grep="error" as an alternative.
- If script1.sh complains about lsb_release, install lsb-release from the AUR or use hostnamectl / cat /etc/os-release instead:
  - sudo pacman -S lsb-release

# Oss-project
# Oss-project
