# **Tojo Clan Ltd: Audit Resolution & Remediation Report**


# **Executive Summary**

Following the Q2 2026 Governance, Risk, and Compliance (GRC) audit of the Tojo Clan Ltd. AWS environment, two critical vulnerabilities were identified regarding data exposure and access control. Immediate remediation actions have been successfully executed by the Cloud Engineering team. The infrastructure is now fully compliant with internal security policies, UK GDPR requirements, and ISO 27001:2022 access control standards.


## **Remediation Actions Executed**

### **1. Resolution of RSK-001 (Critical): Public Data Exposure**

- **Vulnerability:** The Amazon S3 bucket _tojoclan-operative-roster-temp_ was publicly accessible, exposing highly sensitive Personally Identifiable Information (PII) of clan operatives.

- **Action Taken:** The bucket permissions were immediately modified. The "Block All Public Access" configuration was successfully enforced at the bucket level, overriding any existing ACLs or bucket policies that permitted public read access.

- **Status:** **CLOSED**. The data is now secured and compliant with UK GDPR Article 32.

- **Evidence of Remediation:** 

<img width="602" height="278" alt="S3Remediation" src="https://github.com/user-attachments/assets/c6eafa0b-382b-4f94-8438-44cf700db787" />



### **2. Resolution of RSK-002 (High): Lack of Role-Based Access Control (RBAC)**

- **Vulnerability:** AWS Identity and Access Management (IAM) users were provisioned without formal policies, violating the Principle of Least Privilege.

- **Action Taken:** A formal Role-Based Access Control (RBAC) structure was implemented using IAM User Groups. Strict, principle-of-least-privilege policies were attached to these groups, and personnel were assigned accordingly:

  - Patriarchs\_Admin: Assigned **_AdministratorAccess_** (User: _Daigo\_Patriarch_)

  - Lieutenants\_CloudEng: Assigned **_AmazonS3FullAccess_** (User: _Majima\_Lieutenant_)

  - Officers\_ReadOnly: Assigned **_AmazonS3ReadOnlyAccess_** (User: _Kiryu\_Officer_)

- **Status:** **CLOSED**. The environment now satisfies ISO 27001 Control A.5.15 (Access Control).

- **Evidence of Remediation:** 

<img width="602" height="209" alt="IAMRemediation" src="https://github.com/user-attachments/assets/83f98c51-8398-47cf-8aac-3eb8f85d4912" />


***

**Audit Officially Closed By:** Sabari Girish Srinivasan, GRC Analyst.
