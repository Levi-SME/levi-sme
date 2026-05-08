# Excessive Agency and Privilege Creep:

## How it's noticed:

+ Unusual API Call Patterns: The agent triggers APIs or tools it does not need for its primary task, such as a scheduling bot attempting to access HR salary databases.
+ Expansion of Action Capabilities: An agent designed to read data begins to "delete" or "edit" data, indicating a failure of least-privilege principles.
+ Zombie Agents: Orphaned agents that remain active and hold permissions long after their original project or purpose has ended.
+ Cross-Tenant Data Access: An AI agent in a multi-tenant SaaS environment attempts to access data from one customer while serving another.
+ Prompt Injection Exploits: The AI acts on hidden, malicious instructions within input data (e.g., an email with white-text commands) to extract or alter internal data.
+ Excessive Autonomy: High-impact, multi-step actions (e.g., making financial trades) occur without requiring human-in-the-loop approval.

## Mitigation Process:

### Immediate Remediation:

+ Conduct a Thorough Audit: Review all user accounts and entitlements, particularly for long-tenured employees who have changed roles multiple times.
+ Revoke Unnecessary Privileges: Immediately remove administrative rights, unused access, and lingering permissions from completed projects.
+ Reclaim Unused Permissions: Identify high-level access that has not been used over a specific period (e.g., 30–90 days) and remove it.
+ Address Non-Human Identities: Audit service accounts, bots, and API keys, which often hold overly broad permissions.
+ Temporary Suspension: If high-risk privilege misuse is suspected, temporarily suspend the account to investigate the scope of the impact.

### Structural & Process Mitigation:

+ Enforce the Principle of Least Privilege (PoLP): Grant users only the minimum access necessary to perform their current job functions, and nothing more.
+ Implement Role-Based Access Control (RBAC): Define access rights based on job roles rather than individuals, ensuring that when an employee changes roles, their access is updated automatically.
+ Deploy Privileged Access Management (PAM): Use PAM tools to manage high-level access, monitor sessions in real-time, and automatically revoke credentials after a set time (Just-in-Time access).
+ Establish Regular Access Reviews: Schedule automated quarterly or semi-annual access certifications where managers review and validate their team's entitlements.
+ Automate Deprovisioning: Implement automated workflows that remove access immediately when an employee changes departments or leaves the company.

### Mitigating Excessive Agency in AI/Systems:

+ Function Restriction: Limit plugin or AI agent actions to a strictly defined, narrow scope.
+ Human-in-the-Loop: Require manual human consent for critical, high-impact actions (e.g., transferring funds, changing security settings).
+ Verify Everything: Treat every tool call or API request from an agent as a security checkpoint, requiring re-authorization for sensitive actions.
