# Humanitec Roadmap

This document provides a high-level view on our product roadmap for this and upcoming quarters.

It is divided up into things we are currently working on *Now*, what we'll be looking at *Next* and things we will be looking into at a *Later* point in time.

## What we're working on Now

### Humanitec Operator

Humanitec works in an interactive way with infrastructure. This means that Humanitec handles the whole deployment process by making calls to the affected systems (Kubernetes clusters, databases etc.) either directly or via drivers such as the [Terraform driver](https://docs.humanitec.com/integrations/resource-drivers/terraform). This approach can cause inconsistencies with deferred deployment strategies such as when using a GitOps operator like ArgoCD. The Humanitec Operator aims to move functionality currently managed server side by Humanitec into the cluster. This would allow things like resource provisioning to occur as part of a GitOps flow. As the operator also runs in-cluster it would also simplify the use of custom drivers since these would not need to be publicly exposed.

### Agent Based Approach for Deploying to Private Clusters

A common approach used by SaaS products to access private resources is an agent. The agent runs inside the private infrastructure and calls out to Humanitec. This means that nothing in the private infrastructure is exposed to the public internet. This is considered best practice from a security perspective as nothing is exposed publicly and the operations team have complete control over what the agent has access to. It is also easier to administer than other approaches supported by Humanitec including bastion hosts and VPNs. The Humanitec Agent will give operations teams a flexible, easy to configure and secure way of using Humanitec with private infrastructure.

### Deployment Pipelines

It is often the case that additional actions need to be performed before or after deployments. For example, tests can be run to verify the environment and if they pass the deployment can be automatically promoted to the next environment. A deployment pipeline defines a set of steps that specify how a service is deployed, verified or rolled back. This feature aims to allow actions to be run based on the outcome of a deployment or to orchestrate additional actions.

### Custom Workload Profile Features

[Workload Profiles](https://docs.humanitec.com/reference/workload-profiles) are a way to define the baseline configuration of a workload. Humanitec provides a number of default workload profiles and users have been able to add their own. Up to this point, platform teams have been limited to the UI provided by Humanitec. Custom Workload Profile features will allow platform teams to define schemas for their features and annotate these schemas to generate custom UI elements. This will allow platform teams to fully customize the developer experience for their Custom Workload Profiles.

### Global Navigation

Following several months of user testing and customer feedback, we are planning on introducing several changes to improve the usability, predictability and scalability of our UI. The focus lies on creating a better experience for navigating the Humanitec application. We want to address issues related to information hierarchy and aesthetics by touching on UI patterns that will likely change the look and feel of the UI.

### Enhanced Error Reporting

Effective error messaging is crucial for identifying and resolving issues. Our goal is to increase the coverage and improve the informational value of errors in Humanitec. As part of this initiative, we aim to ensure that API errors are consistently reported on the Frontend and provide transparent explanations about the root cause of a problem.

### General Availability of the Terraform Driver

The [Humanitec Terraform driver](https://docs.humanitec.com/integrations/resource-drivers/terraform) allows for the provisioning of resources via Terraform. The current driver is experimental. This means that it is only made available to customers that we work especially closely with. The feedback we have received from these customers allows us to bring the Terraform Driver to General Availability. This means the driver works in a wide range of scenarios, reports errors well and is well documented.

## What we're working on Next

### Resource Classes

Platform teams often offer multiple variations of the same type of resource, such as externally accessible S3, versioned S3, and sensitive data S3. Developers want to be able to specialise resource types in a systematic way, defining whether they want the "external" or "sensitive" version of the S3 resource. Resource classes enable the specialization of resource types by adding an optional "class" property that can be matched using specific criteria.

### Custom Resource Types

This feature allows users to define custom resource types within their Organization. Platform teams might want to create new resource types that are not natively supported by Humanitec or extending any existing resource types e.g. when non-standard authorization is required. With this feature, users can experiment with different resource types when modeling their resource setup in Humanitec.

### Improved System Health Status Messaging

At some point, both developers and platform engineers will need to troubleshoot a failing system. Status messaging in the Humanitec UI is being reworked to increase visibility and support users when troubleshooting. This includes the health of an environment, deployment statuses as well as workload runtime statuses. Errors should be visible to the user at first sight and detailed error messaging should be found by digging deeper.

### Humanitec CLI Beta-level Release

The Humanitec Command Line Interface (CLI) allows users to get your everyday DevOps tasks (e.g., create a new temporary environment to test new features, add new services to an application) done without ever leaving their favourite console. After conducting a final round of testing and development in closed beta, are we planning to release the CLI in open beta for public use.

### Deployment Set v1.0

A Deployment Set in Humanitec contains all of the environment-agnostic configurations for an Application. It describes the material things that should run or be provisioned in an environment. With the introduction of a new deployment set version (v1.0), we’re planning to replace legacy terminology with a naming convention better aligned with industry and Kubernetes standards and unify it across Humanitec’s UI, API and CLI. New vocabulary will be more familiar and intuitive for the platform teams and developers, improving the experience of using the Humanitec application, especially for new users.

## What we'll be looking at Later

### Fleet Management

Larger deployments of Humanitec use organizations as tenants to manage independent teams. For example, different Product groups within a company might each have their own individual Humanitec Organization. This becomes difficult for Platform Teams to manage as they need to stay on top of multiple Humanitec Organizations. Fleet Management is a series of tools for Platform Teams to manage multiple Humanitec Organizations centrally. This allows them to do things keep base configurations consistent or roll out updates to infrastructure in a controlled and managed way.

### Canary Deployment Strategy

The Canary deployment strategy is a popular way of performing zero-downtime deployments. It involved deploying new services and routing a very small slice of traffic to test it. Live traffic is slowly transitioning across to the new services while monitoring them. At the same time, the old services are scaled-down and the new services are scaled up. This continues until all the traffic is running on the new services. This strategy can be considered more sophisticated than “rolling update” and “blue/green” strategies. It also requires the application to be architected such that it is possible to reliably split traffic between 2 versions of the same service without causing errors to end-users.

### Debug Flow Tools

As applications become more complex, it is harder to run the full application locally on the developer’s laptop. Moving development environments into the cloud solves that problem but makes it very hard to debug services under development. Humanitec is investigating a range of technical fixes to help developers bridge the gap between the local machine and the cloud.

### Team Performance Monitoring

Humanitec is sitting on a large amount of data and so has the potential to provide valuable insights about team performance. It would be relatively straightforward to measure time from “commit to production” for example.
