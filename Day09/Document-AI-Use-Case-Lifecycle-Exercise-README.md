# Topic 2.1 — Exercise: Map Your Own Use Case Onto the Lifecycle

## Use Case: Enterprise Document AI for Data Remediation

### Use Case Summary

**Document AI Capability** — Establish an enterprise document ingestion,
classification, extraction, summarization, validation, and Human-in-the-Loop
(HiTL) review capability that supports document-centric business processes.

For this lifecycle exercise, the selected use case is:

> **Enterprise Data Remediation Use Case** — Use Document AI to process
> enterprise documents, automatically extract required information,
> validate the extracted data, identify exceptions, and route exceptions
> to human reviewers for resolution.

The solution can use reusable **Human-in-the-Loop (HiTL)** capabilities such
as reviewer workflows, work queues, role-based access control, exception
management, and approval workflows.

---

# 9-Stage Lifecycle Map

| # | Lifecycle Stage | What Happens for This Use Case | Artifact Produced |
|---|---|---|---|
| 1 | **Ideation** | The business identifies manual document-processing and data-remediation work as a problem and proposes Document AI to automate extraction, validation, and exception handling. | **One-page problem statement** |
| 2 | **Intake** | The team formally documents the document types, data sources, extracted fields, affected users, expected level of automation, and whether sensitive/PII data is involved. | **Completed intake form** |
| 3 | **Risk Tiering** | The use case is assessed against the organization's risk-tiering framework based on its data, users, autonomy, and potential business impact. | **Documented risk tier + rationale** |
| 4 | **Design** | The team designs the Document AI architecture, including ingestion, classification, extraction, validation, exception handling, HiTL review, security controls, and system integrations. | **Architecture diagram + ADRs** |
| 5 | **Build** | Developers implement the approved Document AI workflow, including document ingestion, classification, extraction, validation rules, exception queues, and reviewer workflows. | **Working code + test results** |
| 6 | **Validate** | An independent validation team tests the solution against requirements, including extraction accuracy, validation behavior, exception handling, access controls, and HiTL workflows. | **Independent validation report** |
| 7 | **Deploy** | After required approvals, the Document AI solution is released in a controlled manner, potentially starting with a pilot before wider rollout. | **Deployment approval + rollout plan** |
| 8 | **Monitor** | The team continuously monitors extraction quality, validation failures, exception rates, reviewer activity, system performance, incidents, and potential model/data drift. | **Monitoring dashboard + incident log** |
| 9 | **Retire** | When the use case is replaced or no longer required, the solution is formally decommissioned and its documents, data, access, and records are handled according to applicable requirements. | **Decommission record + data-handling confirmation** |

---

# Detailed Lifecycle Walkthrough

## 1. Ideation

### What happens?

The business identifies a problem:

> Enterprise teams spend significant time manually reviewing documents,
> extracting information, validating data, and resolving exceptions.

A potential solution is proposed:

> Use Document AI to automate document processing and send uncertain or
> exceptional cases to human reviewers.

### Example

```text
Manual Document Processing
          ↓
Read documents manually
          ↓
Extract data manually
          ↓
Validate manually
          ↓
Handle exceptions manually
          ↓
High effort / slower processing
```

Proposed:

```text
Documents
    ↓
Document AI
    ↓
Classification
    ↓
Data Extraction
    ↓
Automated Validation
    ↓
    ├── Valid → Continue Processing
    │
    └── Exception → Human Reviewer
```

### Artifact

**One-page problem statement**

---

## 2. Intake

### What happens?

The proposed use case is formally submitted and its characteristics are
documented.

Important information includes:

- Document/data sources
- Types of documents
- Data fields to be extracted
- Whether PII or sensitive information is present
- Who will use the system
- Who may be affected
- Level of automation/autonomy
- Systems the solution will interact with

### Example

```text
Data Sources:
Enterprise business documents

Potential Data:
Customer / employee / business information

Automation:
Classification + extraction + validation

Human Involvement:
Review exceptions and approve selected cases
```

### Artifact

**Completed intake form**

---

## 3. Risk Tiering

### What happens?

The use case is evaluated using the organization's risk-tiering framework.

The assessment considers factors such as:

- Data sensitivity
- Potential impact
- Level of autonomy
- Affected users
- Business/process impact

The result is a documented risk tier and the reasoning behind it.

> **Important:** The exact tier should be assigned using the organization's
> approved Risk Tiering Framework rather than assuming a tier in advance.

### Example

```text
Document AI Use Case
        ↓
Risk Assessment
        ↓
Evaluate Risk Factors
        ↓
Determine Tier
        ↓
Document Tier + Rationale
```

### Artifact

**Documented risk tier + rationale**

---

## 4. Design

### What happens?

The team designs the technical solution according to the approved use case
and risk requirements.

A possible architecture is:

```text
                Documents
                    ↓
             Document Ingestion
                    ↓
              Classification
                    ↓
               Extraction
                    ↓
             Validation Rules
                    ↓
          ┌─────────┴─────────┐
          ↓                   ↓
       Valid              Exception
          ↓                   ↓
   Continue Process      HiTL Queue
                              ↓
                       Human Reviewer
                              ↓
                     Approve / Correct
                              ↓
                       Final Processing
```

