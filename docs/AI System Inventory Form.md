# Fortress Finance: FinCore AI Inventory Form:

| Agent Name | Agent Version | Functional Goal | Autonomy Level | Decision Logic | Tool List and External Access | Guardrails and HITL Triggers | Auditability and Logging | Risk Profile \
| :---: | :---: | :--- | :---: | :--- | :--- | :--- | :--- | :---: |
| AML-Sentry | v 4.0 | Real-time suspicious activity monitoring and SAR filing. | High | Heuristic + ML Pattern Matching. | Transaction Ledger, Sanctions Lists. | Trigger if transaction >$50k or PEP match. | Immutable WORM log of every thought. | Critical |
| Credit-Quant | v 2.0 | Automated credit scoring and loan underwriting. | Medium | RAG-enhanced Credit Policy Reasoning. | Credit Bureaus, Income APIs. | Reject logic for bias; Max loan $25k | Explainability report for every score | High |
| Trade-Executor | v 5.3 | High-frequency portfolio rebalancing and execution. | High | Reinforcement Learning | Trading APIs (FIX) Market Feeds | Drawdown limit (5%); Max position sizePer-millisecond execution audit | Critical |
| KYC-Onboarder | v 1.2 | Automated document verification and identity liveness. | Medium | Computer Vision + OCR Verification | Government ID Databases | Fail if confidence < 95% or manual flag | Side-by-side evidence capture | High |
| Wealth-Advisor | v 3.0 | Personalized robo-advisory and investment planning. | Low | Goal-Based Optimization Models | Portfolio Mgmt System (Internal) | Portfolio risk > Client profile limit | Suitability check audit trail | Moderate |
| Debt-Collector | v 1.5 | Autonomous outreach for delinquency management. | Medium | NLP + Sentiment Analysis | CRM, VoIP (Twilio), Stripe API | Stop if sentiment: "Hostile" or "Lawyer" | Full transcript and action trace | High |
| Claim-Adjuster | v 2.1 | Processing and settling fintech insurance claims. | Medium | Policy-Aware Reasoning Loop | Policy DB, Payout API | Settlement >$5k requires 2nd human | Rationale for each payout/denial | Moderate |
| Tax-Compliance | v 1.0 | Auto-generating 1099/K-1 tax forms for users. | Low | Tax Code RAG (US/UK/EU)User Ledger, Tax Filing API | Flag for manual review if logic conflict | Verifiable data provenance logs | High |
