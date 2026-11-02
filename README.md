# Active-Directory-Security-Hardening-Lifecycle-Management
Enterprise-grade security hardening and lifecycle management project. Features a virtualised sandbox environment running Windows Server 2019 and Windows 10 client nodes. Orchestrates role-based access control across custom OUs and groups, and enforces strict NIST/CIS security compliance baselines via advanced Group Policy (GPO) engineering.

Objectives

• Build Sandbox Directory Infrastructure by deploying virtualized host configurations to mirror realistic corporate boundaries.
• Design and Structure a scalable Active Directory logical environment by segmenting business units into specialized Organizational Units (OUs).
• Implement Identity & Access Management (IAM) by creating domain user accounts and dynamically provisioning roles using Active Directory Security Groups.
• Enforce Compliance & Industry Standards (NIST and CIS benchmarks) across target OUs via custom Group Policy Objects (GPOs).
• Establish Defense-in-Depth Mechanisms via fine-grained account lockout thresholds, automated failed-logon event auditing, and structural time-fencing.
• Generate Validated Audit Trails using Resultant Set of Policy (RSOP) captures to prove deterministic security policy enforcement.

Tools and Technologies Used

• Virtualization Platforms: Oracle VirtualBox / VMware Workstation Hypervisor.
• Operating Systems: Windows Server 2019 Datacenter Edition (Domain Controller), Windows 10 Enterprise/Pro (Validation Client Node).
• Administrative Tooling Suite: Active Directory Users and Computers (dsa.msc), Group Policy Management Console (gpmc.msc), Resultant Set of Policy Engine (rsop.msc), Windows Network Connections Utility (ncpa.cpl).
• Security Baselines: National Institute of Standards and Technology (NIST) Guidelines, Center for Internet Security (CIS) Benchmarks.
• Command Line Interfaces: Windows Command Prompt (whoami).

Step-by-step Implementation


1. Virtualized Sandbox Provisioning & Base OS Deploys

• Provisioned standalone sandbox virtual environments to establish network validation parameters.
• Workstation Baseline: Deployed a Windows 10 x64 virtual machine instance from stock ISO media.
• Directory Server Baseline: Provisioned a Windows Server 2019 Datacenter virtual machine instance to host local directory services.
• Bypassed network interference boundary conditions across both components by switching off active structural processing on the internal profiles of the local Windows Defender Firewall panel.

2. Network Layout & Deterministic Naming Architecture

• Initialized the local system configuration adapter panel (ncpa.cpl) on the server node to bind static addressing constraints:
	• Static IPv4 Address: 192.168.91.145
	• Subnet Mask: 255.255.255.0
	• Default Gateway: 192.168.91.2
	• Loopback Loop Loop/Primary DNS Address: 192.168.91.145
• Modified structural machine identifying contexts inside the System Properties pane to enforce strict naming taxonomy:
	• Enforced server moniker state change to DC001.
	• Enforced workstation moniker state change to Client001.

3. Active Directory Forest Promotion

• Opened the Windows Server Manager platform interface, initializing the Add Roles and Features Wizard path.
• Target-installed the structural binaries matching Active Directory Domain Services (AD DS) alongside required administrative instrumentation binaries.
• Flagged the post-deployment configuration alert banner to promote the server host to a standalone functional state.
• Selected Add a new forest, anchoring the administrative boundaries to the Root Domain Namespace string: mydomain.local.
• Provisioned active functional forest baseline metrics set to Windows Server 2016 functional capability limits, allocating local password recovery protections.

4. Enterprise Client Node Integration

• Configured the static IP interface settings on Client001 to link targeting logic down to the local Domain Controller network block:
	• Static IPv4 Address: 192.168.91.143
	• Preferred DNS Address Binding: Explicitly mapped to 192.168.91.145 to enable successful local Active Directory SRV record lookups.
• Advanced into the system properties wrapper, changing node state mapping selections from local WORKGROUP boundaries explicitly over to Domain membership matching mydomain.local.
• Authenticated the boundary shift using privileged forest context markers (Administrator / Pa$$w0rd), validating the workstation addition.

5. Logical Environment Architecture (OUs & Groups)

• Executed dsa.msc via the Windows Run interface to launch the administrative hierarchy panel.
• Created two top-level Organizational Units under the root domain mydomain.local: Leadership and Research.
• Established functional Active Directory Security Groups nested inside the respective OUs:
	• Leadership OU: Nested groups CEO and CFO.
	• Research OU: Nested groups Junior Researchers and Senior Researchers.

