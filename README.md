# Continuous deployment pipeline to deploy simple html website to AWS EKS cluster using CircleCI

This is a simple CICD pipeline using CircleCI that simplifies how to automatically deploy a container to an aws eks cluster. The idea is to help student in Udacity and developers to learn how to easily create a CICD pipeline for aws eks. 

**Important for Udacity Cloud DevOps students**

This pipeline is missing required jobs in rubric like: linting, image build/push

### Requirements

* CircleCI
* AWS EKS (Kubernetes)
* Dockerhub
* [**circleci/aws-eks@1.1.0s**](https://circleci.com/developer/orbs/orb/circleci/aws-eks)
* [**circleci/kubernetes@0.4.0**](https://circleci.com/developer/orbs/orb/circleci/kubernetes)

1. Create the CircleCI account

2. Create a GitHub repository

### Install

1. Download or clone this project

2. Push this project to your GitHub repository

3. In CircleCI setup the project.

Once on the Project page, find the project you are using and click Set Up Project.

![set up project](https://github.com/andresaaap/cicd-only-deploying-circleci/blob/main/img/set-up-project.png?raw=true)

According to the AWS EKS orb’s repo it is very important to meet these requirements before running the pipeline:

Add the AWS credentials as environment variables. Configure `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY` and `AWS_DEFAULT_REGION` as CircleCI project or context environment variables as shown in the links provided for [project](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project) or [context](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-context).

![create environment variables](https://github.com/andresaaap/cicd-only-deploying-circleci/blob/main/img/create-env-variables.png?raw=true)

Add the policies to the IAM user suggested in the official eksctl website as [Minimum IAM policies](https://eksctl.io/usage/minimum-iam-policies/)

### Usage

Run the Pipeline by pushing a new commit to the GitHub repository or manually in the project’s GUI in CircleCI

![successful pipeline run](https://github.com/andresaaap/cicd-only-deploying-circleci/blob/main/img/successful-pipeline-run.png?raw=true)

To access the website copy the Load Balancer URL:

![load balancer url](https://github.com/andresaaap/cicd-only-deploying-circleci/blob/main/img/loadbalancer-url.png?raw=true)

![website](https://github.com/andresaaap/cicd-only-deploying-circleci/blob/main/img/website.png?raw=true)

### Personalize the code for your Udacity project or other use cases

- You will need to put your image name in the deployment.json
- You will need to set the correct ports in the deployment.json and service.json
- You will need to set the correct Deployment and Service names in the config.yml


### Links & Resources

* [**What is a Deployment? | Google Kubernetes Engine (GKE)**](https://cloud.google.com/kubernetes-engine/docs/concepts/deployment)
* [**Deployments | Kubernetes Official Docs**](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/)
* [**How to create an AWS EKS cluster using CircleCI, AWS EKS Orb**](https://andresaaap.medium.com/how-to-create-an-aws-eks-cluster-using-circleci-aws-eks-orb-d09a4012fd1d)
