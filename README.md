# Evaluating ML Models as Agent Tools

## Overview

This example demonstrates how to evaluate traditional ML models (like HuggingFace sentiment classifiers) when used as tools within LangGraph agents. It addresses the challenge of layered evaluation—testing the ML model independently, validating tool selection logic, and assessing end-to-end agent responses. The core pattern shows how to combine classification metrics (precision, recall, F1) with LLM-as-judge evaluators using LangSmith.

## Quickstart

### Prerequisites

- Python 3.9+
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

Create a `.env` file or export environment variables:

```bash
export LANGSMITH_API_KEY=your_langsmith_api_key
export OPENAI_API_KEY=your_openai_api_key
export TOKENIZERS_PARALLELISM=false  # Suppress HuggingFace warning
```

### Run

```bash
# Start Jupyter
uv run jupyter lab

# Open ml_model_evals.ipynb
```

## Configuration

| Variable | Description | Required |
|----------|-------------|----------|
| `LANGSMITH_API_KEY` | API key for LangSmith evaluations | Yes |
| `OPENAI_API_KEY` | API key for the LLM powering the agent | Yes |
| `TOKENIZERS_PARALLELISM` | Set to `false` to suppress tokenizer warnings | No |

## Additional Notes

- **Use Case**: The notebook uses clinical trial participant feedback analysis as an example, but the pattern applies to any ML model used as an agent tool.
- **Costs**: Running evaluations will incur OpenAI API costs for the agent and LLM-as-judge evaluators.
- **LangSmith Experiments**: All evaluation results are viewable in the LangSmith Experiments UI for comparison.

### Related Resources

- [LangSmith Evaluation Documentation](https://docs.smith.langchain.com/evaluation)
- [LangGraph Documentation](https://langchain-ai.github.io/langgraph/)
- [OpenEvals Library](https://github.com/langchain-ai/openevals)

## License

MIT

