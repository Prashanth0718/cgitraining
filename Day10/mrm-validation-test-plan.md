# MRM Validation Test Plan

## Use Case

A GenAI tool screens incoming resumes and recommends whether a candidate should be **"Advance"** or **"Reject"** to a recruiter.

The goal of the validation is to make sure the tool is accurate, fair, and able to handle unusual or difficult resumes before it is used in production.

## Validation Test Plan

### 1. Accuracy and Consistency

Check whether the AI makes reasonable and consistent recommendations based on the candidate's qualifications, skills, and experience.

**Adversarial / Edge Case:**

Use two resumes with the same qualifications and experience but different names or gender-related information.

The recommendation should not change without a valid job-related reason.

---

### 2. Bias and Fairness

Check whether the AI treats candidates fairly and does not make decisions based on irrelevant personal characteristics.

**Adversarial / Edge Case:**

Create similar resumes where only characteristics such as age, gender, or location are changed.

The AI should produce consistent recommendations when those characteristics are not relevant to the job.

---

### 3. Robustness

Check whether the AI can handle resumes with unusual formatting, missing information, spelling mistakes, or unexpected layouts.

**Adversarial / Edge Case:**

Test resumes containing tables, multiple columns, unusual formatting, typos, or missing sections.

The AI should still identify the relevant qualifications without incorrectly rejecting the candidate because of the formatting.

---

## Who Should Perform the Validation?

The validation should be performed by an **independent team that was not involved in building the resume-screening tool**.

The development team should not validate its own work because they may unintentionally overlook problems or be biased toward the system they built.

The basic separation should be:

**Development Team → Builds the tool**

**Independent Validation Team → Tests and challenges the tool**

**Governance / Risk Team → Reviews and approves based on the risk**

## Key Takeaway

The purpose of independent validation is not just to show that the AI works.

It is to **actively look for situations where the AI could fail, behave unfairly, or produce unreliable recommendations before it goes live.**
