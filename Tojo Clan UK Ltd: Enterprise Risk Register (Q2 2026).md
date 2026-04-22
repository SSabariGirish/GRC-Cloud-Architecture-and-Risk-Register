**Tojo Clan UK Ltd: Enterprise Risk Register (Q2 2026)** 


### **Risk Scoring Matrix:**

- **Likelihood:** 1 (Rare) to 5 (Almost Certain)

- **Impact:** 1 (Negligible) to 5 (Catastrophic)

- **Risk Level:** 1-5 (Low) | 6-10 (Medium) | 12-16 (High) | 20-25 (Critical)


### **Risk ID: RSK-001 | Public Data Exposure via Misconfigured S3 Bucket**

- **Asset Affected:** Amazon S3 Bucket (_tojoclan-operative-roster-temp-001_)

- **Vulnerability Description:** S3 bucket permissions are misconfigured to allow public read access, exposing highly sensitive employee Personally Identifiable Information (PII) and physical addresses.

- **Threat Actor:** Rival syndicates, cybercriminals, and automated AWS bucket scrapers.

- **Risk Scoring:** Likelihood: 5 (Almost Certain) | Impact: 5 (Catastrophic)

- **Total Risk Score:** **25 (CRITICAL)**

- **Mitigation Strategy & Treatment Plan:**

  - _Immediate Action:_ Reconfigure S3 settings to "Block All Public Access".

  - _Long-Term Strategy:_ Implement AWS Config rules to auto-remediate public buckets and trigger alerts to leadership via AWS Security Hub.

- **Risk Owner:** _Majima\_Lieutenant_ (Cloud Engineer)

***


### **Risk ID: RSK-002 | Lack of Role-Based Access Control (RBAC) in IAM**

- **Asset Affected:** AWS Identity and Access Management (All User Accounts)

- **Vulnerability Description:** IAM users have been provisioned without formal policies attached. This violates the Principle of Least Privilege and creates undefined access states within the cloud environment.

- **Threat Actor:** Insider threats (rogue operatives) or external attackers compromising standard user credentials to pivot to administrative roles.

- **Risk Scoring:** Likelihood: 3 (Possible) | Impact: 4 (Major)

- **Total Risk Score:** **12 (HIGH)**

- **Mitigation Strategy & Treatment Plan:**

  - _Immediate Action:_ Draft and attach strict IAM policies based on operational rank and required duties.

  - _Long-Term Strategy:_ Enforce mandatory Multi-Factor Authentication (MFA) for all AWS Management Console access.

- **Risk Owner:** _Daigo\_Patriarch_ (Global Admin)
