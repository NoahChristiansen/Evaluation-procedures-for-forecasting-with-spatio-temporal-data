# Evaluation procedures for forecasting with spatio-temporal data

This repository contains the research compendium of "Evaluation procedures for forecasting with spatio-temporal data", authored by Mariana Oliveira, Luis Torgo, and Vitor Santos Costa, and presented at ECML-PKDD 2018.


## Prerequisites

To install this package, run:

```
library(devtools)  # You need to install this package!
install_github("mrfoliveira/Evaluation-procedures-for-forecasting-with-spatio-temporal-data", ref="master")
```

To replicate figures, installing the following package is also necessary:

```
if(!("ggplot2" in installed.packages())) install.packages("ggplot2")
```

## Reproducing experiments

To run experiments, run the following lines from the main directory:

```
library(STEvaluationPaper)
source("analysis/step1_gen_data.R")
source("analysis/step2_artificial_experiments.R")
source("analysis/step3_real_experiments.R")
```

## Contents

The repository is organized as follows:
* **data** - Contains the real-world data sets used in the experiments in an appropriate format
* **inst/analysis** - Contains scripts for generating data and launching experiments
* **inst/results** - Contains files of the results presented in the paper
* **man** - Contains function documentation
* **R** - Contains reusable functions

#### R

* analyse\_utils.R - functions that can be used to summarize produced by experiments
* calc_metrics.R - functions to calculate error metrics
* experiment_utils.R - functions designed to launch experiments
* fold_alloc.R - functions for allocating observations to cross-validation folds
* gen\_data\_utils.R - functions needed to generate lists of STARMA-generated datasets, depends on starma_utils.R
* methods.R - functions implementing different error estimation methods, depends on fold_alloc.R, utils.R
* starma_utils.R - functions needed to generate STARMA artificial data and check coefficient stationarity
* st_indicators.R - functions designed to calculate spatio-temporal indicators
* utils.R - general utility functions used inside some evaluation methods
* workflow.R - functions needed for the multiple steps in experiments, including learning, generating and evaluating predictions


#### inst/analysis

* step1_gen_data.R - data generation script
* step2_artificial_experiments.R - running experiments on artificially generated datasets
* step3_real_experiments.R - calculating spatio-temporal indicators and running experiments on real data sets
