# Linux-File-System-Hunting
1. System Behavior & /etc
The /etc directory is the heart of Linux configuration. It controls everything from boot
behavior to application settings. Hunting here reveals how the system is 'intended' to run.

2. DNS Configuration
   
Check /etc/resolv.conf to see which DNS servers the system uses. For modern
systems, /etc/systemd/resolved.conf also plays a key role in how names are
resolved.

3. Network & Routing
   
The routing table can be inspected via /proc/net/route . Interface configurations

live in /etc/network/interfaces (Debian) or /etc/sysconfig/network-
scripts/ (RHEL).

Security & Monitoring

4. Logs & Insights
   
Found in /var/log/ . Crucial files include auth.log (login attempts) and syslog .
These provide a trail of all system activities.


5. User Management
   
Key files include /etc/passwd (user list), /etc/shadow (hashed passwords),
and /etc/group . Analyzing these is fundamental for privilege escalation hunting.

Kernel & Process Interfaces

6. Process Information ( /proc )
   
A virtual filesystem. Hunting inside /proc/[pid]/ reveals open files, memory maps,
and environment variables for specific processes.

7 Device Handling ( /dev )

Represents hardware as files. Check for unusual device files or hidden directories within
/dev that might be used by rootkits.

Persistence & Services

8. Service Configurations
   
Service logic lives in /etc/systemd/system/ or /lib/systemd/system/ .
Hunting here helps identify auto-start persistence mechanisms.

9. Environment Configuration
    
Check /etc/environment , /etc/profile , and ~/.bashrc to see how PATH
variables and aliases are manipulated.
