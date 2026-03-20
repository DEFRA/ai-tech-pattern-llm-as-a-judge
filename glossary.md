# Glossary

| Term | Definition                                                                                                                              |
|---|-----------------------------------------------------------------------------------------------------------------------------------------|
| **CDP** | Core Delivery Platform — the hosting platform this pattern targets                                                                      |
| **DLQ** | Dead Letter Queue — where SQS messages are moved after exceeding the maximum retry count                                                |
| **Ground truth** | The assumed ideal or correct response used as a baseline for evaluation                                                                 |
| **Guardrails** | AWS Bedrock safety controls applied to LLM requests, required by CDP                                                                    |
| **Inference profile** | A Bedrock ARN that specifies which model and configuration to use when calling the LLM                                                  |
| **LLM as a Judge** | Using a large language model to score a generated response against a known ground truth                                                 |
| **LLMJudge** | The pydantic-ai class that implements the LLM as a Judge pattern                                                                        |
| **pydantic-ai** | Python library used to execute LLM models, supporting Bedrock inference profiles and guardrails                                         |
| **RAG Search** | Retrieval-Augmented Generation search — fetches relevant documents used as context for the LLM response being evaluated                 |
| **Rubric** | A detailed prompt that instructs the LLM Judge how to score a response                                                                  |
| **SQS** | AWS Simple Queue Service                                                                                                                |
| **Visibility timeout** | The period an SQS message is hidden from other consumers while being processed; if unacknowledged, the message becomes available again  |