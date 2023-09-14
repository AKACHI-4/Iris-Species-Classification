# Iris Species Detection

Welcome to the Iris Species Detection repository! This project showcases the deployment of a machine learning model for identifying iris flower species using Azure ML.

## Overview

This repository contains code and configurations for deploying a machine learning model as a web service endpoint. The deployed model can classify iris flowers into different species based on their characteristics.

## Repo Structure 

The repository includes a `notebook.ipynb` file, which contains all the necessary dependencies and step-by-step instructions for use within Azure ML Studio.

## Prerequisites

Before you begin, please ensure you have the following prerequisites:

- An [Azure for Students subscription](https://azure.microsoft.com/free/students/).
- Familiarity with Azure ML Studio.

## Here are the steps to deploy the model 👇

- ### Azure Machine Learning Setup

  - Create an Azure Machine Learning workspace:

     - Utilize the [Azure portal](https://portal.azure.com) to set up your Azure Machine Learning workspace.
     - Retrieve the workspace details and update the `./config.json` file in your project directory with the necessary information.

  - Set up authentication credentials:

     - This script uses Azure Identity for authentication. It first attempts to use the DefaultAzureCredential, and if that fails, it falls back to InteractiveBrowserCredential for interactive login. Ensure you are authenticated using `az login` or provide your preferred authentication method as needed.

- ### Data Preparation

  The script utilizes an example dataset from Azure Storage. You have the flexibility to replace it with your dataset. Ensure that your dataset is accessible via a URL.

- ### Environment Configuration

  In this step, the script sets up the Python environment for model training. It creates a Conda environment defined in `./dependencies/conda.yaml`. You can customize this environment to meet your model's specific requirements.

- ### Model Training

  The script trains a machine learning model using the specified data and environment configuration. It uses Scikit-Learn's GradientBoostingClassifier as an example model. You have the option to replace it with your preferred machine learning algorithm.

- ### Model Registration

  After training, the model is registered in the Azure Machine Learning workspace. The registered model is then available for deployment.

- ### Endpoint Deployment

  The script deploys the trained model as an Azure Managed Online Endpoint. It allows you to create a deployment with a specified instance type (e.g., Standard_DS1_v2). Please note that the instance type selection should align with your subscription's available resources. If you encounter memory issues or quota limitations, consider upgrading your subscription or choosing a different instance type.

- ### Sample Inference

  Once the model is deployed, you can send inference requests to the endpoint. The script provides a demonstration of how to send a sample inference request using a JSON file (`./deploy/sample-request.json`). You can easily modify this file to send your input data for predictions.

- ### Contribute

  We welcome contributions! Feel free to raise an issue and start working on it. ❤
