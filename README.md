# minDG (Coming Soon)
A minimal DomainBed implementation, aims for fast experiment results.

## What's up with DomainBed?
[DomainBed](https://github.com/facebookresearch/DomainBed) is a great library for domain generalization research. However, the training and hyperparameter tuning processes are simply too time-consuming and expensive. This repository aims to provide a minimal implementation of DomainBed, which is used for fast-track experiments in cases when researchers simply want to test new methods.

## What are the new features?
We aim to provide the following features:
- DomainBed dataloaders: dataloaders from DomainBed are directly ported to this repository, which means that the data loading process is exactly the same as in DomainBed.
- `timm` models: we provide a wrapper for [`timm`](https://github.com/rwightman/pytorch-image-models) (PyTorch-Image-Models) models, which means that you can use any model from `timm` with minimal effort.
- DomainBed algorithms backward compatibility: users can directly use the `Alrgorithm` classes in DomainBed and minDG interchangably without any additional modification.
- Training-domain model selection: we offer the Training-domain model selection method like DomainBed.
- Extendable CLI: users can add CLI arguments more freely.
- Single environment or Iterative-Single environment: users can choose to perform DG on a single environment, or can run DG on all environments iteratively like DomainBed via `--train_all`. For example, on PACS with 4 environments, when `--train_all` is set to False (default) and `--test_envs 0`, only one run will be performed on the first environment. When `--train_all` is set to True, 4 runs will be performed with `--test_envs 0, test_envs, 1,...` and so on.
- `wandb` and `webhook` support: we support `wandb` logging and `webhook` notification via environment variables.

## What did we remove?
- No automatic hyperparameter tuning
- No other model selection methods except Training-Domain
- Only supports model saving (by now), not args or other metadata
- Only ERM is ported from DomainBed, but users are free to add other algorithms

## Benchmark (Coming Soon)
