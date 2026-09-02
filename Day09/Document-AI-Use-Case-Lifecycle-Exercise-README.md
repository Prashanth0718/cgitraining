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

