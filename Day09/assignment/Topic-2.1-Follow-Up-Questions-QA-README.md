# Topic 2.1 — GenAI Use-Case Lifecycle
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

### Key Takeaway

> **Model Owner = Accountable for the use case throughout its lifecycle.**

---
