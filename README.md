# Interrupt Bench

Interrupt bench studies models' robustness to unusual interruption between agent loops.

## Methodology

We adopt the [ExploitBench](https://github.com/exploitbench/exploitbench) as they are one of the benchmarks considered unflawed according to [Epoch AI's review](https://epoch.ai/benchmarks). Compared with other benchmarks like SimpleQA Verified, ExploitBench requires long-horizon agent run and multi-turn tool calls. Which better serves our research purpose.

The agent will be interrupted each ~1k output token. Then, the API call is retried with an empty user message. All other agent environment completely replicates ExplointBench.
