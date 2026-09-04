# Facebook GenAI Use Case — Lifecycle

## Use Case

A GenAI assistant for Facebook that helps users create posts, captions, and replies. The assistant suggests content, but the user stays in control and decides what to publish.

## 1. Ideation

We noticed that users sometimes spend a lot of time deciding what to write in a post or reply. The idea is to use GenAI to give users a useful first draft instead of making them start from a blank page.

**Artifact:** Problem statement

## 2. Intake

The team collects the basic details of the use case, including what information the assistant needs, who will use it, and how much control the AI will have. In this case, the AI suggests content and the user decides whether to use it.

**Artifact:** Completed intake form

## 3. Risk Tiering

The use case is reviewed for things such as the data being used, how much autonomy the AI has, who could be affected, and how easy it is to reverse an action. Since the AI only suggests content and the user reviews it before publishing, it would likely be a lower-risk use case, depending on the actual risk assessment.

**Artifact:** Risk tier and rationale

## 4. Design

The team decides how the user request will reach the GenAI model and how the generated response will come back to the user. The design also includes safety checks, data handling, and the requirement that the user reviews the content before publishing.

**Artifact:** Architecture diagram and ADR

## 5. Build

Developers build the content-generation functionality and connect it with the required Facebook components. They also test normal requests as well as harmful, inappropriate, or misleading prompts.

**Artifact:** Working code and test results

## 6. Validate

A team that was not involved in building the system independently tests it. They try normal cases, edge cases, and difficult prompts to see whether the assistant behaves as expected before it is released.

**Artifact:** Independent validation report

## 7. Deploy

Once the required checks and approvals are completed, the assistant is released gradually rather than immediately to everyone. The rollout also includes a way to roll back or pause the feature if a serious problem appears.

**Artifact:** Deployment approval and rollout plan

## 8. Monitor

After launch, the team keeps an eye on things like errors, content quality, safety issues, and user feedback. Important problems are recorded and investigated instead of being ignored.

**Artifact:** Monitoring dashboard and incident log

## 9. Retire

If the assistant is no longer needed or is replaced by a better solution, it is formally taken out of service. The team also records what happened to the system and confirms that user data was handled according to the required policy.

**Artifact:** Decommission record and data-handling confirmation

