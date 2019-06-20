[![CircleCI](https://circleci.com/gh/jalilromrani/Operationalize-a-Machine-Learning-Microservice-API.svg?style=svg)](https://circleci.com/gh/jalilromrani/Operationalize-a-Machine-Learning-Microservice-API)

## Project Overview

In this project, I apply the skills I have acquired in [Cloud Dev Ops Engineer](https://www.udacity.com/course/cloud-dev-ops-nanodegree--nd9991) program to operationalize a Machine Learning Microservice API. 

I'm given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests my ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

The project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* If you haven't already done so, clone the [project repository](https://github.com/jalilromrani/Operationalize-a-Machine-Learning-Microservice-API), and navigate to the project folder.

```
git clone https://github.com/jalilromrani/Operationalize-a-Machine-Learning-Microservice-API.git
cd Operationalize-a-Machine-Learning-Microservice-API
```

* Create a virtualenv and activate it

```
python3 -m venv ~/.devops
source ~/.devops/bin/activate
```

* Run `make install` to install the necessary dependencies

```
make install
```

## Other Libraries
While you still have your .devops environment activated, you will still need to install:
* Docker
* Hadolint
* Kubernetes (Minikube)

### Docker
You will need to use Docker to build and upload a containerized application. If you already have this installed and created a docker account, you may skip this step.

1. You’ll need to [create a free docker account](https://hub.docker.com/signup), where you’ll choose a unique username and link your email to a docker account. **Your username is your unique docker ID.**
2. To install the latest version of docker, choose the Community Edition (CE) for your operating system, [on docker’s installation site](https://docs.docker.com/v17.12/install/). It is also recommended that you install the latest, **stable release.**
3. After installation, you can verify that you’ve successfully installed docker by printing its version in your terminal: `docker --version`

### Run Lint Checks
This project also must pass two lint checks; `hadolint` checks the Dockerfile for errors and `pylint` checks the `app.py` source code for errors.

1. Install `hadolint` following the instructions, [on hadolint's page](https://github.com/hadolint/hadolint):
- **For Mac:**
```
 brew install hadolint
```
- **For Windows:**
```
scoop install hadolint
```
2. In your terminal, type: `make lint` to run lint checks on the project code. If you haven’t changed any code, all requirements should be satisfied, and you should see a printed statement that rates your code (and prints out any additional comments):
```
------------------------------------
Your code has been rated at 10.00/10
```
Your terminal should look something like this:
![make lint](output_txt_files/0 - make lint.png)

### Install Minikube
To run a Kubernetes cluster locally, for testing and project purposes, you need the Kubernetes package, Minikube. This operates in a virtual machine and so you'll need to download two things: A virtual machine (aka a hypervisor) then minikube. Thorough installation instructions can be found [here](https://kubernetes.io/docs/tasks/tools/install-minikube/). Here is how I installed minikube:

1. Install VirtualBox
- **For Mac:**
```
brew cask install virtualbox
```
- **For Windows:**
```
I recommend using a [Windows host](https://www.virtualbox.org/wiki/Downloads).
```
2. Install minikube:
- **For Mac:**
```
brew cask install minikube
```
- **For Windows:**
```
I recommend using the [Windows installer](https://kubernetes.io/docs/tasks/tools/install-minikube/).
```

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl
