# Self-Hosting SSOReady on Kubernetes

This guide outlines the steps to deploy **SSOReady** on your Kubernetes cluster. Ensure that you have a PostgreSQL database running within the same cluster before proceeding.

## Prerequisites

- A running PostgreSQL database in your Kubernetes cluster.
- Helm 3+ installed.
- Kubernetes 1.18+.
- The domain name for accessing the SSO services.
- letsencrypt
- nginx

## Steps to Deploy

### 1. Update Configuration Files

- The main configuration is defined in the `values.yaml` file. Update this file to set the necessary environment variables for your deployment.
  
- Make sure to customize the settings for each component by updating the `values.yaml` files located in the following directories:
  - `sso/values.yaml`
    
### 2. Configure PostgreSQL Connection

In the Helm chart, you'll need to configure the PostgreSQL database connection. In the `values.yaml` file, update the following sections:
- Database host
- Database port
- Username
- Password
- Database name

These settings ensure that all SSO components can connect to the PostgreSQL instance.

### 3. Update the Domain Name

Update your domain name for the SSO services in the configuration files. This is crucial for setting up access to the SSO admin and application interfaces.

### 4. Create the SSO Namespace

Create a dedicated namespace for the SSO components. Run the following command to create the `sso` namespace:

```bash
# create namespace
kubectl create namespace sso

#.Install the Helm Chart
helm install -n sso sso ./sso
```
### Reference
For more information, you can refer to the : https://ssoready.com/docs/self-hosting-ssoready .


