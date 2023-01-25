# Humanitec Roadmap

This document provides a high-level view on our product roadmap for this and upcoming quarters.

## Now

### Humanitec Operator

Humanitec works in an interactive way with infrastructure. This means that Humanitec handles the whole deployment process by making calls to the affected systems (Kubernetes clusters, databases etc.) either directly or via drivers such as the [Terraform driver](https://docs.humanitec.com/integrations/resource-drivers/terraform). This approach can cause inconsistencies with deferred deployment strategies such as when using a GitOps operator like ArgoCD. The Humanitec Operator aims to move functionality currently managed server side by Humanitec into the cluster. This would allow things like resource provisioning to occur as part of a GitOps flow. As the operator also runs in-cluster it would also simplify the use of custom drivers since these would not need to be publicly exposed.

### Custom Workload Profile Features

[Workload Profiles](https://docs.humanitec.com/reference/workload-profiles) are a way to define the baseline configuration of a workload. Humanitec provides a number of default workload profiles and users have been able to add their own. Up to this point, platform teams have been limited to the UI provided by Humanitec. Custom Workload Profile features will allow platform teams to define schemas for their features and annotate these schemas to generate custom UI elements. This will allow platform teams to fully customize the developer experience for their Custom Workload Profiles.

### Global Navigation

Following several months of user testing and customer feedback, we are planning on introducing several changes to improve the usability, predictability and scalability of our UI. The focus lies on creating a better experience for navigating the Humanitec application. We want to address issues related to information hierarchy and aesthetics by touching on UI patterns that will likely change the look and feel of the UI.

### Deployment Set v1.0

A Deployment Set in Humanitec contains all of the environment-agnostic configurations for an Application. It describes the material things that should run or be provisioned in an environment. With the introduction of a new deployment set version (v1.0), we’re planning to replace legacy terminology with a naming convention better aligned with industry and Kubernetes standards and unify it across Humanitec’s UI, API and CLI. New vocabulary will be more familiar and intuitive for the platform teams and developers, improving the experience of using the Humanitec application, especially for new users.

### Improved System Health Status Messaging

Debugging a failure in a deployment is almost universal - at some point both developers and platform engineers will need to understand the causality and placement of errors. To increase visibility and support users when troubleshooting issues, status messaging in the Humanitec UI is being reworked. The health of an environment, deployment statuses as well as workload runtime statuses should be visible to the user at first sight and extensive error messaging in case of failures provided.

### Scoped API Tokens

Almost all requests made to the Humanitec API require authentication. Humanitec allows users to retrieve API tokens from their organization settings to authenticate with the API. Scoped API tokens present a new way of creating and managing API tokens with increased security and visibility. To obtain a token, users will need to create a service user with an assigned set of RBAC roles. An API token can then be generated from the user and is used to interact with Humanitec’s API on the service user’s behalf.

### Humanitec CLI Beta-level Release

The Humanitec Command Line Interface (CLI) allows users to get your everyday DevOps tasks (e.g., create a new temporary environment to test new features, add new services to an application) done without ever leaving their favourite console. After conducting a final round of testing and development in closed beta, are we planning to release the CLI in open beta for public use.

## Next

### Deployment Pipelines

It is often the case that additional actions need to be performed before or after deployments. For example, tests can be run to verify the environment and if they pass the deployment can be automatically promoted to the next environment. A deployment pipeline defines a set of steps that specify how a service is deployed, verified or rolled back. This feature aims to allow actions to be run based on the outcome of a deployment or to orchestrate additional actions.

### Agent Based Approach for Deploying to Private Clusters

A common approach used by SaaS products to access private resources is an agent. The agent runs inside the private infrastructure and calls out to Humanitec. This means that nothing in the private infrastructure is exposed to the public internet. This is considered best practice from a security perspective as nothing is exposed publicly and the operations team have complete control over what the agent has access to. It is also easier to administer than other approaches supported by Humanitec including bastion hosts and VPNs. The Humanitec Agent will give operations teams a flexible, easy to configure and secure way of using Humanitec with private infrastructure.

### Improved Deployment Diff

Deployment Diffs allow users to see everything that has changed between two selected deployments in Humanitec. Seeing these differences is useful when trying to debug errors for example. To make the Deployment Diff even more powerful, we plan to enrich and restructure the information it contains and improve its visualisation.

### Improved Deployment Clone Diff

In Humanitec users make use of deployment clones to create new environments or to move a deployment from one environment to another. This is either done in form of a full clone, comprising the entire application, or a partial clone by only selecting a subset of workloads to be promoted. With the implementation of a deployment clone diff, differences between source and target environment are visualised, allowing users to define the state of their environments in a more transparent and flexible way.

## Later

### Fleet Management

Larger deployments of Humanitec use organizations as tenants to manage independent teams. For example, different Product groups within a company might each have their own individual Humanitec Organization. This becomes difficult for Platform Teams to manage as they need to stay on top of multiple Humanitec Organizations. Fleet Management is a series of tools for Platform Teams to manage multiple Humanitec Organizations centrally. This allows them to do things keep base configurations consistent or roll out updates to infrastructure in a controlled and managed way.

### Canary Deployment Strategy

The Canary deployment strategy is a popular way of performing zero-downtime deployments. It involved deploying new services and routing a very small slice of traffic to test it. Live traffic is slowly transitioning across to the new services while monitoring them. At the same time, the old services are scaled-down and the new services are scaled up. This continues until all the traffic is running on the new services. This strategy can be considered more sophisticated than “rolling update” and “blue/green” strategies. It also requires the application to be architected such that it is possible to reliably split traffic between 2 versions of the same service without causing errors to end-users.

### Debug Flow Tools

As applications become more complex, it is harder to run the full application locally on the developer’s laptop. Moving development environments into the cloud solves that problem but makes it very hard to debug services under development. Humanitec is investigating a range of technical fixes to help developers bridge the gap between the local machine and the cloud.

### Team Performance Monitoring

Humanitec is sitting on a large amount of data and so has the potential to provide valuable insights about team performance. It would be relatively straightforward to measure time from “commit to production” for example.