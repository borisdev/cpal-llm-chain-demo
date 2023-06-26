# Narrative Dependency Plannimg with an LLM: A Testable and Composable Approach  

Here I introduce a new approach to making a plan. The approach leverages the new advances in Large Language Models (LLMs) to translate a narrative chain of dependencies into code. The approach also highlights my prompt-engineering contribution to the LangChain open-source libray called the [Causal Program-aided Language (CPAL) LLM chain](https://github.com/hwchase17/langchain/pull/6255). 


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

The difference between my new CPAL and the existing PAL chain approach is explained in my [LangChain PR here](https://github.com/hwchase17/langchain/pull/6255). 

## How does will the future application work?

The app does the following. 

- The user writes causal narrative to define a work-breakdown-structure (WBS).
- The LLM translates the causal narrative into code.
- Another user writes a hypothetical question about a proposed change to the
  WBS.
- The LLM translates the question into a query. 
- The application runs the query and generates a report on the counterfactual
  outcome to the hypothetical question.

### Thesis

The thesis here is that the CPAL chain allows you to represent a project plan both as code and as a narrative, giving you the best of both worlds.

### Why Plan as Narrative?

Narratives are the top tool to persuade others of a plan during consensus building. You use a narrative to defend the validity of your plan by illustrating how a causal chain of events can lead to the desired outcome. Narratives are the top medium for ordinary people to convey their causal mental model.

### Why Plan as Code?

Though fast, narratives are problematic as their complexity increases. The problem is LLMs and humans are prone to hallucination when predicting the outcomes of a narrative. The cost of building a consensus around the validity of a narrative outcome grows as its narrative complexity increases. This is a culprit in the “tribal knowledge” problem and "highest-paid person in the room" problem. The Amazon-6-pager narrative meeting form attacks this problem. Likewise, the Plan as Code concept attacks this problem. Code does not require tribal knowledge or social power to validate. As narrative complexity increases, the value of representing a plan as code goes up. Code is testable, complex narratives are not.

Moreover, code is quickly composable, complex narratives are not. Composability means it can be integrated with other project plans and applications. For community voting and funding, composable plans can be integrated with a Dapp. For stochastic simulations, a composable plan can be integrated with the DoWhy library.

In summary, a code representation makes a project plan composable and testable.
