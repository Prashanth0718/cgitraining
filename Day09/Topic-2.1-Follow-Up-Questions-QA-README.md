# Topic 2.1 — GenAI Use-Case Lifecycle
## Follow-Up Questions & Answers

This README contains all 4 follow-up questions from Topic 2.1,
with answers, explanations, examples, and key takeaways.

---

## 1. Data Source Change

### Question

At which stage would you expect to first catch that a use case's data
sources have shifted from internal-only to include customer PII?

### Answer

**Intake**

### Why?

The **Intake** stage captures important information about the proposed
use case, including:

- Data sources
- Autonomy
- Affected users

If a use case originally uses only internal company data but later
includes customer PII, this change should be identified during the
**Intake** process.

### Example

Original:

```text
Data Sources
    ↓
Internal company documents
```

After the change:

```text
Data Sources
    ↓
Internal documents
+
Customer PII
```

This change needs to be captured and assessed.

### Key Takeaway

> **Intake = Understand exactly what the use case involves.**

---

## 2. Validate Artifact

### Question

What artifact would you expect out of the `Validate` stage,
specifically, and who should NOT be the one producing it?

### Answer

**Independent Validation Report**

The report should **NOT** be produced by the build team.

### Why?

The build team is responsible for creating the system.

An **independent validator** should evaluate and challenge the system
separately.

```text
Build Team
    ↓
Builds the system
    ↓
Independent Validator
    ↓
Tests / Challenges the system
    ↓
Independent Validation Report
```

The validator should **not** have been part of the build team.

### Example

Imagine a development team builds a GenAI HR assistant.

The development team performs the build:

```text
Developers
    ↓
Build RAG + LLM system
```

Then an independent validation team checks:

```text
Independent Validator
    ↓
Accuracy
Security
Requirements
Risk controls
Expected behavior
```

The result is documented in the:

**Independent Validation Report**

### Key Takeaway

> **Build = Create the system.**
>
> **Validate = Independently check the system.**

---

## 3. Scope Expansion

### Question

If a Tier 1 use case's scope quietly expands to include write-access
to a production system, which stage should be revisited?

### Answer

**Risk Tiering**

### Why?

The original use case may have been considered low risk.

However, giving the AI **write-access to a production system** can
significantly change:

- Scope
- Autonomy
- Potential impact
- Risk

Therefore, the use case should be **reassessed and potentially
re-tiered**.

### Example

Original system:

```text
AI Assistant
    ↓
Read-only access
    ↓
Tier 1
```

The scope changes:

```text
AI Assistant
    ↓
Production WRITE access
    ↓
Greater potential impact
    ↓
Revisit Risk Tiering
```

The organization should reassess the risk rather than continuing to
treat the use case as the original Tier 1 use case.

### Important Concept — Re-tiering

A use case's risk tier is not necessarily permanent.

If important characteristics of the use case change, the risk should
be reassessed.

```text
Existing Use Case
       ↓
Scope Changes
       ↓
Risk Tiering
       ↓
Reassess Risk
       ↓
Possible New Tier
       ↓
Update Controls / Design
```

### Key Takeaway

> **Significant scope change → Reassess the risk tier.**

---

## 4. Retirement Ownership

### Question

Who typically owns the decision to `Retire` a use case, and why does
that decision need an owner at all?

### Answer

**The Model Owner**

### Why?

The **Model Owner** is accountable for the AI use case.

Someone needs to be responsible for deciding when the system should
no longer be used.

Without clear ownership:

```text
Nobody owns the system
        ↓
Nobody decides when to retire it
        ↓
Old system may continue running
        ↓
Potential unnecessary risk
```

The Model Owner provides accountability for the use case throughout
its lifecycle.

For higher-risk use cases, governance sign-off may also be required.

### Example

Suppose a company has an old GenAI HR assistant that has been replaced
by a newer system.

The Model Owner can initiate the retirement:

```text
Model Owner
    ↓
Decides system is no longer needed
    ↓
Retirement process
    ↓
Decommission system
    ↓
Handle data appropriately
    ↓
Record completion
```

For Tier 2 / Tier 3 use cases, governance sign-off is required
according to this lifecycle framework.

### Key Takeaway

> **Model Owner = Accountable for the use case throughout its lifecycle.**

---

# Quick Revision

| # | Question | Answer | Concept Tested |
|---|---|---|---|
| 1 | Where is a data-source change first caught? | **Intake** | Data / scope capture |
| 2 | What comes from Validate? | **Independent Validation Report** | Independent validation |
| 3 | Scope expands to production write-access | **Revisit Risk Tiering** | Re-tiering |
| 4 | Who owns retirement? | **Model Owner** | Accountability |

---

# 🧠 Four Things to Remember

### 1. INTAKE

```text
Intake
  ↓
Data + Autonomy + Affected Users
```

> Understand exactly what the use case involves.

### 2. INDEPENDENT VALIDATION

```text
Build Team
    ≠
Independent Validator
```

> The team that builds the system should not be the independent
> validator of that same system.

### 3. RE-TIERING

```text
Important Scope Change
        ↓
Reassess Risk
        ↓
Possible New Tier
```

> A risk tier can change when the use case changes.

### 4. MODEL OWNER

```text
Model Owner
     ↓
Accountability
     ↓
Lifecycle decisions
```

> Someone must be accountable for the AI use case, including its
> eventual retirement.

---

# Final Mental Model

The 4 questions are testing four different parts of the lifecycle:

```text
                    AI USE CASE
                         │
                         ▼
                     INTAKE
                         │
                  "What data?"
                         │
                         ▼
                    VALIDATE
                         │
               "Who independently
                   checks it?"
                         │
                         ▼
                 RISK TIERING
                         │
              "Did the scope change?"
                         │
                         ▼
                  MODEL OWNER
                         │
                 "Who is accountable?"
                         │
                         ▼
                      RETIRE
```

## One-Line Revision

> **Intake catches what the use case involves → Independent Validation
checks the build → Risk Tiering is revisited when scope changes →
Model Owner remains accountable for retirement.**
