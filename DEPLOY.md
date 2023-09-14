# Model Deployment 

It's an overview of the steps and components involved in deploying a machine learning model using Azure ML. The provided Python script demonstrates the process of creating a machine learning pipeline, training a model, registering it, and deploying it as a web service endpoint.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Azure Machine Learning Setup](#azure-machine-learning-setup)
3. [Data Preparation](#data-preparation)
4. [Environment Configuration](#environment-configuration)
5. [Model Training](#model-training)
6. [Model Registration](#model-registration)
7. [Endpoint Deployment](#endpoint-deployment)
8. [Sample Inference](#sample-inference)
9. [Troubleshooting](#troubleshooting)

## Prerequisites

Before you begin, make sure you have the following prerequisites:

- An [Azure for Students subscription](https://azure.microsoft.com/free/students/).
- Python 3.8 or later.
- Azure Machine Learning SDK installed (`azureml-sdk`).
- Azure CLI installed and authenticated.

## Azure Machine Learning Setup

1. Create an Azure Machine Learning workspace:

   - Use the [Azure portal](https://portal.azure.com) to create an Azure Machine Learning workspace.
   - Retrieve the workspace details and update the `./config.json` file in your project directory with the necessary information.

2. Set up authentication credentials:

   - This script uses Azure Identity to authenticate. It first tries to use the DefaultAzureCredential, and if that fails, it falls back to InteractiveBrowserCredential for interactive login. Ensure you are authenticated using `az login` or provide your own authentication method as needed.

## Data Preparation

The script uses an example dataset from Azure Storage. You can replace it with your own dataset. Ensure that your dataset is accessible via a URL.

## Environment Configuration

In this step, the script sets up the Python environment for model training. It creates a Conda environment defined in `./dependencies/conda.yaml`. You can customize this environment based on your model's requirements.

## Model Training

The script trains a machine learning model using the specified data and environment configuration. It uses Scikit-Learn's GradientBoostingClassifier as an example model. You can replace it with your own machine learning algorithm.

## Model Registration

After training, the model is registered in the Azure Machine Learning workspace. The registered model can be used for deployment.

## Endpoint Deployment

The script deploys the trained model as an Azure Managed Online Endpoint. It creates a deployment with a specified instance type (e.g., Standard_DS1_v2). Please note that the instance type should be chosen based on your subscription's available resources. If you encounter memory issues or quota limitations, you may need to upgrade your subscription or select a different instance type.

## Sample Inference

Once the model is deployed, you can send inference requests to the endpoint. The script demonstrates how to send a sample inference request using a JSON file (`./deploy/sample-request.json`). You can modify this file to send your own input data for predictions.

## Troubleshooting

If you encounter issues related to memory limitations or service unavailability due to your subscription type, refer to the [Azure troubleshooting guide](https://aka.ms/oe-tsg#error-outofquota) for guidance on resolving these issues. If necessary, consider upgrading your Azure subscription for better resource availability.

Please feel free to reach out to Azure Support for further assistance with subscription-related issues.

For more information and advanced configurations, refer to the [Azure Machine Learning documentation](https://docs.microsoft.com/azure/machine-learning/).
