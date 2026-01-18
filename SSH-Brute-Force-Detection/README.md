# SSH Brute Force Detection Lab

## Objective
Detect and analyze failed SSH authentication attempts using system logs.

## Environment
- Kali Linux
- OpenSSH
- systemd journal (journalctl)

## Scenario
The SSH service was enabled and monitored for authentication activity. 
Multiple login attempts were made using an invalid username to simulate brute-force behavior.

## Detection Method
The following commands were used:
- journalctl | grep "Failed password"
- journalctl | grep sshd

## Findings
- Multiple failed authentication attempts detected
- Invalid user enumeration observed
- PAM authentication failures logged
- SSH session terminated after repeated failures

## Impact
Repeated failed SSH authentication attempts may indicate brute-force or unauthorized access attempts.

## Mitigation (Future Work)
- Implement SSH hardening
- Enable automated blocking (e.g., fail2ban)
