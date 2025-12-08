# Evaluating ML Models as Agent Tools

## Overview

This example demonstrates how to evaluate traditional ML models (like HuggingFace sentiment classifiers) when used as tools within LangGraph agents. It addresses the challenge of layered evaluation—testing the ML model independently, validating tool selection logic, and assessing end-to-end agent responses. The core pattern shows how to combine classification metrics (precision, recall, F1) with LLM-as-judge evaluators using LangSmith.

[MLOps-> LangSmith Slide](https://docs.google.com/presentation/d/1pVv3_0aI4HDk0e9lSxx5_SY_qleMr-wgVn0W6_9wcp4/edit?usp=sharing)

## Quickstart

### Prerequisites

- Python 3.11+
- [uv](https://docs.astral.sh/uv/) package manager
- LangSmith account ([sign up](https://smith.langchain.com/))
- OpenAI API key

### Installation

```bash
cd ml-model-evals

# Install dependencies
uv sync
```

### Environment Setup

Copy `.env.example` to `.env` and fill in your API keys:

```bash
cp .env.example .env
```

Then edit `.env` with your actual API keys:

```
OPENAI_API_KEY=your_openai_api_key_here
LANGSMITH_API_KEY=your_langsmith_api_key_here
TOKENIZERS_PARALLELISM=false
LANSMITH_PROJECT=your_langsmith_project
```

### Run

```bash
# Start Jupyter
uv run jupyter lab

# Open ml_model_evals.ipynb
```

## Additional Notes

- **Use Case**: The notebook uses clinical trial participant feedback analysis as an example, but the pattern applies to any ML model used as an agent tool.
- **Costs**: Running evaluations will incur OpenAI API costs for the agent and LLM-as-judge evaluators.
- **LangSmith Experiments**: All evaluation results are viewable in the LangSmith Experiments UI for comparison.

### Related Resources

- [LangSmith Evaluation Documentation](https://docs.smith.langchain.com/evaluation)
- [LangSmith Summary Evaluations](https://langchain-5e9cc07a.mintlify.app/langsmith/summary)
- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [OpenEvals Library](https://github.com/langchain-ai/openevals)

## License

MIT

