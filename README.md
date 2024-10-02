# Azure Function App: Start and Stop VM

This Azure Function App automates the starting and stopping of a Virtual Machine (VM) in Azure. The VM is configured to start at 7 AM and stop at 5 PM from Monday to Friday.

## Features

- Starts a specified VM in a defined resource group.
- Stops the same VM at a specified time.
- Utilizes Azure's managed identity for authentication and authorization.

## Prerequisites

- An Azure subscription.
- Azure SDK for Python.
- Azure Function App setup.

## Configuration

### Environment Variables

Make sure to set the following environment variables in your Azure Function App configuration:

- **AZURE_SUBSCRIPTION_ID**: Your Azure subscription ID.
- **RESOURCE_GROUP**: The name of the resource group where your VM resides (e.g., `Lab-Win11`).
- **VM_NAME**: The name of the VM you want to start and stop (e.g., `win11`).

### Python Packages

Ensure that the following Python packages are included in your Function App:

- `azure-functions`
- `azure-identity`
- `azure-mgmt-compute`

## Functionality

### Start VM

The `start_vm` function initiates the specified VM using the Azure Compute Management client. This function is triggered by a timer to run at 7 AM (UTC+1) from Monday to Friday.

### Stop VM

The `stop_vm` function stops the specified VM using the Azure Compute Management client. This function is triggered by a timer to run at 5 PM (UTC+1) from Monday to Friday.

## Usage

1. Deploy the Azure Function App to your Azure account.
2. Set the required environment variables.
3. Monitor the logs to ensure the VM starts and stops as scheduled.

## Logging

Logging is set up to provide feedback on the operations of starting and stopping the VM. You can view logs in the Azure portal under the Function App's "Log stream".

## Troubleshooting

- Ensure that the environment variables are correctly set.
- Verify that the VM and resource group names are correct.
- Check Azure logs for detailed error messages if the VM fails to start or stop.

## License

This project is licensed under the MIT License.
