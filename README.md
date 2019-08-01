# Environment set up guideline

The tutorial environment can be set up by three different options

## Option 1 - Local machine 
The code examples and notebooks from Microsoft/Recommenders repository can be run on a local machine with Linux, Windows, or MacOS system. Details about about how to set up environment on a local machine can be found in the the [SETUP.md](https://github.com/microsoft/recommenders/blob/master/SETUP.md) file of the Microsoft/Recommenders repository.

## Option 2 - Docker
Alternative to running notebooks on a local environment, Docker support is also provided. Instructions for building a Docker image with the Docker file provided in the repository can be found [here](https://github.com/microsoft/recommenders/blob/le_docker/docker/README.md). 

There are pre-built images available on Dockerhub for use. 

|Environment|Image name|
|------------|-----------|
|CPU|yueguoguo/reco_cpu|
|PySpark|yueguoguo/reco_pyspark|
|GPU|yueguoguo/reco_gpu|
|Full|yueguoguo/reco_full|

The pre-built images (e.g., the CPU environment) can be used directly by the following command,
```
docker pull yueguoguo/reco_cpu
```

## Option 3 - Azure Data Science Virtual Machine (DSVM)
The setup process on an [Azure Data Science Virtual Machine](https://azure.microsoft.com/en-us/services/virtual-machines/data-science-virtual-machines/) is the same as that for a local environment. Details of HOW-TO can be therefore found [here](https://github.com/microsoft/recommenders/blob/master/SETUP.md).
