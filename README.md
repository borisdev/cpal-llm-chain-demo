# Plan as Narrative, Test as Code

## Objective

Here I introduce a new approach to making a plan. The approach leverages the new advances in Large Language Models (LLMs) to translate a narrative chain of dependencies into code. The approach also highlights my prompt-engineering contribution to the LangChain open-source libray called the [Causal Program-aided Language (CPAL) LLM chain](https://github.com/hwchase17/langchain/pull/6255). This implementation of CPAL is a work in progress.

## Usage overview

- The user writes causal narrative to define a [work-breakdown-structure (WBS)](https://en.wikipedia.org/wiki/Work_breakdown_structure).
- The LLM translates the causal narrative into code.
- Another user writes a hypothetical question about a proposed change to the
  WBS.
- The LLM translates the question into a query. 
- The application runs the query and generates a report on the outcomes.


## Technical introduction for the non-coder

### What is a LLM chain? 

A chain within the Langchain library is a type of composable application interface to a LLM. 
As an analogy, just as SaaS application requires an interface to cloud databases, Inference as a Service (IaaS) requires 
an interface to to cloud LLMs.

### What is a CPAL chain?

A CPAL chain allows a user to ask hypothetical questions about a causal
narrative. Without the CPAL chain's interface the LLM would still be able to
answer such hypothetical questions but it would hallucinate more frequently than
otherwise because its answers are not constrained by a causal
structure.

The difference between my new CPAL and the existing PAL chain approach is explained in my [LangChain PR here](https://github.com/hwchase17/langchain/pull/6255). 
