# Part 2 — RAGAS Homework

## Case 3: Diagnose the RAG Failure

### Query

> Does this NDA let the vendor use our data to train their AI models?

### Retrieved Context

**1. Section 4.2**

> Recipient shall use Confidential Information solely to evaluate the proposed partnership, and for no other purpose, including training, fine-tuning, or improving any machine learning or AI model.

**2. Section 7.1**

> Agreement shall remain in effect for two years from Effective Date.

### Generated Answer

> “Confidentiality clauses like this typically exist to protect sensitive business information shared during partnership discussions, and NDAs commonly include data retention along with mutual obligations for both parties to safeguard each other's data appropriately.”

---

## Diagnosis

This is a **RAG generation failure**.

The retrieval step worked reasonably well because **Section 4.2 directly contains the answer** to the user's question. However, the generated answer failed to use that information and instead produced a generic explanation about NDAs.

### 1. Context Relevance — Good

The first retrieved context is highly relevant.

Section 4.2 explicitly says that Confidential Information can be used only to evaluate the proposed partnership and specifically excludes:

- Training AI models
- Fine-tuning AI models
- Improving machine learning or AI models

Therefore, the retrieved context contains exactly the information needed to answer the question.

### 2. Context Precision — Partially Good

The first retrieved chunk is highly relevant, but the second chunk (Section 7.1) only discusses the agreement duration.

Section 7.1 does not help answer whether the vendor can use the data to train AI models.

Therefore, retrieval is good overall, but including an unrelated second chunk can reduce context precision depending on how the RAGAS metric is calculated.

### 3. Answer Relevance — Poor

The generated answer does **not directly answer the user's question**.

The user asked whether the vendor is allowed to use the data for AI training. A good answer should clearly say **No** and explain why.

Instead, the generated answer talks generally about:

- Confidentiality clauses
- Protecting sensitive business information
- Data retention
- Mutual obligations

It does not mention the important restriction in Section 4.2.

Therefore, **Answer Relevance is low**.

### 4. Faithfulness — Poor / Potentially Low

The answer should be grounded in the retrieved context.

However, the generated response introduces general claims about **data retention** and **mutual obligations** that are not supported by the retrieved sections.

The retrieved context does support the restriction against AI training, but the generated answer does not use it.

Therefore, the response can receive a **low Faithfulness score**, depending on the RAGAS evaluator and version being used.

### 5. What the Correct Answer Should Be

A suitable answer would be:

> **No.** Section 4.2 says the vendor may use Confidential Information only to evaluate the proposed partnership and for no other purpose, explicitly including training, fine-tuning, or improving any machine learning or AI model.

This answer is:

- Direct
- Relevant to the question
- Grounded in the retrieved context
- Supported by Section 4.2

---

## Final Diagnosis

The main problem is **not retrieval**. The required information was successfully retrieved.

The problem is in the **generation stage**:

**Query → Retrieval → Relevant Context → ❌ Incorrect/Generic Generation**

The LLM failed to ground its answer in the most relevant retrieved chunk.

### RAGAS Metric Summary

| Metric | Expected Result | Reason |
|---|---|---|
| Context Relevance | Good | Section 4.2 directly answers the question |
| Context Precision | Partially Good | Section 7.1 is irrelevant to the question |
| Answer Relevance | Poor | The answer does not answer the yes/no question |
| Faithfulness | Poor / Potentially Low | The answer contains claims not supported by the retrieved context |

## Key Learning

A RAG system can retrieve the **correct information** but still produce a **wrong answer**.

This case demonstrates that RAG quality depends on both:

1. **Retrieval quality** — finding the right information.
2. **Generation quality** — correctly using that information in the final answer.

In this case:

**Retrieval = Mostly successful**

**Generation/Grounding = Failed**
