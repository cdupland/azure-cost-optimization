# Azure Stream Analytic
## Overview
Our target goal is to optimize resource usage and only run our Stream Analytics Job when needed.
We will use an Azure Function to control the job state and stop it by leveraging the Azure Management SDK with a simple API call.

## Requirements
You need the following resources before starting:
* Create a service principale that will be used to autorize the Management SDK to work on your subscription
    * Use the [azure cli](http://shell.azure.com) 
    * Log in:
        * az login
    * Set default subscrition:
        * az account set -s <name or ID of subscription>
    * Create a service principal:
        * az ad sp create-for-rbac --sdk-auth
    * Write down:
        * ClienID, ClientSecret, TenantID and SubscriptionID
* Create an Azure Function
* Add the following Application Settings
    * "DefaultASAJobName": Stream Analytics Job to Stop
    * "DefaultASAJobRG": Resource group of the where the Azure Stream Analytics Job is deployed
    * "SDK-ClientId"
    * "SDK-ClientSecret"
    * "SDK-TenantId"
    * "SDK-SubscriptionId"
  *Compile Deploy the [Azure Function project](../OptimiseAzureResources.sln)
  *Compile Deploy the [Azure Function project](../)