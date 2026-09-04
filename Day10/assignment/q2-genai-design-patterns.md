# Day 10 - Question 2

## GenAI Design Patterns

For this question, I am using a **customer support system** as the example. The system uses GenAI to understand customer complaints and help support agents prepare responses.

---

## 1. Prompt Chaining

### Scenario

In this approach, the whole task is divided into a few smaller steps.

For example, when a customer sends a complaint, the system first understands what the customer is asking. Then it identifies the type of issue, generates a reply, and checks the reply before showing it to the support agent.

The output from one step is used as the input for the next step.

**HITL:** The support agent reviews the final response before it is sent to the customer.

**Override / Escalation:** If the response is incorrect or the complaint is serious, the agent can change the response or send the case to a senior support team.

**Design Record:** The design record should explain why the task was divided into multiple steps and what each step is responsible for.

---

## 2. Routing

### Scenario

In customer support, different types of questions usually need to go to different teams.

For example, if a customer says, "I was charged twice," the system can identify it as a billing issue and send it to the billing process. If the customer says, "The application is not opening," it can be sent to the technical-support process.

So, routing is mainly about deciding **where the request should go**.

**HITL:** If the system is not confident about the type of request, it can send the ticket to a support agent instead of making a guess.

**Override / Escalation:** A support agent should be able to correct the routing if the ticket was sent to the wrong team.

**Design Record:** The design record should mention the different categories, how the routing decision is made, and what happens when the system is unsure.

---

## 3. Orchestrator-Worker

### Scenario

Here, I think of the orchestrator as a manager and the workers as people who handle different tasks.

For example, a customer may ask, "Can you check my order and tell me why it is delayed?"

The orchestrator can divide this into smaller tasks. One worker can check the order details, another can check delivery information, and another can look for the reason for the delay. The results are then brought together to prepare the final response.

**HITL:** If the response involves something important, such as a refund or compensation, a support agent can review it before it is sent.

**Override / Escalation:** If the workers provide conflicting information, the system should not simply choose one result. It can send the case to a human for review.

**Design Record:** The design record should explain what the orchestrator does, what each worker is responsible for, and how failures or conflicting results are handled.

---

## 4. Evaluator-Optimizer

### Scenario

In this approach, the system first generates a response and then another step checks whether the response is good enough.

For example, the GenAI creates a reply to a customer complaint. The evaluator checks whether the reply actually answers the customer's question, contains correct information, has an appropriate tone, and follows company rules.

If the response has a problem, it can be improved and checked again.

**HITL:** For sensitive complaints, a support agent can review and approve the final response.

**Override / Escalation:** The support agent can reject the AI-generated response and write their own response. Serious complaints can also be sent to a senior support team.

**Design Record:** The design record should explain what the evaluator checks and when the system should involve a human.

---

## 5. Parallelization

### Scenario

Sometimes a customer support ticket needs several checks, but those checks do not depend on each other.

For example, when a ticket comes in, one check can look for spam, another can check for sensitive content, and another can look at the customer's sentiment. These checks can happen at the same time instead of waiting for one check to finish before starting the next one.

The results can then be considered together before deciding what to do with the ticket.

**HITL:** If one of the checks finds something serious, the ticket can be sent to a human support agent.

**Override / Escalation:** A human should be able to correct an incorrect flag. For example, a normal angry customer complaint should not automatically be treated as abusive just because the AI misunderstood the wording.

**Design Record:** The design record should explain which checks can run independently and what should happen if the checks give different results.

---