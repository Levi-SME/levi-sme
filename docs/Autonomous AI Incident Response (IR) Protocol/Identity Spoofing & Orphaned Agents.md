# Identity Spoofing & Orphaned Agents:

## How it's noticed:

+ Behavioral Deviations: Agents suddenly executing tasks outside their established baseline—such as accessing sensitive data, changing configurations, or interacting with new endpoints.
+ Failed Authentication/Unauthorized Access: A rise in 403 Forbidden errors or anomalous access patterns from a trusted agent identity.
+ Unexpected Persona Shifts: The agent begins taking actions not authorized by its original "human-in-the-loop" or starts interacting with different departments.
+ Credential Reuse: Detection of the same AI credentials being used simultaneously in different geographical locations or across different, unrelated applications.
+ Weak Authentication Exploits: Identification of tools using static API keys or hardcoded secrets, which are easy for attackers to steal and use for impersonation.
+ Unowned Agents in Inventory: Discovering AI agents that do not map to any active employee, project, or IT system.
+ Stale or Persistent Activity: Agents that never shut down or that continue to make API calls to external systems long after a project has finished.
+ Privilege Creep: Agents maintaining or acquiring elevated, root permissions, even when their intended function required minimal access.
+ Unusual Data Exfiltration: Slow, continuous, and subtle data transfers initiated by an agent that no one is actively monitoring.
+ Documentation Failure: Inability to locate documentation or identify the responsible party for a particular agent.
+ Identity Threat Detection & Response (ITDR): Using ITDR to continuously monitor for anomalous behavioral patterns and privilege escalation.
+ Mutual Authentication (mTLS): Requiring unique credentials for every agent and enforcing mutual authentication between agents and external systems to prevent spoofing.
+ Continuous Monitoring and Behavioral Baselines: Establishing a behavioral norm for each agent (times of operation, types of queries) and flagging deviations.
+ Regular Audits of Non-Human Identities (NHI): Auditing API keys, service accounts, and tool access to identify unused or high-risk shadow AI agents.

## Mitigation Process:

## A) Identitu Spoofing:

### Immediate Isolation & Blocking:

+ Email Spoofing: Activate SPF, DKIM, and DMARC protocols. Immediately set DMARC policies to ensure spoofed emails are dropped by recipients.
+ Regular Audits of Non-Human Identities (NHI): Auditing API keys, service accounts, and tool access to identify unused or high-risk "shadow AI" agents.

### Credential and Session Reset:

+ Force a password change on the potentially compromised account.
+ Revoke all active sessions (tokens) for that user, requiring re-authentication via MFA.

### Notification and Reporting:

+ Notify stakeholders, including IT security teams and, if necessary, customers.
+ Report the incident to the appropriate authorities (e.g., FTC, local police).

### Analysis and Forensic Investigation:

+ Review system logs to identify how the breach occurred and what data was accessed.

## B) Orphaned Agents:

### Immediate Quarantining:

+ Immediately disable the agent's permissions rather than deleting it immediately, in case it is still performing a critical, unknown function.
+ Restrict network access for the agent, placing it into a quarantine group.

### Ownership Assignment & Auditing:

+ Identify the creator (creator/owner) of the agent.
+ Audit the agent’s credentials and access scope (privilege level).
+ Compare the agent's actual permissions against its stated purpose.

### Deprecation and Decommissioning:

+ Transition the agent into a formal deprecation phase, where its availability is limited while its impact is assessed.
+ Remove unused agents, or update them to align with current security policies (e.g., least-privilege model).

### Permanent Remediation:

+ Create a dead man's switch policy where unused agents are automatically disabled after a set period.
+ Integrate HR/IT onboarding and offboarding systems to automatically deprovision agents when employees leave.

### Long-Term Measures:
+ Enforce Least Privilege & RBAC: Implement Role-Based Access Control (RBAC) so that if a user account becomes orphaned, it has limited lateral movement opportunity.
+ Continuous Monitoring: Use AI-driven behavioral analytics to detect anomalous activity, such as a user suddenly accessing high-sensitivity data or a service agent connecting from an unknown IP.
+ Regular Access Reviews: Perform quarterly reviews of both human and non-human identities to identify and remove unused accounts.
+ Employee Awareness Training: Train users to identify phishing, spoofing, and unauthorized requests.
