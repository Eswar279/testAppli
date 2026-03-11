# Sample Azure DevOps Node.js Web Apps

This workspace contains two simple Node.js Express applications (`app1` and `app2`) along with reusable Azure DevOps pipeline templates.

## Overview

The following steps outline the infrastructure and automation setup:

1. **Create Azure DevOps organization** (https://dev.azure.com).
2. **Create two repositories** inside that organization (e.g. `app1` and `app2`).
   - Push the contents of the `app1` and `app2` folders to the respective repos.
3. **Create a free Azure portal account** (https://portal.azure.com). A credit card is required, but the resources used here are free.
4. **Create a subscription** and then two resource groups: `app1-rg` and `app2-rg`.
5. **Create two Azure Web Apps** (App Service) named `app1web` in `app1-rg` and `app2web` in `app2-rg` using the free F1 tier.
6. **Use Azure DevOps Deployment Center** or manual configuration to set up pipelines.
   - The included `azure-pipelines.yml` files reference a reusable template in `templates/deploy-template.yml`.
   - Configure an Azure service connection (`azureServiceConnection`) in DevOps to allow the pipeline to deploy.
7. The `templates/deploy-template.yml` file can be shared across multiple apps to keep pipelines DRY.

## Local Development

Each app can run locally:
```
cd app1
npm install
npm start
```

```
cd app2
npm install
npm start
```
