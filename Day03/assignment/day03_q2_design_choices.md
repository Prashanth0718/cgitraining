



# Day 03 – Q2: Design Choices

## Question

**Q2. Give the design choices for below scenarios and their explanation.**

---

# Scenario 1 – Healthcare

## Clinical Intake Drug-Interaction Flag

### Question / Scenario

A hospital's intake system needs to flag potential multi-drug interaction risks as a nurse enters a new patient's medication list — a single-patient, moderate-urgency check during intake, not a batch job. It must run inside the hospital's own network per data-governance policy, and getting the interaction reasoning right matters for patient safety.

### Design Choice 1 – Model Family

**Selected: Reasoning Model**

### Design Choice 2 – Where It Runs

**Selected: Edge / On-Prem**

### Explanation

A reasoning model is selected because the system needs to identify potential multi-drug interaction risks, and getting the interaction reasoning right is important for patient safety.

Edge / On-Prem is selected because the system must run inside the hospital's own network according to its data-governance policy.

---

# Scenario 2 – Government / Defense

## Sovereign Case-File Summarization

### Question / Scenario

A government agency needs to summarize case files on an air-gapped network — no connection to any public cloud is permitted for any request, ever. Case files are lengthy and require genuine multi-step synthesis (cross-referencing dates, names, and prior rulings), not just extraction.

### Design Choice 1 – Model Family

**Selected: Reasoning Model**

### Design Choice 2 – Where It Runs

**Selected: Edge / On-Prem**

### Explanation

A reasoning model is selected because the case files require genuine multi-step synthesis and cross-referencing of dates, names, and prior rulings. This requires more than simple information extraction.

Edge / On-Prem is selected because the network is air-gapped and the scenario explicitly states that no connection to any public cloud is permitted. Therefore, the model must run within the organization's controlled environment.

---








