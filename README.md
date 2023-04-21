# SIGMOD23Experiments
This is a container for reproducing the experimental results in our SIGMOD paper 
*"Generalizing Bulk-Synchronous Parallel Processing: From Data to Threads and Agent-Based Simulations"*.

### Systems
In our paper, we reviewed existing BSP-like systems, including Spark, GraphX, Giraph, and Flink (Gelly), and compared their performance with our system CloudCity. 
We proposed a set of simulation workloads selected from areas where simulations are prevalent: population dynamics (gameOfLife), economics (stockMarket), and epidemics, 
and implemented these workloads on each system. 
You can find the scripts and experimental results for each system in the corresponding folder, whose names are self-explanatory. The input graphs for each of these systems can be generated from `ExperimentGraphs`.

### Setup
We used a cluster of servers running CentOS 7, with Java 8 installed. Each server has 24 cores (two Intel Xeon E5-2680, 48 hardware threads), 256GB of RAM, and 
400GB of SSD. Each server connects to routers through two 10Gb Ethernet network interface cards.
