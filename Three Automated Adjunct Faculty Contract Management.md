# Three Automated Adjunct Faculty Contract Management Workflows

## Project Context

The project designed an automated adjunct faculty contract-management solution to streamline the collection of faculty information, contract preparation, electronic signing, and contract tracking. The solution connects structured data storage with Power Automate, Microsoft Word templates, SharePoint, DocuSign, and Power BI.

The three workflows are:

1. Data Collection & Validation
2. Contract Generation
3. Electronic Signing & Reporting

The workflows are connected: validated faculty data becomes the source for contract generation, and contract-signing activity updates the records used for reporting.

---

## 1. Data Collection & Validation

### Purpose

The purpose of this workflow is to collect adjunct faculty and course information, validate the data before it is used, and store reliable records in a centralized location.

### Workflow Steps

1. **Collect information from stakeholders**

   * The administrative specialist gathers faculty information.
   * The department chair provides course numbers, course sessions, and the number of courses being taught.
   * Faculty members provide demographic information and identify information that needs to be updated.

2. **Enter or import information**

   * The information is entered into a structured Excel source or another approved data-entry interface.
   * Each faculty record is associated with a unique identifier, such as the faculty G-number.

3. **Trigger the validation flow**

   * Power Automate reads the submitted or imported record.
   * The flow checks whether the record contains the required information.

4. **Validate the record**

   * The flow checks for missing fields.
   * It validates the faculty G-number.
   * It checks for missing pay rates or course information.
   * It checks for duplicate records.

5. **Handle invalid information**

   * If the record contains errors, the administrative specialist is asked to correct the information.
   * The record goes through validation again before it can continue to contract generation.

6. **Store validated data**

   * Validated information is stored in a centralized SharePoint-based data source or the selected structured database.
   * The record is assigned a processing status to distinguish it from records that still require review or processing.

### Data Flow

**Administrative Specialist / Department Chair / Faculty**
→ **Excel or data-entry interface**
→ **Power Automate validation flow**
→ **Required-field checks**
→ **G-number validation**
→ **Duplicate detection**
→ **Correction loop if invalid**
→ **Validated record stored in SharePoint, Excel, or Dataverse**

### Automation and System Design Evidence

This workflow demonstrates:

* Event-driven automation
* Structured data collection
* Required-field validation
* Unique-identifier matching
* Duplicate detection
* Conditional logic
* Exception handling
* Centralized storage
* Separation of data validation from contract generation

The project requirements specifically identify validation of G-numbers, missing pay rates, and duplicate records as part of the automated workflow.

### Security Considerations

The project identified data security and HIPAA-related network concerns as important business challenges. For a production implementation, access to faculty records should be restricted according to user roles. Sensitive information should not be unnecessarily copied into contracts, email messages, or reporting dashboards.

The workflow supports this design by separating the complete source record from the limited information needed for contract generation.

---

## 2. Contract Generation

### Purpose

The purpose of this workflow is to automatically create a standardized contract from validated faculty and course information while retaining an administrative review step before the contract is sent for signature.

### Workflow Steps

1. **Identify an eligible record**

   * Power Automate retrieves a validated faculty record.
   * The flow uses the faculty G-number or another unique identifier to locate the correct information.

2. **Retrieve contract data**

   * The flow retrieves the faculty’s name, address, salary, course information, and teaching schedule.
   * Salary information is determined according to the project’s defined process:

     * If the faculty member qualifies for a pay increase, the department chair provides a new salary calculation.
     * If not, the previous contract salary may be used.

3. **Populate the Word template**

   * Power Automate maps the source fields to predefined placeholders in a Microsoft Word contract template.
   * The flow inserts the appropriate faculty, compensation, and teaching-assignment information.

4. **Create the contract**

   * A completed Word document is generated.
   * The document is saved in SharePoint.

5. **Update the source record**

   * The record is marked with a status such as **Generated**.
   * This status helps prevent the same faculty record from generating multiple contracts.

6. **Complete administrative review**

   * The administrative specialist reviews the generated contract.
   * Authorized users can correct errors before the document is sent for signing.
   * The document is revalidated after changes.

7. **Route the contract**

   * Once reviewed, Power Automate sends the contract to DocuSign for electronic signing.

### Data Flow

**Validated faculty record**
→ **Power Automate retrieves record by unique ID**
→ **Salary and course information assembled**
→ **Word template placeholders populated**
→ **Completed contract generated**
→ **Contract saved in SharePoint**
→ **Record marked Generated**
→ **Administrative review**
→ **Approved contract sent to DocuSign**

### Automation and System Design Evidence

This workflow demonstrates:

* Data-to-document transformation
* Field mapping
* Template-based document generation
* Unique-record lookup
* Conditional salary logic
* Automated file creation
* Status tracking
* Duplicate-processing prevention
* Human-in-the-loop review
* Integration between structured data and document systems

