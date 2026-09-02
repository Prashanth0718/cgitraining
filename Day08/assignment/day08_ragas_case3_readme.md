# Part 2 — RAGAS Homework

## Case 3: Diagnose the RAG Failure

### Query

> Does this NDA let the vendor use our data to train their AI models?

### Retrieved Context

**Section 4.2:**  
Recipient shall use Confidential Information solely to evaluate the proposed partnership, and for no other purpose, including training, fine-tuning, or improving any machine learning or AI model.

**Section 7.1:**  
Agreement shall remain in effect for two years from Effective Date.

### Generated Answer

> Confidentiality clauses like this typically exist to protect sensitive business information shared during partnership discussions, and NDAs commonly include data retention along with mutual obligations for both parties to safeguard each other's data appropriately.

## Diagnosis

The **retrieval was successful**, because Section 4.2 directly answers the question.

The **generation failed** because the LLM did not use the relevant information from Section 4.2 and instead gave a generic explanation about NDAs.

### RAGAS Metrics

- **Context Relevance — Good:** Section 4.2 directly addresses AI training.
- **Context Precision — Partially Good:** Section 7.1 is irrelevant to the question.
- **Answer Relevance — Poor:** The generated answer does not answer whether AI training is allowed.
- **Faithfulness — Poor/Potentially Low:** The answer mentions data retention and mutual obligations that are not supported by the retrieved context.

### Correct Answer

**No.** Section 4.2 states that the Confidential Information may only be used to evaluate the partnership and explicitly prohibits using it for training, fine-tuning, or improving AI/ML models.

## Conclusion

**Retrieval = Successful**  
**Generation/Grounding = Failed**
