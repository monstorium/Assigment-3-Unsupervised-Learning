# Unsupervised Learning and Dimensionality Reduction
VARUN GIRIDHAR (3.24.2019)

LINK TO CODE & DATA:
https://github.com/monstorium/Assigment-3-Unsupervised-Learning/tree/master/assignment3

# Data Sets
Data Set #1: '/data/blood-transfusion-service.csv'
Data Set #2: '/data/monks-problem.csv'

These data sets are cited in the pdf for the paper for assignment 3.

# Note About The Code
This code is "heavily inspired" by Chad Maron's code for CS 7641 from Fall 2018. It can be found here: https://github.com/cmaron/CS-7641-assignments/tree/master/assignment3

## Requirements
You will need to use python 3.x with this code, and to pip install the packages in `requirements.txt`. The main addition here is the tables module which _does_ require HDF5. If you are using OS X with Homebrew you can simply `brew install hdf5` before installing the requirements. 
If this does not work for you, try the `requirements-no-tables.txt` file. Windows users have noted the need to install the tables module but on some systems this is not required. 

## Overall Flow
1. Update `run_experiment.py` to use your data sets for dataset1 and dataset2. Also set `best_nn_params` for your data sets (lines 94 and 101).
2. Run the various experiments (perhaps via `python3 run_experiment.py --all`)
3. Plot the results so far via `python3 run_experiment.py --plot`
4. Update the dim values in `run_clustering.sh` based on the optimal values found in 2 (perhaps by looking at the scree graphs)
5. Run `run_clustering.sh`
6. One final run to plot the rest `python3 run_experiment.py --plot`

There are clearly some redundant steps here but thankfully the plotting is pretty fast compared to the data generation.

## Output
Output CSVs and images are written to `./output` and `./output/images` respectively. Sub-folders will be created for each DR algorithm (ICA, PCA, etc) as well as the benchmark.

If these folders do not exist the experiments module will attempt to create them.

## Clustering Experiments

The experiments will output modified versions of the data sets after applying the DR methods. The script `run_clustering.sh` can be used to perform clustering on these modified datasets, using a specific number of components for the DR method.

**BE SURE TO UPDATE THE VALUES IN THIS SCRIPT FOR YOUR DATASETS**. 

There are different optimal values for each algorithm and each dataset, and using the wrong value will make you a sad panda.

## Graphing

The run_experiment script can be use to generate plots via:

```
python3 run_experiment.py --plot
```

Since the files output from the experiments follow a common naming scheme this will determine the problem, algorithm,
and parameters as needed and write the output to sub-folders in `./output/images`.

