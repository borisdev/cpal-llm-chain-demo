# Causal Program-aided Language "Plan as Code" demo

The Causal Program-aided Language (CPAL) chain is my proposed code contribution
to the Langchain open-source library.

Here is am trying to demonstrate a CPAL chain approach to build project planning
applications. 

## What is a LLM chain? 

A chain within the Langchain library is a type of composable application interface to a LLM. 
As an analogy, just as SaaS required building composable interfaces to cloud
databases, the new wave of Inference as a Service (IaaS) requires building
composable application interfaces to cloud LLMs. In a sense, Langchain chains are like
views in Django/Flask/FastAPI.

## What is a CPAL chain?

A CPAL chain allows a user to ask hypothetical questions about a causal
narrative. Without the CPAL chain's interface the LLM would still be able to
answer such hypothetical questions but it would hallucinate more frequently than
otherwise because its answers are not constrained by a causal
structure.

The difference between CPAL and PAL is in the last section below.

## How does the "Plan as Code" demo app works?

The app does the following. 

- The user writes causal narrative to define a work-breakdown-structure (WBS).
- The LLM translates the causal narrative into code.
- Another user writes a hypothetical question about a proposed change to the
  WBS.
- The LLM translates the question into a query. 
- The application runs the query and generates a report on the counterfactual
  outcome to the hypothetical question.


## Two for one coupon

The thesis here is that the CPAL chain allows you to represent a project plan
both as code and as a narrative, giving you the best of both worlds.

## Why Plan as Narrative?

Narratives are the top tool to persuade others of a plan during
consensus building. You use a narrative to defend the validity of your plan by
illustrating how a causal chain of events can lead to the desired outcome.
Narratives are the top medium for ordinary people to convey their causal mental
model.


## Why Plan as Code?

Though fast, narratives are problematic as their complexity increases. The
problem is LLMs and humans are prone to hallucination when predicting the
outcomes of a narrative. The cost of building a consensus around the validity of
a narrative outcome grows as its narrative complexity increases. This is a
culprit in the "tribal knowledge" problem and "highest paid person in the room"
problem. The Amazon-6-pager narrative meeting form attacks this problem.
Likewise, the Plan as Code concept attacks this problem. Code does not require
tribal knowledge or social power to validate. As narrative complexity increases
the value of a representing a plan as code goes up. Code is testable, complex
narratives are not.

Also, code is quickly composable, complex narratives are not. Composability
means it can be integrated with other project plans and applications. For
community voting and funding, composable plans can be integrated with a Dapp.
For stochastic simulations, a composable plan can be integrated with the DoWhy
library.

In summary, a code representation makes a project plan composable and testable. 



## CPAL versus PAL?

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
