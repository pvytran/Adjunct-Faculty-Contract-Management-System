# Adjunct Faculty Contract Management System

## Project Overview

A Microsoft 365-based solution designed to streamline adjunct faculty contract management through centralized data, automated contract generation, electronic signatures, secure document storage, and reporting.

The system replaces manual, disconnected processes with an integrated workflow using **SharePoint, Power Automate, Microsoft Word, DocuSign, and Power BI**.

> **Portfolio Project:** This repository contains sanitized documentation and fictional sample data for demonstration purposes. No real faculty or contract information is included.

---

## Problem

The original process relied on multiple data sources and manual steps for:

* Collecting faculty and course information
* Preparing contracts
* Routing contracts for review and approval
* Obtaining electronic signatures
* Tracking contract status
* Storing completed contracts
* Producing status reports

This created opportunities for duplicate records, data-entry errors, delayed contracts, and limited visibility into contract status.

---

## Solution

The proposed system centralizes contract-related information in SharePoint and uses Power Automate to automate the workflow.

### Workflow

```text
Faculty & Course Data
        ↓
SharePoint
        ↓
Power Automate
        ↓
Contract Generation
        ↓
Review / Approval
        ↓
DocuSign
        ↓
Signed Contract Storage
        ↓
Power BI Reporting
```

---

## Technology Stack

| Technology     | Purpose                               |
| -------------- | ------------------------------------- |
| SharePoint     | Centralized data and document storage |
| Power Automate | Workflow automation and routing       |
| Microsoft Word | Contract template generation          |
| DocuSign       | Electronic signatures and audit trail |
| Power BI       | Reporting and status dashboards       |

---

## Key Features

### Centralized Data Management

* Faculty information stored in SharePoint
* Course and section information maintained in structured lists
* Contract records linked to faculty and course information

### Automated Contract Generation

* Contract information is collected from centralized data
* Power Automate processes contract requests
* Microsoft Word templates are populated with contract information

### Electronic Signatures

* Contracts are routed through DocuSign
* Signature status can be tracked
* Completed documents are stored for future reference

### Status Tracking

The workflow supports tracking contract progress through stages such as:

```text
Generated
   ↓
Review
   ↓
Approval
   ↓
Signature
   ↓
Completed
```

### Reporting

Power BI provides reporting and visibility into contract activity and status.

---

## Security Considerations

Security was considered throughout the system design.

Key considerations include:

* Least-privilege access
* Role-based access control
* Controlled SharePoint permissions
* Secure document storage
* Protection of contract-related information
* Validation of imported data
* Duplicate-record prevention
* Avoiding sensitive information in the public GitHub repository

See [Security and Compliance](docs/security-and-compliance.md) for additional details.

---

## Architecture

The system architecture and component relationships are documented here:

[View System Architecture](architecture/system-architecture.md)

---

## Workflows

Detailed workflow documentation:

* [Data Collection](workflows/data-collection.md)
* [Contract Generation](workflows/contract-generation.md)
* [Signing and Reporting](workflows/signing-and-reporting.md)

---

## Example Data

The `examples/` directory contains fictional data demonstrating the structure of the system:

* `sample-faculty-data.csv`
* `sample-course-data.csv`
* `sample-contract-data.csv`

All example information is fictional and intended only for portfolio demonstration.

---

## Testing

Testing documentation covers workflow validation and functional testing of major system components.

[View Testing Documentation](docs/testing.md)

---

## Project Contribution

My project work included requirements analysis, system design, SharePoint data organization, workflow automation, contract generation, electronic-signature integration, status tracking, reporting, testing, and security-aware documentation.

[View Project Contribution](docs/project-contribution.md)

---

## Skills Demonstrated

**Cybersecurity & IT**

* Access Control
* Data Security
* Security-Aware System Design
* Risk Management
* Data Validation
* Secure Document Management

**Microsoft 365**

* SharePoint
* Power Automate
* Power BI
* Microsoft Word

**Additional Skills**

* Workflow Automation
* Requirements Analysis
* System Design
* Data Management
* Testing
* Documentation

---

## Repository Structure

```text
adjunct-faculty-contract-management-system/
│
├── README.md
├── SECURITY.md
├── .gitignore
│
├── architecture/
│   └── system-architecture.md
│
├── workflows/
│   ├── data-collection.md
│   ├── contract-generation.md
│   └── signing-and-reporting.md
│
├── examples/
│   ├── sample-faculty-data.csv
│   ├── sample-course-data.csv
│   └── sample-contract-data.csv
│
└── docs/
    ├── README.md
    ├── security-and-compliance.md
    ├── testing.md
    └── project-contribution.md
```

---

## Portfolio Purpose

This repository demonstrates practical experience with **workflow automation, Microsoft 365 technologies, data management, security-aware system design, testing, and technical documentation**.

The project is documented using sanitized information and fictional sample data to protect sensitive information.
