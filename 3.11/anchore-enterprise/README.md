# Anchore Enterprise Installation on OKD 3.11

This document will walkthrough installing Anchore Enterprise on OpenShift Kubernetes Distribution (OKD) 3.11 with Helm. Anchore maintains a Helm chart for simplifying the deployment. You can find out more information by checking out the [GitHub Repository](https://github.com/helm/charts/tree/master/stable/anchore-engine) for the chart. 

## Prerequisites

- OpenShift Kubernetes Distribution (OKD) 3.11 installed. Read more about the installation requirements [here](https://docs.okd.io/3.11/install/running_install.html).
- [Helm](https://helm.sh/) client and server installed and configured within your OKD cluster.

## Anchore Helm Chart

Anchore maintains a [Helm chart] to simplify the software installation process. An Enterprise installation of the chart will include the following:

- Anchore Enterprise Software
- PostgreSQL (9.6.2)
- Redis 4

To make the necessary configurations to the Helm chart, create a custom anchore_values.yaml file and reference it during installation. There are many options for configuration with Anchore, this document is intended to cover the minimum required changes to successfully install Anchore Enterprise on OKD 3.11.

**Note:** Due to permission constraints when utilizing OpenShift, the official RHEL PostgreSQL image must be utilized, which requires custom environment variables to be configured for compatibility with this chart.

### Configurations



