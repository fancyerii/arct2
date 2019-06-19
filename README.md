# Probing Neural Network Understanding of Natural Language Arguments

Authors: Timothy Niven and Hung-Yu Kao

Abstract:

> We are surprised to find that BERT's peak performance of 77\% on the Argument Reasoning Comprehension Task reaches just three points below the average untrained human baseline. However, we show that this result is entirely accounted for by exploitation of spurious statistical cues in the dataset. We analyze the nature of these cues and demonstrate that a range of models all exploit them. This analysis informs the construction of an adversarial dataset on which all models achieve random accuracy. Our adversarial dataset provides a more robust assessment of argument comprehension and should be adopted as the standard in future work.

## Adversarial Dataset

Provided in the `adv` folder.

The script `make_adversarial_dataset.py` provides dictionaries 
mapping the original to negated claims, and code to recreate them.
The versions we used in our experiments are in the `adv` folder.

## Viewing our Results

Each experiment has its own folder in the `results` folder.
The suffixes indicate the setup
- `cw` only considers claims and warrants
- `rw` only considers reasons and warrants
- `w` only considers warrants
- `adv` uses the adversarial dataset

Within each experiment's folder you will find
- `accs.csv`: contains accuracies for train, dev, and test over
  all random seeds
- `best_params.json`: lists the best parameters from grid search
- `grid.csv`: lists all grid search results and parameter
  combinations
- `preds.csv`: lists all predictions for all data points which
  can be filtered by dataset and queried by each data point's 
  unique identifier

You can get a summary of the accuracies over various random
seeds for an experiment by running

```
python accs.py experiment_name 
```

For details of how each experiment is run, you can view the
files in the `experiments` folder.

## Reproducing our Results

Package requirements are listed in `requirements.txt`.

First, prepare the data by running `prepare.sh`.

To reproduce the results of any of the experiments run the
script

```
python run.py experiment_name
```

## Reference

Todo: add bibtex reference.