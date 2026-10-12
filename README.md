# SIGMOD23Experiments

A self-contained container for reproducing the experimental results of:

- Zilu Tian, Peter Lindner, Markus Nissl, Christoph Koch, and Val Tannen. *"Generalizing bulk-synchronous parallel processing for data science: From data to threads and agent-based simulations."* Proc. ACM Manag. Data (SIGMOD), 2023.
- Zilu Tian. *"Multi-stage vertex-centric programming for agent-based simulations."* Proc. of the 22nd ACM SIGPLAN International Conference on Generative Programming: Concepts and Experiences (GPCE), 2023.

## Systems

In the SIGMOD paper, we reviewed existing BSP-like systems — Spark, GraphX, Giraph, and Flink (Gelly) — and compared their performance with our system **CloudCity**. We proposed a set of simulation workloads from areas where simulations are prevalent: population dynamics (`gameOfLife`), economics (`stockMarket`), and epidemics, and implemented these workloads on each system.

Each folder below contains the full source, benchmark configuration, driver scripts, and measured results for one system. The input graphs for all of these systems can be generated from `ExperimentGraphs`.

| Folder | System | Notes |
|---|---|---|
| `CloudCityExperiments/` | CloudCity (ours) | thread-based BSP runtime |
| `SparkExperiments/` | Spark 3.3 | vertex programs in `/src/main/scala/simulations/` |
| `GraphxExperiments/` | GraphX (Spark 3.3) | vertex programs in `/src/main/scala/simulations/` |
| `GiraphExperiments/` | Apache Giraph | vertex programs, see `checkstyle*.xml` for code conventions |
| `FlinkExperiments/` | Flink 1.16.1 | vertex programs in `/src/main/scala/simulations/` |
| `ExperimentGraphs/` | — | graph generator shared by all systems |
| `Flink-SSSP/` | Flink 1.16.1 | minimal example of an iterative algorithm in Flink (Scala 2.12) |

## Benchmark

Each system folder documents its own benchmark experiments (tuning, scaleup, scaleout, communication frequency, computation interval). In short: build the vertex program, then run a benchmark named `{test}` with

```
python3 bin/bench.py -t test
```

(from within the system folder; see that folder's `README.md` for details). Measured results for reference live under each system's `benchmark/`.

## Setup

Experiments were run on a cluster of servers running CentOS 7 with Java 8. Each server has 24 cores (two Intel Xeon E5-2680, 48 hardware threads), 256 GB of RAM, and 400 GB of SSD, connected via two 10 Gb Ethernet NICs.
