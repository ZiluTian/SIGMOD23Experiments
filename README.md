# SIGMOD23Experiments
This is a container for reproducing the experimental results in our SIGMOD paper 
*"Generalizing Bulk-Synchronous Parallel Processing: From Data to Threads and Agent-Based Simulations"*.

### Systems
In our paper, we reviewed existing BSP-like systems, including Spark, GraphX, Giraph, and Flink (Gelly), and implemented the same set of simulation workloads on each system. 
The workloads contain applications selected from areas where simulations are prevalent: population dynamics (gameOfLife), economics (stockMarket), and epidemics. 
You can find the scripts and experimental results for each system in the corresponding folder, whose names are self-explanatory. 
The directory `ExperimentGraphs` contais the scripts for generate graphs used in each of the system.

### Setup
We used a cluster of servers running CentOS 7, with Java 8 installed. Each server has 24 cores (two Intel Xeon E5-2680, 48 hardware threads), 256GB of RAM, and 
400GB of SSD. Each server connects to routers through two 10Gb Ethernet network interface cards.
