# Plan as Narrative, Test as Code

Leverage an LLM to make community planning better.

## Objective

Here I introduce a new approach to making a plan. The approach leverages the new advances in Large Language Models (LLMs) to translate a narrative chain of dependencies into code. The approach also highlights my prompt-engineering contribution to the LangChain open-source libray called the [Causal Program-aided Language (CPAL) LLM chain](https://github.com/hwchase17/langchain/pull/6255). This implementation of CPAL is purely conceptual. 

## Usage

- User A writes causal narrative to define a plan or more formally a [work-breakdown-structure (WBS)](https://en.wikipedia.org/wiki/Work_breakdown_structure).
- The LLM translates User A's causal narrative of the plan into code.
- A teammate User B writes a hypothetical question of her speculated change to the
  original plan.
- The LLM translates User B's question into a query. 
- The application runs the query and generates a report on the impact of User B's speculated plan change on the plan's outcomes.

## Research questions

- Is there public data to make a prototype of this concept app?
- How can we add time as a parameter for each work span, and total time as an outcome?
- How can we add cyclic dependencies?
- What optimization code already exists to help a planner?
- Geo-spatial queries and impact analysis?
- Time and cost and ROI optimizations?

## References

- Extend the my CPAL experimental work in LangChain, [LangChain PR here](https://github.com/hwchase17/langchain/pull/6255). 
- LangChain's tweet on the CPAL is [here](https://twitter.com/LangChainAI/status/1678797225013440514?t=l0uWL3le49SaZx0mAAKh7ww&s=40)
  
## Cool stuff by others

- 2023 [AutoScrum™: Automating Project Planning Using Large Language Model Programs](https://arxiv.org/pdf/2306.03197.pdf) 
