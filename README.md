# LLM as a Judge — Technical Pattern

This repository contains a technical pattern for implementing LLM as a Judge. LLM-As-A-Judge requires asking an LLM to 
score one response in relation to a ground-truth (the assumed ideal response), using a detailed prompt (rubric).

See [glossary](glossary.md) for definitions of key terms used in this pattern.

The implementation of this pattern can be found in the following 3 repositories:

- [ai-uc-rag-evaluation-ui](https://github.com/DEFRA/ai-uc-rag-evaluation-ui) — UI for setting up data and viewing results
- [ai-uc-rag-evaluation-data](https://github.com/DEFRA/ai-uc-rag-evaluation-data) — Backend to access and insert data into the vector store
- [ai-uc-rag-evaluation-runtime](https://github.com/DEFRA/ai-uc-rag-evaluation-runtime) — Backend to run the LLM as a judge evaluations

This pattern was based on the initial spikes looking at evaluating LLM results:

- [ai-spike-llm-validation](https://github.com/DEFRA/ai-spike-llm-validation/blob/main/experiment-writeup.md)
- [ai-spike-evaluation-metrics](https://github.com/DEFRA/ai-spike-evaluation-metrics/blob/main/experiment-writeup.md)

Key findings from the spikes:

- LLM as a judge is an effective metric for evaluating generative AI responses against a known ground truth.
- Of the implementations tested, pydantic-ai's `LLMJudge` performed best.
- The rubric is critical to the quality of the judgement.
- The model used for the judge is also critical to the quality of the judgement.

Based on these findings, this pattern uses pydantic-ai with support for multiple rubrics and multiple models, enabling 
comparison of judgement scores.

## Who this pattern is for

This pattern is targeted at developers and QA who are looking to implement LLM as a Judge on CDP or need to evaluate the
response from generative AI in an automated fashion.

## The problem

As part of the Large Language Model (LLM) validation framework we need a process for comparing LLM responses to known 
ground truths, e.g. comparing the answers to questions with the known correct answer or comparing LLM generated 
summaries to the human-written equivalent. This repository aims to provide a reference implementation for how LLM as a
judge can be used on the CDP platform.

## Licence

THIS INFORMATION IS LICENSED UNDER THE CONDITIONS OF THE OPEN GOVERNMENT LICENCE found at:

<http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3>

The following attribution statement MUST be cited in your products and applications when using this information.

> Contains public sector information licensed under the Open Government license v3

## Implementation patterns
This repository contains the following patterns

- [LLM as a judge](./patterns/llm-as-a-judge.md) An implementation of the LLM as a Judge that can run in the CDP 
environment.

### About the licence

The Open Government Licence (OGL) was developed by the Controller of Her Majesty's Stationery Office (HMSO) to enable
information providers in the public sector to license the use and re-use of their information under a common open
licence.

It is designed to encourage use and re-use of information freely and flexibly, with only a few conditions.
