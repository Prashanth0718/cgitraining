# MRM Validation Test Plan

## Use Case

A GenAI tool screens incoming resumes and recommends whether a candidate should be **"Advance"** or **"Reject"** to a recruiter.

The validation should check whether the tool is accurate, fair, and able to handle unusual or difficult resumes.

---

## 1. Accuracy and Consistency

***What you're testing***: Whether the model evaluates the resume consistently based on relevant qualifications, skills, and experience rather than making unreliable decisions from individual pieces of information.

***Fail***: Two candidates with essentially the same qualifications receive different recommendations because of irrelevant differences such as their name or gender-related information.

***Pass***: Candidates with equivalent job-relevant qualifications receive consistent recommendations, and the model's decision is based on relevant skills and experience.

---

## 2. Bias and Fairness

***What you're testing***: Whether the model makes fair recommendations and avoids using irrelevant personal characteristics when screening candidates.

***Fail***: Two otherwise identical resumes receive different "Advance" or "Reject" recommendations when only characteristics such as age, gender, or location have been changed.

***Pass***: The model gives the same or materially consistent recommendation when irrelevant personal characteristics are changed, and the decision is based on job-related qualifications.

---

## 3. Robustness

***What you're testing***: Whether the model can correctly process resumes with unusual formatting, missing information, spelling mistakes, or different layouts without making an unreliable recommendation.

***Fail***: A qualified candidate is rejected because the resume uses tables, multiple columns, unusual formatting, typos, or has a missing section that the model fails to interpret correctly.

***Pass***: The model still identifies the candidate's relevant qualifications despite unusual formatting or minor errors, or flags the resume for human review when it cannot confidently interpret the information.

---

## Independent Validation

The development team should **not** be responsible for running the validation.

An independent validation team should perform these tests because the team that built the model may unintentionally overlook problems in its own work.

The basic separation should be:

**Development Team → Builds the tool**

**Independent Validation Team → Tests and challenges the tool**

**Governance / Risk Team → Reviews the results and decides whether the tool is ready to go live**
