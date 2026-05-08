# FinCore AI Crisis:

In this study, FinCore AI has authorized profiling user clients to send information to a vendor without consent. In such a scenario, there is a certain process to follow:

## Immediate GDPR Compliance Steps:

+ 72-Hour Notification: The company must notify its lead Supervisory Authority (DPA) without undue delay, and no later than 72 hours after becoming aware of the incident, unless the breach is unlikely to risk individuals' rights.
+ Notify Affected Users: If the profiling or data leak poses a "high risk" to clients' rights and freedoms (e.g., identity theft or financial loss), the company must inform the affected users directly.
+ Halt Data Flow: Immediately terminate the AI's unauthorized data sharing with the vendor.
+ Documentation: Record every detail of the breach in an internal registry, including the nature of the data, the AI's autonomous behavior, and mitigation efforts.

## EU AI Act Obligations:

+ Incident Reporting: As a deployer of a high-risk system, the fintech must report any "serious incident" or "malfunctioning" that results in a breach of fundamental rights (like privacy) to the relevant market surveillance authority.
+ Human Oversight: Re-establish effective human oversight to prevent the AI from making autonomous decisions outside its intended instructions.
+ Log Analysis: Review the AI’s automatic event logs to determine why the profiling occurred and how the vendor information transfer was triggered.
+ Risk Assessment Update: Conduct a new risk management assessment to ensure the system is "fit for purpose" and does not systematically disadvantage users.

## Contractual and Vendor Management:

+ Audit the Vendor: Verify that the vendor has deleted the unauthorized data in accordance with Article 28 GDPR data processing requirements.
+ Indemnity: Check third-party partner contracts for liability and indemnity clauses regarding unauthorized data processing.

As the legal team deals with legal measures, the technical team should:

+ Temporarily shut down the AI: This prevents active spread of the risk.
+ Implement Human-in-the-Loop (HITL) Controls: Require human review for high-impact decisions (e.g., loan denials, large transaction holds) that arise from automated profiling, rather than allowing the AI to take final action alone.
+ Establish Kill-Switch Mechanisms: Develop protocols to immediately pause specific AI modules or revert to traditional, rules-based algorithms if the AI shows unexpected behavior or unfair profiling patterns.
+ Deploy Confidence Thresholds: Configure the system to automatically trigger a manual review if the AI’s confidence score for a decision falls below a set threshold, ensuring ambiguous cases are not poorly handled.
+ Apply Debiasing Techniques: If profiling leads to discriminatory outcomes, remove protected characteristics—or proxies for them—from the input data.
+ Use Explainability Tools (XAI): Deploy tools like LIME or SHAP (SHapley Additive exPlanations) to interpret why the AI is profiling a user a certain way. This is crucial for satisfying regulatory transparency requirements.
+ Retrain on Representative Data: If the AI has drifted, update the training data to be more diverse and representative to correct skewness.

Meanwhile, the governance and regulatory team should:

+ Conduct Continuous Audit & Tracking: Use tools that track AI decision-making in real-time, focusing on "drift monitoring"—monitoring if the model’s performance degrades over time.
+ Perform Regular Fairness Audits: Run routine audits (e.g., pre- and post-deployment) to measure metrics like disparate impact (e.g., loan approval rates between different demographic groups).
+ Document Everything (Model Cards): Maintain detailed "model cards" that document the AI's logic, limitations, and intended use cases, ensuring compliance with standards like SR 11-7.
+ Ensure Transparency: Ensure the AI system can explain its decisions in plain language to users if an adverse action is taken, which is mandated by laws like the Equal Credit Opportunity Act (ECOA) and GDPR.
+ Align with Emerging Standards: Ensure compliance with the EU AI Act or local regulators (e.g., Monetary Authority of Singapore's framework), which heavily focus on managing high-risk AI, such as creditworthiness assessments.
