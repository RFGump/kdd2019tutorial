# Environment set up guideline

The tutorial environment can be set up by three different options

|Option|Prerequisite|Pros|Cons|
|------------|-------------|-----------|--------------|
|Local machine|Standalone single-node Spark/Miniconda/Jupyter notebook|Users can use tools they are familiar with in the local machine|Limited by the environment (e.g., OS) and hardware of the local machine (e.g., GPU)|
|Cloud (Azure)|Azure subscription|High flexibility to run notebooks on heterogeneous environment and computing targets|Starts with free credits (200 USD) but will be charged after the credits are used up|
|**Docker container**|**Docker**|**Portable and environment-independent**|**Require Docker to be pre-installed**|

## Option 1 - Local machine 
The code examples and notebooks from Microsoft/Recommenders repository can be run on a local machine with Linux, Windows, or MacOS system. Details about how to set up environment on a local machine can be found in the the [SETUP.md](https://github.com/microsoft/recommenders/blob/master/SETUP.md) file of the Microsoft/Recommenders repository.

**NOTE** in the tutorial, we have notebooks that run in a Spark environment. If the local environment without Spark is used, the notebooks cannot be successfully run. 

## Option 2 - Azure Data Science Virtual Machine (DSVM)
The setup process on an [Azure Data Science Virtual Machine](https://azure.microsoft.com/en-us/services/virtual-machines/data-science-virtual-machines/) is the same as that for a local environment. Details can be found [here](https://github.com/microsoft/recommenders/blob/master/SETUP.md).

## Option 3 - Docker
Alternative to running notebooks on a local environment, Docker support is also provided. Instructions for building a Docker image with the Docker file provided in the repository can be found [here](https://github.com/microsoft/recommenders/blob/le_docker/docker/README.md). 

In the tutorial, Docker is preferred to run the notebooks used in the Microsoft/Recommenders repository given its portability to various platforms and inclusion of different framework (i.e., Spark, Tensorflow, etc.)

Before running the Docker image in a container, one needs to install Docker
* [Install on Windows 10](https://runnable.com/docker/install-docker-on-windows-10)
* [Install on Linux](https://runnable.com/docker/install-docker-on-linux)
* [Install on MacOS](https://docs.docker.com/docker-for-mac/install/)

Building Docker image in time may take some time. There are pre-built images available on Dockerhub for use. 

|Environment|Image name|
|------------|-----------|
|CPU|yueguoguo/reco_cpu|
|**PySpark**|**yueguoguo/reco_pyspark**|
|GPU|yueguoguo/reco_gpu|
|Full|yueguoguo/reco_full|

In the tutorial, we use the PySpark one where the single-node Python and PySpark codes can run. To use these images, one needs to [create a Docker Hub account](https://hub.docker.com/signup). Assuming Docker has been installed, in either the Linux/MacOS terminal or Windows PowerShell, commands to run for practising the notebooks are as below:

1. Pull the image
```
docker pull yueguoguo/reco_pyspark
```
2. Check if the images exist
```
docker images
```
3. Run the Docker container (here the port of 8888 from the container is tunnelled to the local system)
```
docker run -p 8888:8888 yueguoguo/reco_pyspark
```
One should see the follows, which indicates that the container is running successfully. 
4. Go to the browser, and launch the Jupyter notebooks by `localhost:8888`.

A few commands that help use Docker 
* Check the images available in local environment, `docker images`
* Check the running containers, `docker ps`
* Remove a container, `docker rm <container_id>`
* Remove an image, `docker rmi <image_id>`
* Remove all containers, `docker rm $(docker ps -a -q)`
* Remove all images, `docker rmi $(docker images -a -q)`
