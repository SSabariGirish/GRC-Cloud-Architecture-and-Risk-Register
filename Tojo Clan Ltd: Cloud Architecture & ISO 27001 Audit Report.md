# **Tojo Clan Ltd: Cloud Architecture & ISO 27001 Audit Report**


# **AWS Environment Overview** 

To support its highly confidential operations, Tojo Clan UK Ltd. relies on a streamlined Amazon Web Services (AWS) cloud environment. This infrastructure is designed to handle Identity and Access Management (IAM), secure document storage, and continuous auditing. 


### **Identity & Access Management (IAM)**

The digital hierarchy within the organization is enforced through AWS IAM, with three specific user accounts established for core personnel: 

- _Daigo\_Patriarch_: Designated as the Global Administrator, possessing Full Access privileges. 

- _Majima\_Lieutenant_: Designated as the Cloud Engineer, responsible for Storage Management. 

- _Kiryu\_Officer_: Designated as a Standard Operative, restricted to Read-Only Access. 

Current State of Accounts: While accounts have been provisioned, formal policies and granular permissions have not yet been attached. 


### **Cloud Storage (Amazon S3)**

Classified organizational data is maintained within two primary S3 buckets: 

- Secure Vault (_tojoclan-client-dossiers-sec-001_): 

  - Configuration: "Block all public access" is enabled with SSE-S3 default encryption active. 

  - Purpose: Serves as the repository for high-sensitivity VIP itineraries and threat intelligence. 

- Temporary Roster (_tojoclan-operative-roster-temp-001_): 

  - Configuration: "Block all public access" has been intentionally disabled. 

  - Purpose: A short-term holding area containing _operative\_addresses\_Q1.txt_, which lists personal details and addresses of clan operatives. 


### **Monitoring & Logging (AWS CloudTrail)**

To ensure continuous oversight of digital activities, AWS CloudTrail is utilized: 

- The Patriarch's Ledger: The "Patriarchs-Ledger-Trail" is deployed to log standard AWS management events and API activity. 

- Configuration: Audit logs are forwarded to an isolated S3 bucket for secure, tamper-proof retention. 


### **Control 5.15 (Access Control):** 

- Status: **Gap Identified**

- Audit Finding: IAM users (Daigo\_Patriarch, Majima\_Lieutenant, Kiryu\_Officer) have been created, but formal Role-Based Access Control (RBAC) policies have not been attached. This violates the principle of least privilege, as permissions might be granted ad-hoc in the future. 


### **Control 8.3 (Information Access Restriction):** 

- Status: **Critical Non-Compliance**

- Audit Finding: The S3 bucket (_tojoclan-operative-roster-temp_) is currently configured to allow public read access, exposing the Personally Identifiable Information (PII) of clan operatives. This represents a severe lapse in access control and places the organisation in direct breach of UK GDPR, incurring significant regulatory and reputational risk.


### **Control 8.15 (Logging):** 

- Status: **Compliant**

- Audit Finding: AWS CloudTrail is operational across the environment. Management events are actively logged and forwarded to an isolated S3 repository, satisfying requirements for monitoring, anomaly detection, and non-repudiation.
