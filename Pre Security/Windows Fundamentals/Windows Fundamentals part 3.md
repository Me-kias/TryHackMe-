WINDOWS FUNDAMENTALS 3 – NOTES

TASK 1 – INTRODUCTION
- Recap of Windows Fundamentals 1 & 2
- This room focuses on Windows security features
- Start the Windows machine (browser-based or via VPN)
- Read the overview and deploy the VM
- Task is informational only


TASK 2 – WINDOWS UPDATE
Purpose:
- Manage OS updates and security patches
- Microsoft releases patches monthly (Patch Tuesday = 2nd Tuesday)

How to open:
- Search: Windows Update
- Settings → Windows Update

Notes:
- VM has no internet, so no new updates will install
- Updates include security patches and bug fixes
- Windows may require restarts after updates

Task focus:
- Review installed updates
- Observe definition updates and installation dates


TASK 3 – WINDOWS SECURITY
Purpose:
- Central dashboard for Windows protection features

How to open:
- Settings → Windows Security
- Or search: Windows Security

Main sections:
- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

Status indicators:
- Green: No action required
- Yellow: Recommendation
- Red: Action required

Task focus:
- Identify which section needs attention


TASK 4 – VIRUS & THREAT PROTECTION
Sections:
- Current threats
- Scan options (Quick, Full, Custom)
- Threat history
- Allowed threats

Virus & threat protection settings:
- Real-time protection
- Cloud-delivered protection
- Automatic sample submission
- Controlled folder access
- Exclusions
- Notifications

Key notes:
- Real-time protection blocks active threats
- Automatic sample submission sends suspicious files to Microsoft
- Controlled folder access protects important directories
- Files can be scanned via right-click
- Ransomware protection uses controlled folder access

Task focus:
- Review settings and identify disabled protections


TASK 5 – FIREWALL & NETWORK PROTECTION
Purpose:
- Controls incoming and outgoing network traffic

Firewall profiles:
- Domain network
- Private network
- Public network

Each profile allows:
- Firewall enable/disable
- Blocking incoming connections

Additional features:
- Allow an app through firewall
- Advanced firewall rules

Command:
- wf.msc

Task focus:
- Understand when each network profile is used


TASK 6 – APP & BROWSER CONTROL
Purpose:
- Protect users from malicious apps, files, and websites

Features:
- Microsoft Defender SmartScreen
- Reputation-based protection
- Exploit protection

Exploit protection:
- Protects against memory-based attacks
- Prevents exploitation of applications
- Includes system-wide and per-app settings

Notes:
- Advanced configuration
- Changes should only be made by experienced users


TASK 7 – DEVICE SECURITY
Purpose:
- Hardware-level security protections

Features:
- Core isolation
- Memory integrity
- Security processor

Security processor:
- Handles cryptographic operations
- Protects sensitive data
- Helps prevent tampering

Task focus:
- Understand the role of hardware-based security


TASK 8 – BITLOCKER
Purpose:
- Full disk encryption
- Protects data if the device is lost or stolen

Notes:
- Works best with a TPM
- Not available in the attached VM
- Encrypts entire drives

Without TPM:
- Requires a startup key to unlock the drive

Task focus:
- Understand BitLocker requirements


TASK 9 – VOLUME SHADOW COPY SERVICE
Purpose:
- Creates system restore points and snapshots

Capabilities:
- Create restore points
- Restore system files
- Configure protection settings
- Delete restore points

Security notes:
- Malware may delete shadow copies
- Not a replacement for backups
- Offline backups are recommended

Task focus:
- Understand VSS purpose and limitations


TASK 10 – CONCLUSION
- Reviewed Windows security features
- Covered Defender, Firewall, BitLocker, TPM, and VSS
- Terminate machines after completion
- Continue with further Windows security learning