The design also considers:

- Security
- Access control
- Data protection
- Auditability
- Human review
- Exception handling
- Integration with enterprise systems

### Artifact

**Architecture diagram + Architecture Decision Records (ADRs)**

---

## 5. Build

### What happens?

The development team implements the approved architecture.

The build may include:

- Document ingestion
- Document classification
- Information extraction
- Validation
- Exception detection
- Reviewer work queues
- Role-based access control
- Approval workflows
- Logging and audit capabilities

### Example

```text
Approved Design
      ↓
Development
      ↓
Document AI Components
      ↓
Integration
      ↓
Testing
      ↓
Working Solution
```

### Artifact

**Working code + test results**

---

## 6. Validate

### What happens?

An independent validator evaluates whether the solution works as expected
and meets the required controls.

The validator should **not be part of the team that built the system**.

Validation can check:

- Extraction accuracy
- Classification accuracy
- Validation behavior
- Exception handling
- HiTL workflow
- Access controls
- Security requirements
- Expected business outcomes
- Compliance with the approved design

### Important

```text
Build Team
    ↓
Builds the solution

Independent Validator
    ↓
Independently tests/challenges it
```

### Artifact

**Independent validation report**

---

## 7. Deploy

### What happens?

After required validation and approval, the Document AI solution is released
to production in a controlled manner.

A possible rollout:

```text
Pilot
  ↓
Small business group
  ↓
Evaluate results
  ↓
Broader rollout
  ↓
Enterprise use
```

Monitoring should be available as part of the production rollout.

### Artifact

**Deployment approval + rollout plan**

---

## 8. Monitor

### What happens?

The solution is continuously monitored after deployment.

Important metrics may include:

- Document processing volume
- Classification accuracy
- Extraction accuracy
- Validation failure rate
- Exception rate
- Human-review rate
- Reviewer turnaround time
- System errors
- Security incidents
- Model/data drift

### Example

```text
Production Document AI
        ↓
     Monitoring
        ↓
 ┌──────┼──────────┐
 ↓      ↓          ↓
Quality Errors   Exceptions
        ↓
     Incident
        ↓
Investigate / Correct
```

### Artifact

**Monitoring dashboard + incident log**

---

## 9. Retire

### What happens?

If the use case is replaced, discontinued, or no longer needed, it is formally
retired.

Activities can include:

- Disable the application
- Remove unnecessary access
- Decommission integrations
- Handle stored documents/data appropriately
- Preserve required records
- Confirm retirement completion

### Example

```text
Old Document AI Solution
          ↓
Replacement Solution Available
          ↓
Retirement Decision
          ↓
Decommission
          ↓
Data Handling
          ↓
Retirement Record
```

### Artifact

**Decommission record + data-handling confirmation**

---

# Lifecycle at a Glance

```text
1. IDEATION
   "We have a document-processing problem."
          ↓
2. INTAKE
   "Let's formally describe the use case."
          ↓
3. RISK TIERING
   "How risky is this use case?"
          ↓
4. DESIGN
   "How should we build it safely?"
          ↓
5. BUILD
   "Let's implement the approved design."
          ↓
6. VALIDATE
   "Does it work and meet requirements?"
          ↓
7. DEPLOY
   "Let's release it in a controlled way."
          ↓
8. MONITOR
   "Is it still working correctly?"
          ↓
9. RETIRE
   "Let's formally shut it down when it is no longer needed."
```

---

# Key Concepts Demonstrated

## 1. Human-in-the-Loop

The system does not need to make every decision automatically.

```text
AI processes document
        ↓
Confident result?
   ┌────┴────┐
  YES        NO
   ↓          ↓
Continue   Human Review
             ↓
       Approve / Correct
```

This allows uncertain or exceptional documents to be reviewed by a human.

---

## 2. Artifacts Create an Audit Trail

Each stage leaves evidence:

```text
Ideation      → Problem Statement
Intake        → Intake Form
Risk Tiering  → Tier + Rationale
Design        → Architecture + ADRs
Build         → Code + Test Results
Validate      → Validation Report
Deploy        → Approval + Rollout Plan
Monitor       → Dashboard + Incident Log
Retire        → Decommission + Data Confirmation
```

This means someone can review the lifecycle later and understand:

> What was proposed, what risks were identified, how it was designed,
> how it was tested, who approved it, how it performed, and how it was
> eventually retired.

---

# Exercise Deliverable

The required deliverable is a **9-row lifecycle map** for the selected
use case, with artifacts named for at least 3 stages.

For this Document AI use case, all 9 stages and their artifacts have been
mapped above.

### Minimum acceptable artifact examples

If only 3 artifacts are required, these are clear examples:

1. **Ideation → One-page problem statement**
2. **Design → Architecture diagram + ADRs**
3. **Validate → Independent validation report**

The full map above identifies an artifact for **every stage**.
