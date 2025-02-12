# Feelgood GmbH SAAS Helm Chart


- Sample code sourced from official documents, stackoverflow, Gen AI resources available online.

- This file aims to explain deployment of nginx, tomcat, artemis using kubernetes in multitenancy setup, how upgrades are handled, authetications are done and automating the deployment using argocd.

## Overview
Feelgood GmbH offers a SaaS solution in the form of a browser-based application. This Helm chart facilitates the deployment and management of the application components in a Kubernetes cluster. 

## System Architecture
The application consists of several components:
- **Nginx**: Responsible for serving static content and authentication with Keycloak (SSO).
- **Tomcat Server**: The core of the application that processes business logic as a multi-tenancy system.
- **Artemis Message Queue**: Manages message delivery between components.
- **Database**: Serves as the endpoint for data storage and retrieval.

## Objectives
To improve scalability and automation, the Feelgood application is deployed in a Kubernetes cluster. All necessary components are containerized (nginx, tomcat, schemagen, artemis).

## Repository Structure
```
feelgood-gmbh-saas-chart/
├── charts/
├── templates/
│   ├── argocd-application.yaml
│   ├── configmap.yaml
│   ├── deployment.yaml
│   ├── ingress.yaml
│   ├── maintainance-config.yml
│   ├── namespace.yaml
│   ├── secrets.yaml
│   ├── service.yaml
├── .gitignore
└── Chart.yaml
├── LICENSE.md
└── README.md
├── values.yaml
```
# Prerequisites
Ensure you have the following installed:
- Kubernetes
- Helm
- ArgoCD

# Installation

# 1. Clone the Repository
   
shell,
   
- git clone https://github.com/shahzeena1/feelgood-gmbh-saas-chart.git
   
- cd feelgood-gmbh-saas-chart

# 2. Deploy ArgoCD,

Follow the ArgoCD Official documentation to install ArgoCD on your Kubernetes cluster.

Apply the ArgoCD Application Configuration,

- kubectl apply -f templates/argocd-application.yaml

# 3. Deploy the Helm Chart,

- helm upgrade --install feelgood-gmbh-saas ./feelgood-gmbh-saas-chart


# Configuration,

- Modify the values.yaml file to suit your requirements. Key configurations include:

- image: Docker images for the application components.

- nginx, tomcat, artemis: Configuration for the application components.

- keycloak: Keycloak integration settings.

- maintenancePage: Maintenance page settings.

- ingress: Ingress settings.

- secrets: Database credentials.

- tenants: Tenant-specific configurations.

# Notes:

This setup assumes that the database is managed externally.

Replicas, high availability, and other advanced features are not covered in this context.

# License:

This project is licensed under the MIT License. See the LICENSE.md file for details.

# Contribution:

Please don't open any Pull Request as it's a dummy/non-functional code.

# Contact:

For any inquiries or support, please contact us at support@feelgoodgmbh.com(Dummy email).