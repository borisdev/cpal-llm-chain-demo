# LLM CPAL chain to define a work-breakdown-structure

The CPAL chain is my code contribution to Langchain.

Below is a conceptual overview and a demo application.

## What is a Langchain chain?

A Langchain chain is a composable application interface to a LLM. 
As an analogy, just as SaaS required building composable interfaces to cloud
databases, the new wave of Inference as a Service (IaaS) requires building
composable application interfaces to cloud LLMs. In a sense, Langchain chains are like
views in Django/Flask/FastAPI.


## What is the difference between CPAL and PAL?

"PAL uses uses the LLM to read natural language problems and generate programs
as the intermediate reasoning steps, but offloads the solution step to a runtime
such as a Python interpreter." (Gao, 2022) [PAL: Program-aid Language
Models](https://arxiv.org/abs/2211.10435). 

PAL stands for Program-aided Langauge. CPAL stands for Causal Program-aided
Language. The difference in name is the word Causal.

Like [PAL](https://arxiv.org/abs/2211.10435), CPAL intends to reduce large
language model (LLM) hallucination. Also like PAL, CPAL is implemented as a
chain using the [langchain](https://python.langchain.com/en/latest/index.html)
open source library. 

The CPAL chain is different from the PAL chain because it adds a causal
structure (or DAG) to links entity actions (or math expressions). As a
side-note, Langchain's `graph_qa` chain also extracts entity-action-entity
relations into a DAG, but does not connect them to math expressions. 

Preliminary evaluation on simple math word problems shows that this CPAL chain
generates less hallucination than the PAL chain because the answers to queries
must adhere to the narrative's causal structure. 

## Demo Application: Project Planning as Code

A large language model can represent a causal narratives as code. This can
disrupt how we do complex project planning.

### Motivation

Narratives are important. They are a tool to persuade others of a plan during
consensus building. You use a narrative to defend the validity of your plan by
illustrating how a causal chain of events can lead to the desired outcome.
Narratives are the top medium for ordinary people to convey their causal mental
model.

Narratives are also problematic. The problem is LLMs and humans are prone to
hallucination when predicting the outcomes of a narrative. At a verbal concensus
building meeting its hard to evaluate the impact of complex narrative condition
changes on outcome changes. This is a culprit in the "tribal knowledge" problem
and "highest paid person in the room" (HIPPO) problem. The Amazon-6-pager
narrative meeting form attacks this problem. Likewise, this "Causal Story as
Code" concept attacks this problem. Once again, translating a causal narrative into code
makes it easier to evaluate the validity of a plan.

### How it works

The code in this repo runs a demo application, which does the following. 

- The user writes causal narrative to define a work-breakdown-structure (WBS).
- The LLM translates the causal narrative into code.
- Another user writes a hypothetical question about a proposed change to the WBS.
- The LLM translates the question into a query. 
- The application runs the query and generates a report on the counterfactual outcome to the hypothetical question.

### Future implications

For community voting and funding, composable plans can be integrated with a Dapp. 
For stochastic simulations, a composable plan can be integrated with the DoWhy library.
