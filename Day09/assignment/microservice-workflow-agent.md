# Microservice vs Workflow vs Agent

These three terms can sound similar when working on GenAI projects, but they solve different problems.

## 1. Microservice

A microservice is a small software component that is responsible for a particular function.

For example, in a Facebook application, we could have a service whose only job is to generate a caption.

```text
User request
    ↓
Content Generation Service
    ↓
Generated caption
```

The service does the job it was designed to do. It does not normally decide the whole process by itself.


## 2. Workflow

A workflow is a set of steps that are defined beforehand.

For example:

```text
User enters a request
        ↓
Check the request
        ↓
Generate content
        ↓
Run safety check
        ↓
Show the draft to the user
        ↓
User approves
        ↓
Publish
```

The order of the steps is already known. The system follows the process rather than deciding a completely new process each time.


## 3. Agent

An agent is different because it can decide what actions or tools it needs to use to achieve a goal.

For example, a user could ask:

> "Create a post about my trip and get it ready for tomorrow."

An agent could decide that it needs to:

```text
Understand the request
        ↓
Find the required information
        ↓
Create a draft
        ↓
Check the content
        ↓
Ask the user for approval
        ↓
Schedule the post
```

The important part is that the agent can choose the next action based on the situation instead of only following one fixed sequence.