6. Identity Creation & Role-Based Access Control (RBAC)

• Provisioned standard enterprise domain accounts (sam, david) under the default Users container.
• Stripped user self-modification flags during the onboarding process by enforcing custom credential states.
• Implemented RBAC mappings by binding the unique user entities explicitly to their respective organizational security contexts:
	• Bound user sam to the CEO global security group.
	• Bound user david to the Junior Researchers global security group.

7. Granular Group Policy & Security Control Engineering

• Launched gpmc.msc to configure domain scope controls.
• Generated separate GPO containers labeled Leadership and Research to target baseline deviations.
• Configured password complexities according to explicit baseline benchmarks:
	• Leadership GPO: Enforced an 8-character minimum policy aligning with legacy NIST guidelines.
	• Research GPO: Configured strict CIS compliance including a 14-character minimum password length, 90-day maximum age lifecycle, 72-day minimum age restriction, and active history tracking (5 passwords remembered).
• Configured target-specific time-fences on the user object properties panel, locking Junior Researchers (e.g., user david) out of the domain network except between the core operational window of 7:00 AM to 7:00 PM.
• Modulated the Default Domain Policy object to achieve universal endpoint hardening across the forest infrastructure:
	• Auditing: Enabled Advanced Audit Policy Configuration under Account Logon, explicitly tracking both Success and Failure variations of Audit Other Account Logon Events.
	• Lockout Policy: Standardised the threshold value to 3 invalid logon attempts, anchoring a strict 1440-minute (24-hour) account lockout duration and a 10-minute reset window.

Vulnerability Mapping


Target System Component	Discovered Vulnerability / Risk	Implemented GPO / AD Mitigation	Enforced Standard
Domain Authentication Path	Brute-force attacks & credential stuffing due to lack of a strict lockout threshold.	Enforced 3 invalid attempts account lockout threshold with a 24-hour lockout length.	Defense-in-Depth
Research Data Store	Lateral movement or insider threats operating undetected during off-business hours.	Hardened access vectors by explicitly restricting target logins to 7:00 AM – 7:00 PM.	Least Privilege / Time-Fencing
Corporate Identity Set	Weak or easily guessable user credentials exposed to dictionary attacks.	Mandated 14-character minimum complex password requirements with lifetime tracking.	CIS Benchmarks
Security Auditing Engine	Silent security baseline failures due to lack of forensic trails on anomalous logon attempts.	Activated strict logging parameters capturing all failed authentication attempts globally.	NIST / Audit Compliance


Verification and Defensive Validation


1. Authentication Path Validation

• Validated cross-platform connectivity by successfully passing credentials from a Windows 10 workstation node up to the parent mydomain.local directory server.
• Executed the command-line probe whoami to verify deterministic host context binding (mydomain\administrator and mydomain\sam).

2. Time-Fence Boundary Enforcement Test

• Attempted off-hours authentication using the account david@mydomain.local.
• The system triggered an explicit kernel rejection message confirming that the account has time restrictions preventing sign-in at that time.

3. Account Lockout Validation Test

• Simulated a brute-force attack vectors on user sam by passing intentional invalid credentials three consecutive times.
• The domain controller successfully locked out the identity, returning an explicit security notification stating that the referenced account is currently locked out.

4. Deterministic GPO Audit Verification

• Executed rsop.msc to parse local policy application chains and exported definitive runtime reports.
• Reviewed the verified HTML report outputs, confirming absolute compliance execution states including the active 8-character and 14-character minimum barriers across targeted structural endpoints.

Key Takeaways

• Segmented Architecture Restricts Blast Radii: Segmenting assets using distinct OUs prevents global compromise if a single business group is breached.
• Baseline Alignment Mitigates Identity Risks: Implementing standardized CIS and NIST guidelines significantly reduces an organization's exposure to common credential attacks.
• Proactive Fencing Reduces Attack Surfaces: Implementing automated constraints, such as time-based logons, minimizes open windows of vulnerability without requiring manual administrative tracking.
• Continuous Auditing Ensures Forensics: Hardening auditing policies ensures that defensive operators maintain clear visibility into anomalous events, making malicious operations easy to detect and analyze.
