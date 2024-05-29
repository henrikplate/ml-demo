# ml-demo

## Motivation

Dependencies of ML/AI applications are sometimes satisfied through manual or scripted installation in development environments or CICD pipelines, or by means of containers.

The reason to not use manifest files is that specific hardware environments and dependency combinations are not managed or manageable through PIP.

However, the risk is that those dependencies are overlooked, and this repository is meant to check whether SCA tools can successfully identify dependencies that are not managed through manifest files.

## Setup

`setup.py` declares a dependency on Hugging Face [transformers](https://github.com/huggingface/transformers).

Transformers, in turn, expects one of Tensorflow, Pytorch or JAX installed in its environment, cf. its installation [instructions](https://github.com/huggingface/transformers/tree/a564d10afe1a78c31934f0492422700f61a0ffc0?tab=readme-ov-file#installation). 

In this experiment, we install tensorflow manually via `pip install tensorflow` in a virtual environment.

The SCA tools are pointed to the directory containing a clone of this repository and the `.venv` subdirectory.

## Results

We tested three SCA tools and the following table reports the number of dependencies found by each.