The project prototype documents Power Automate extracting information from Excel, inserting the information into a Word contract template, and saving the completed contract in SharePoint.

The project requirements also specify that contracts must populate the correct placeholders, be reviewed by an administrative specialist, and be marked as generated to prevent duplicate processing.

### Security Considerations

The workflow should restrict access to:

* Faculty source records
* Contract templates
* Generated contracts
* Salary information
* Contract-editing and approval functions

SharePoint permissions and version history can support controlled access and document accountability. A human review checkpoint also reduces the risk of sending an incorrect contract to an external signer.

---

## 3. Electronic Signing & Reporting

### Purpose

The purpose of this workflow is to route contracts for electronic signature, automate follow-up activities, store completed contracts, and provide visibility into contract progress.

### Workflow Steps

1. **Send the approved contract**

   * Power Automate sends the reviewed contract to DocuSign.
   * DocuSign manages the signing experience for the required recipients.

2. **Route the contract to signers**

   * The contract follows the defined signing sequence.
   * Required signers review and sign the contract electronically.

3. **Monitor contract status**

   * The workflow tracks whether the contract is pending, signed, declined, or incomplete.
   * The status information is used to determine the next action.

4. **Send reminders**

   * Power Automate checks for contracts that remain unsigned.
   * The flow sends reminders when the required condition is met.
   * The project design allows up to three reminders.

5. **Handle expired or incomplete contracts**

   * If the contract is still unsigned after the reminder limit, it can be marked as expired or requiring administrative follow-up.
   * The administrative specialist can determine whether additional action is needed.

6. **Store the signed contract**

   * Completed contracts are saved in SharePoint.
   * The related record is updated with the final signing status and completion information.

7. **Update reporting information**

   * Contract status and progress information are made available to Power BI.
   * The dashboard provides visibility into completed, pending, and outstanding contracts.

### Data Flow

**Approved contract in SharePoint**
→ **Power Automate sends contract to DocuSign**
→ **DocuSign routes contract to required signers**
→ **Signing events update contract status**
→ **Power Automate checks reminder conditions**
→ **Reminder or expiration path if incomplete**
→ **Signed contract saved in SharePoint**
→ **Record status updated**
→ **Power BI dashboard displays progress**

### Automation and System Design Evidence

This workflow demonstrates:

* Integration with an external electronic-signature platform
* Sequential multi-party routing
* Condition-based automation
* Automated reminders
* Expiration and escalation logic
* Document lifecycle tracking
* Centralized storage
* Transactional status updates
* Reporting data preparation
* Separation of operational processing from analytics

The project’s finished-product overview identifies DocuSign as the signing platform, Power Automate as the reminder mechanism, SharePoint as the storage location, and Power BI as the reporting tool.

The project also describes sequential signing, automated notifications, reminders, completion metrics, and an expiration condition after the third reminder.

### Security and Audit Considerations

An electronic-signature workflow should preserve:

* Recipient authentication
* Controlled access to contracts
* Secure transmission of documents
* Signature timestamps
* Signing history
* Reminder and expiration events
* Final signed-document storage
* Role-based access to reports

Power BI reports should focus on operational information such as contract status, pending signatures, completion dates, and outstanding actions without unnecessarily displaying sensitive personal information.

---

## End-to-End System Design

The three workflows create a connected process:

**Source information**
→ **Data Collection & Validation**
→ **Validated faculty record**
→ **Contract Generation**
→ **Reviewed contract**
→ **Electronic Signing**
→ **Signed contract and updated status**
→ **SharePoint storage and Power BI reporting**

### System Responsibilities

| System                                | Primary Responsibility                                                                                |
| ------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Excel, Power Apps, or structured form | Collect faculty and course information                                                                |
| SharePoint, Excel, or Dataverse       | Store structured records                                                                              |
| Power Automate                        | Validate records, move data, generate documents, route contracts, send reminders, and update statuses |
| Microsoft Word                        | Provide the standardized contract template                                                            |
| DocuSign                              | Manage electronic signing and signer routing                                                          |
| SharePoint                            | Store generated and completed contracts                                                               |
| Power BI                              | Display contract status and progress                                                                  |

## Recruiter-Facing Summary

Designed and prototyped an automated adjunct faculty contract-management solution that connected structured data collection, validation, document generation, electronic signing, and reporting. Built the workflow logic around required-field and G-number validation, duplicate detection, unique-record matching, Word template population, SharePoint document storage, DocuSign routing, automated reminders, expiration handling, and Power BI status reporting. The project demonstrates practical understanding of **automation, data flow, system integration, security controls, human approval checkpoints, document lifecycle management, and reporting architecture**.
