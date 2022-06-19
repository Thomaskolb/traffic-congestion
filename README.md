# Traffic congestion

In order to get started with the code in this repository, make sure Jupyter is installed so you can run Jupyter notebooks.

Open the notebook with Jupyer and run the following sections:

- **Imports** import dependencies.
- **Data objects**: define the graph structure.
- **Helper functions**: a collection of functions that will be used later on (including the RandDijkstra algorithm and the diversity score).
- **Cross-over functions + mutation operators**: Roundabout, newRoute, randomP, exSegment, exhaustive crossover, and some MREA helper functions.
- **MREA**: the MREA algorithm itself, see the paper for details and pseudocode.
- **Graph generation**: generates an MR instance in the form of a graph with the structure defined above.

Now we are ready to actually run the algorithm and perform some tests to make sure everything is working as expected. Run the code cells in the following sections to perform some quick tests.

- **Initial test of algorithm**: run the algorithm with a small sample size to verify that it works as intended.
- **Ablation testing code**: not included in the paper.

Run the subsequent sections to reproduce the experiments from our paper or modify parameters to run your own experiments.

- **Experiment: individual mutation operator performance**
- **Experiment: testing mutation operators with and without Roundabout for different connectivity graphs**
- **Experiment: population size (MU) test**

The experiments will also generate plots of the results.

Some sample output and plots are saved in the notebook itself, so they should be visible if you open it. Once you run it, you will overwrite those results with your own output.

The MREA tends to produce a warning message that `get_previous_vertex` is already the first vertex. This happens if a connection is created from a vertex to itself. In this case, the mutation operator will be ignored. This is typically not a problem in practice, so you can simply ignore these warnings for now.

The parameters you can experiment with are:

- **k**: number of drivers.
- **mu**: population size. Typically a low value. If mu is 1, no crossover is performed.
- **n**: the number of routes a driver can choose from. The default value is 2.
