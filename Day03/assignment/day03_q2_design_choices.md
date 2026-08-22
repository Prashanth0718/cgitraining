# Day 03 – Q2: Design Choices

## Question

**Q2. Give the design choices for the below scenarios and their explanation.**

---

## Scenario 1 – Healthcare

### Clinical Intake Drug-Interaction Flag

**Question / Scenario:**

A hospital's intake system needs to flag potential multi-drug interaction risks as a nurse enters a new patient's medication list — a single-patient, moderate-urgency check during intake, not a batch job. It must run inside the hospital's own network per data-governance policy, and getting the interaction reasoning right matters for patient safety.

### Design Choice 1 – Model Family

**Selected:** Reasoning Model

### Design Choice 2 – Where It Runs

**Selected:** Edge / On-Prem

### Explanation

A reasoning model is selected because the scenario requires identifying potential multi-drug interaction risks, and getting the interaction reasoning right is important for patient safety.

Edge / On-Prem is selected because the system must run inside the hospital's own network according to its data-governance policy.

