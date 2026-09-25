# Interrupt Bench

Interrupt bench studies models' robustness to unusual interruptions between agent loops.

## Motivation

In RL, models are usually set in a stable agent environment. Where:

1. The network is always stable
2. No users are interjecting

This is not the case on real user clients. All kinds of factors might cause an API failure/interruption during the agent loop. Hence, models are forced to face this rather unusual pattern during their training and must recover to their ongoing work. This benchmark evaluates how well models mitigate frequent interruptions.

## Methodology

We adopt the [ExploitBench](https://github.com/exploitbench/exploitbench) as it is one of the benchmarks considered unflawed according to [Epoch AI's review](https://epoch.ai/benchmarks). Compared with other benchmarks like SimpleQA Verified, ExploitBench requires long-horizon agent runs and multi-turn tool calls. This better serves our research purpose.

The agent will be interrupted every ~1k output tokens. Then, the API call is retried with an empty user message. All other agent environment completely replicates ExplointBench.

## Acknowledgement

Thanks to [a friend](https://github.com/johnbean393) for asking this.
