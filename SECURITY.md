# Security Policy

## Overview

This repository documents the **Adjunct Faculty Contract Management System** as a technical portfolio project.

The repository is intended to demonstrate system architecture, workflow automation, data management, security-aware design, testing, and documentation.

It does **not** contain production credentials, confidential contracts, or real sensitive faculty information.

---

## Security Objectives

The project considers the following security objectives:

* Confidentiality
* Integrity
* Availability
* Access control
* Least privilege
* Data validation
* Secure document storage
* Auditability
* Minimization of unnecessary information exposure

---

## Sensitive Information

The following information must **never** be committed to this public repository:

* Passwords
* API keys
* Access tokens
* Authentication credentials
* Private keys
* Connection strings containing credentials
* Real faculty information
* Personally identifiable information (PII)
* Real contracts
* Confidential organizational documents
* Private SharePoint URLs
* Production configuration containing secrets

---

## Sanitized Portfolio Data

All examples included in this repository should use fictional or sanitized information.

For example:

```text
Faculty Name: Example User
Faculty ID: DEMO-001
Email: example@example.com
Contract ID: DEMO-CONTRACT-001
```

These values are for demonstration purposes only.

---

## Access Control

The system architecture incorporates access-control concepts to ensure that users receive only the access required for their responsibilities.

The design follows the principle of:

> Least privilege

Conceptually:

```text
User
  ↓
Authentication
  ↓
Authorization
  ↓
Required Resource
```

Access should be based on the user's role and responsibilities.

---

## Document Security

Contracts and related documents should be stored in controlled locations.

The intended workflow is:

```text
Generated Contract
       ↓
Review
       ↓
Electronic Signature
       ↓
Completed Contract
       ↓
Controlled Storage
```

Public GitHub documentation should not contain actual contract documents.

---

## Data Protection

Sensitive information should be protected throughout its lifecycle.

```text
Collection
    ↓
Processing
    ↓
Storage
    ↓
Access
    ↓
Retention
    ↓
Secure Disposal
```

Only information necessary for the business process should be collected and exposed.

---

## Workflow Security

Automated workflows should be designed with appropriate authorization and validation.

Security considerations include:

* Validating incoming data
* Restricting workflow access
* Preventing unauthorized modifications
* Preventing duplicate processing
* Controlling document access
* Monitoring workflow activity
* Protecting credentials and secrets

---

## Power Automate Security

Power Automate workflows should use appropriate authentication and permissions for connected services.

Credentials and connection information should never be stored directly in source files.

The public repository therefore contains workflow documentation and diagrams rather than authentication information.

---

## SharePoint Security

SharePoint should be configured using appropriate permissions for:

* Lists
* Libraries
* Documents
* Folders
* Users
* Groups

Access should be granted according to the user's responsibilities.

---

## DocuSign Security

Electronic-signature workflows should use the appropriate authentication, recipient, document, and permission controls provided by the signing platform.

No production DocuSign credentials or signing information should be stored in this repository.

---

## Power BI Security

Reports and dashboards should only expose information to authorized users.

Where sensitive data is involved, appropriate access controls should be implemented before publishing reports.

The public portfolio should use sanitized or fictional data.

---

## GitHub Repository Security

Before committing files, check for accidentally exposed secrets.

Example:

```bash
git status
```

Review files before committing:

```bash
git diff
```

Check the repository for potentially sensitive content before pushing.

Never commit files containing:

```text
.env
credentials
passwords
API keys
private keys
access tokens
connection strings
```

---

## Example `.gitignore`

A project can use a `.gitignore` file to prevent common sensitive or unnecessary files from being committed.

Example:

```gitignore
# Environment files
.env
.env.*
!.env.example

# Credentials
credentials.json
secrets.json
*.pem
*.key

# Local configuration
config.local.*
settings.local.*

# Operating system files
.DS_Store
Thumbs.db

# Editor files
.vscode/
.idea/
```

---

## Incident Reporting

If sensitive information is accidentally committed:

1. Stop sharing the repository contents.
2. Determine what information was exposed.
3. Revoke or rotate affected credentials immediately.
4. Remove the sensitive information from the repository history when appropriate.
5. Review access logs if available.
6. Notify the appropriate system owner or security team.
7. Document the incident and corrective action.

Simply deleting a secret from the latest commit may not be sufficient because it can remain in Git history.

---

## Vulnerability Reports

If a security issue is discovered in this portfolio repository, please report it through the repository's available GitHub security-reporting mechanism rather than publicly posting sensitive information in an issue.

Do not include:

* Passwords
* Access tokens
* Private keys
* Personal information
* Confidential documents

in a public issue.

---

## Security Testing

Security testing for the project can include:

```text
Data Validation
      ↓
Access Control Review
      ↓
Permission Review
      ↓
Workflow Testing
      ↓
Negative Testing
      ↓
Information Exposure Review
      ↓
Final Security Review
```

Testing should be performed only against systems and environments for which the tester has authorization.

---

## Portfolio Security Principles

This repository follows several basic security principles:

### 1. Least Privilege

Users should receive only the permissions necessary to perform their responsibilities.

### 2. Defense in Depth

Security should not depend on a single control.

### 3. Secure Configuration

Services should be configured with appropriate permissions and security settings.

### 4. Data Minimization

Avoid collecting or exposing information that is not required.

### 5. Separation of Secrets

Credentials should be stored using appropriate secret-management mechanisms rather than source code.

### 6. Auditability

Important workflow actions should be traceable when appropriate.

### 7. Secure Documentation

Public documentation should describe the architecture without exposing confidential implementation details.

---

## Security Disclaimer

This repository is a portfolio demonstration and should not be considered a complete production security assessment.

Organizations implementing a similar system should perform their own:

* Security assessment
* Risk assessment
* Privacy review
* Access-control review
* Compliance review
* Configuration review
* Penetration testing where appropriate

Security requirements should be based on the organization's environment, policies, regulatory requirements, and risk profile.

---

## Security Checklist

Before publishing changes:

* [ ] No passwords committed
* [ ] No API keys committed
* [ ] No access tokens committed
* [ ] No private keys committed
* [ ] No real personal information committed
* [ ] No real contracts committed
* [ ] No confidential documents committed
* [ ] No private production URLs exposed
* [ ] Example data is sanitized
* [ ] Documentation has been reviewed
* [ ] `.gitignore` is configured
* [ ] Repository contents have been reviewed before publishing

---

## Security Resources

For GitHub repository security guidance, refer to the official GitHub documentation.

For Microsoft Power Automate security and governance guidance, refer to the official Microsoft documentation.

The links should be added to the repository only from official sources and kept current as platform guidance changes.
