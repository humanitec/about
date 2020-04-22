# Humanitec Roadmap

This document provides a high-level view on our product roadmap for this and upcoming quarters. It also lists roadmap items of past quarters.

## Q2 2020

## Q3 2020 and beyond

## Past quarters

### Q1 2020

#### Dynamic Environment Variable Management
Environment management across environments is complex and error-prone. With this feature, environment variables are classified as one of 3 types:
* **Static:** The same for each environment deployed in
* **Dynamic:** The platform can infer the different values that a variable should have in each environment via a system of “placeholders” and string formatting
* **Environment Specific:** Developers must either accept or update the value of the variable when being deployed to a different environment
For example, a dynamic environmental variable definition which resolves to the external DNS name of a module called “api-server” would be:

    API_SERVER_NAME = "${modules.api-server.service.externalName}"

#### Deployment Sets

**Deployment version history**

The full state of each deployment to an environment is recorded as a “deployment set”. Deployment sets can be compared to show differences between them. A previous deployment set can be redeployed to perform a rollback. Cloning one environment to another is done by applying a deployment set from one environment into another. As part of this, the Dynamic Environment Variable Management feature ensures that environmental variables are correctly handled.

**Serialization of Deployment Sets**

The deployment set is the unit of state that is used to serialize out Helm Charts that describe a particular deployment. These charts can be directed towards a git repository and so form part of a “GitOps” process.

#### Generalized Module Sources

The current version of the platform has a tight dependency on GitHub. This feature relaxes that dependency.

**Connect your CI**

Rather than building containers directly from source code, the platform will hook into the end of your CI pipeline. This allows any successfully built and tested container to be used directly in the platform.

**Import any Git Repository**

Rather than relying on the GitHub API, code can be pushed to the Humanitec platform using standard git primitives.  For example, customers could establish a remote branch with humanitec. Pushing code into the humanitec platform would then make that commit available to be deployed via the platform:

    $ git push humanitec master

#### External Modules (3rd Party In-Cluster Components / Services)

Many modern cloud-native applications make use of services and components based on popular open-source projects, for example, Redis or RabbitMQ. With this feature, we aim to build a growing set of curated, ready to deploy packages of these popular components and services. These packages can then be simply deployed into the cluster by developers.

#### Provisioning External Services

Many applications rely on databases and services that run external to the cluster. The platform already supports the automatic generation of Postgres databases via Google CloudSQL. This feature would extend the range of services supported. A stretch objective here is also to provide a way for developers to build their own implementation if the set of services supported by Humanitec does not cover what they need. 
