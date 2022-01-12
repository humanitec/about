# Humanitec Roadmap

This document provides a high-level view on our product roadmap for this and upcoming quarters. It also lists roadmap items of past quarters.

## Q1 2022

### Dependant Resources

Some resources require inputs form other resources to be provisioned. For example, an "RDS Instance for MySQL" is needed in order to provision a `mysql` database or an "Azure Service Bus Namespace" might be needed in order to provision an `azure-service-bus-topic`. For more sophisticated setups, it might be necessary to provision underlying infrastructure which other resources will then depend on. It might also be necessary to inject common inputs into multiple resources (e.g. individual subscriptions for multiple workloads must all subscribe to the same topic). The feature will allow resource definitions to depend on resources defined by other resource definitions.

### App Details Page UI Update

Following several months of user testing and customer feedback we are planning on introducing a number of changes to improve the usability, predictability and scalability of our UI. The focus lies on the App Details Page, the control centre of an App. We want to address issues related to interaction design, information hierarchy, status communication as well as aesthetics while touching on UI patterns which are likely to change the look and feel of the Humanitec UI as a whole.

### Increase Resource Driver Range And Flexibility

Resource Drivers are used to provision things that are consumed by workloads. Most commonly this is infrastructure such as databases or dns. There are a growing number of drivers available out-of-the-box in Humanitec. In this quarter we aim to improve the flexibility and range of our driver offering. This includes adding generic drivers that work with templates and IaC as well as open-sourcing many of our drivers. We also plan to extend how drivers can be defined - allowing drivers to be defined in terms of other drivers. This should make it easier for ops teams to define good defaults to reuse within their teams. A comprehensive overview of the Humanitec driver ecosystem as well as its integration and contribution options will be published in a central hub on our website.

## Q2 2022 and beyond

The following features are in our backlog and planned for implementation from Q2 2022 onwards. They are subject to change based on additional feedback we will gather until then.

### Canary Deployment Strategy

The Canary deployment strategy is a popular way of performing zero-downtime deployments. It involved deploying new services and routing a very small slice of traffic to test it. Live traffic is slowly transitioning across to the new services while monitoring them. At the same time, the old services are scaled-down and the new services are scaled up. This continues until all the traffic is running on the new services. This strategy can be considered more sophisticated than “rolling update” and “blue/green” strategies. It also requires the application to be architected such that it is possible to reliably split traffic between 2 versions of the same service without causing errors to end-users.

### Debug Flow Tools

As applications become more complex, it is harder to run the full application locally on the developer’s laptop. Moving development environments into the cloud solves that problem but makes it very hard to debug services under development. Humanitec is investigating a range of technical fixes to help developers bridge the gap between the local machine and the cloud.

### Shared Services

Larger IT deployments in organizations often include services that are shared by multiple applications. (E.g., a product inventory service might be used by Point of Sale, logistics, forecasting, and financial reporting applications.)

For highly used services, a common pattern is to deploy the production version twice: once in the Production Environment and again in the Development environment. This allows developers to depend on the real service for testing while also not worrying about having to manage it as part of their workflow. This could be managed by Humanitec by marking an environment as being “exported” to all other development environments in all applications.

### On-Premise Offering

Many companies in regulated industries are wary of the public cloud and so wish to run all services used by their in house engineers themselves. Companies in this situation wishing to use Humanitec would, therefore, require an on-premise version of Humanitec. Being able to deploy and use Humanitec in this configuration is not particularly complex, however, the support process around it and the pace of receiving updates is the biggest challenge.

### Team Performance Monitoring

Humanitec is sitting on a large amount of data and so has the potential to provide valuable insights about team performance. It would be relatively straightforward to measure time from “commit to production” for example.

## Past Quarters

### Q4 2021

#### Deployment Pipelines

It is often the case that additional actions need to be performed before or after deployments. For example, tests can be run to verify the environment and if they pass the deployment can be automatically promoted to the next environment. A deployment pipeline defines a set of steps that specify how a service is deployed, verified or rolled back. This feature aims to allow actions to be run based on the outcome of a deployment or to orchestrate additional actions.

#### Dependant Resources

Some resources require inputs form other resources to be provisioned. For example, an "RDS Instance for MySQL" is needed in order to provision a `mysql` database or an "Azure Service Bus Namespace" might be needed in order to provision an `azure-service-bus-topic`. For more sophisticated setups, it might be necessary to provision underlying infrastructure which other resources will then depend on. It might also be necessary to inject common inputs into multiple resources (e.g. individual subscriptions for multiple workloads must all subscribe to the same topic). The feature will allow resource definitions to depend on resources defined by other resource definitions.

#### UI update: fresh looks and a more intuitive interface

Following several months of user testing and customer feedback we are planning on introducing a number of changes to improve the usability, predictability and scalability of our UI. The focus lies on the App Details Page, the control centre of an App. We want to address issues related to interaction design, information hierarchy, status communication as well as aesthetics while touching on UI patterns which are likely to change the look and feel of the Humanitec UI as a whole.

### Q3 2021

#### Deployment Pipelines

It is often the case that additional actions need to be performed before or after deployments. For example, tests can be run to verify the environment and if they pass the deployment can be automatically promoted to the next environment. A deployment pipeline defines a set of steps that specify how a service is deployed, verified or rolled back. This feature aims to allow actions to be run based on the outcome of a deployment or to orchestrate additional actions.

#### Custom Workload Profiles

Most teams adopting Humanitec already have workloads that they run in Kubernetes. The manifests being generated and applied to the cluster for these workloads can very often be directly transferred into Humanitec using the `humanitec/default-module` profile. More advanced setups often have some workloads that cannot be translated into an existing profile, for example services that have to be run as stateful sets. In some cases, ops teams might want to set their own defaults for some properties (e.g. minimum CPU) or include annotations or labels as part of the base profile that is deployed. This feature allows ops users to define their own Workload Profiles, specify which features a profile supports and which it does not, upload Helm Charts that form the basis of a workload profile and define a schema that can be used to define custom configuration for a workload profile.

#### Cherry-Pick Workloads

One of the major benefits of a microservice architecture is the ability to update individual parts of the application on their own schedule. As long as the contract between the services does not change, in theory, a single service can be promoted to another environment without impact. Humanitec currently only allows the promotion of all workloads in an application to another environment via "cloning". This feature will allow individual workloads to be cherry-picked into another environment while preserving the history of where the cherry-picked workloads came from.

#### Resources 2.0

Resource definitions and resource drivers provide a lot of the power and flexibility that Humanitec provides to ops and developer teams. After working with our resources concept with multiple different setups across different companies we have identified many areas of improvement. We aim to simplify both our UI and API while at the same time making the resources concept more powerful. This will expand what can be done with resources to include things like running message queues in cluster in some environments and as managed services in another or managing things like APMs or API Gateways in the cluster.

### Q2 2021

#### Blue/Green Deployment Strategy

The Blue/Green deployment strategy is a popular way of performing zero downtime deployments while retaining guarantees about the integrity of the whole environment. It works by deploying to a secondary (Green) environment and once this environment has been validated, cut the traffic from the current (Blue) environment to the new Green environment. The process is repeated, this time from Green to Blue at the next deployment. Compared with the zero-downtime “rolling update” strategy that Humanitec defaults to, a Blue/Green deployment strategy provides more control to operations and development teams deploying applications.

#### Cherry-Pick Workloads

One of the major benefits of a microservice architecture is the ability to update individual parts of the application on their own schedule. As long as the contract between the services does not change, in theory, a single service can be promoted to another environment without impact. Humanitec currently only allows the promotion of all workloads in an application to another environment via "cloning". This feature will allow individual workloads to be cherry-picked into another environment while preserving the history of where the cherry-picked workloads came from.

#### Path-Based Routing

Applications that are made up of multiple services usually serve different parts of the API surface from different services running in the same cluster. Routing can be handled via an ingress controller, an API gateway, or some other kind of proxy. These can be configured in a range of ways from Kubernetes Ingress objects to CRDs or annotations. This feature aims to create a system that allows developers to define routing information for their workloads while allowing Ops to define how DNS names are allocated and what technology is used to define the routing rules.

#### Resources 2.0

Resource definitions and resource drivers provide a lot of the power and flexibility that Humanitec provides to ops and developer teams. After working with our resources concept with multiple different setups across different companies we have identified many areas of improvement. We aim to simplify both our UI and API while at the same time making the resources concept more powerful. This will expand what can be done with resources to include things like running message queues in cluster in some environments and as managed services in another or managing things like APMs or API Gateways in the cluster.

### Q1 2021

#### Volumes

Volumes pose a particular area of complexity for Kubernetes applications. This feature aims to simplify handling of volumes by treating volumes as External Resources inside Humanitec. This means developers can simply declare a dependency on a volume and where it should be mounted and Humanitec will figure out how to provision or connect the volume.

#### Custom Base Helm Charts for Workloads

An important way that Humanitec reduces the complexity of dealing with Kubernetes is by providing sensible and widely applicable defaults. This is especially true for generating Kubernetes manifests for deployment. This advanced feature aims to give organizations more control over the manifests that are generated by Humanitec. DevOps engineers will be able to introduce Helm Charts that conform to a particular interface instead of using the defaults provided by Humanitec.

#### 3rd Party Container Registries

Humanitec currently only supports container registries that use standard, static credentials. Many container registries offered by cloud providers have more sophisticated credential requirements. For example, the Elastic Container Registry (ECR) from AWS requires time-limited credentials to be periodically generated. The Google Container Registry (GCR) from GCP provides custom tooling to configure access to the registry.
We will take the opportunity to support a configuration where the customer can supply their registry credentials in-cluster. This would allow Humanitec to perform deployments without having access to the registry credentials ahead of time.

### Q4 2020

#### Role-Based Access Control

Humanitec currently has a very simple permission model: any member of an organization can perform all actions in that organization. Many larger companies and companies in regulated markets have more complex needs and so require a finer-grained permission structure. Examples include limiting who can deploy to different environments, who can create new applications, or who can configure external resources. These fine-grained permissions should use a Role-Based Access Control (RBAC) model. To allow easy integration with corporate systems, Humanitec should be able to function as a SAML Service Provider.

#### Better Debugging for Failed Deployments

Debugging failed deployments in Kubernetes is particularly complex because of the number of moving parts involved. Some errors are straightforward and come to light immediately (e.g. container cannot be pulled from the registry) while others (e.g. a container entering a crash-loop) can come to light many minutes after a deployment has been kicked off. This feature set aims to outline the sequence of steps performed by Humanitec when initiating a deployment. It informs the user once the step is performed successfully, or alternatively provides details for easier debugging if an error occurs.

### Q3 2020

#### Seamless Onboarding Experience

Users wishing to try Humanitec should have a seamless onboarding experience. Providing full in-app support and guided tutorials will significantly shorten new users’ time-to-value and help them to get started faster. Additionally, one of the key activation points is connecting Humanitec to your own infrastructure, therefore it is essential to provide users a way to easily use packaged CI steps for major CI tools such as GitLab, GitHub, CircleCI, TravisCI, DroneCI, and Jenkins.

#### Event-Driven Jobs

It is often useful to be able to perform actions on events such as “new environment created”, “deployment completed”, or “environment deleted”. The actions could be as simple as posting a Slack message or as complex as running a suite of integration tests or initializing data. This feature covers running basic webhooks to enable things like Slack integration and running Kubernetes Jobs that can support things like running automated tests in an environment.

#### Runtime Monitoring

When running applications in production, monitoring is essential. With this feature, Humanitec will provide CPU, memory, and disk space statistics and will inform developers when these limits are reached. This allows for easier debugging and enables developers to make educated decisions while configuring their containers and replicas on Humanitec. Furthermore, Humanitec should provide the required integrations to most commonly used monitoring tools (e.g., Prometheus, Grafana, DataDog) to fully support development teams’ existing infrastructures.

#### Humanitec CLI

Many developers are not comfortable working with a GUI. At the same time, an API is hard to use for day-to-day deployments and application management. The Humanitec CLI will provide a middle ground between the API and the GUI. This feature is essential to pursue the API-first approach and provide full support to users that spend most of their time interacting with tools via their terminal. Using Humanitec CLI developers will be able to authenticate, create, and configure apps, deploy and manage environments, and much more. The CLI will also provide special functionality such as port forwarding into running applications or direct connection to managed databases.

### Q2 2020

#### Provisioning External Resources

Many applications rely on databases and services that run external to the cluster. Humanitec already supports the automatic generation of Postgres databases via Google CloudSQL. This feature would extend the range of services supported. A stretch objective here is also to provide a way for developers to build their own implementation if the set of services supported by Humanitec does not cover what they need.

#### Environment Management

Humanitec allows developers to easily spin up and tear down environments on demand. Additionally, developers need to manage their workflows across multiple environments. This feature aims to take out the manual work associated with environment management and ease team workflow. It allows developers to compare deployments in different environments, patch the difference to another environment, manage variables per environment, as well as filter and label them for automation.

#### Published API

Much of what Humanitec can do will help with various forms of automation. For example, a test automation system may want to use Humanitec to spin up a new, clean environment to run tests in and then tear it down once it is done. Humanitec has the potential to add a whole set of use cases by defining and publishing a well-designed API.

#### Runtime Status

Successful deployment does not mean successful running. Developers need to know the runtime status of what they have deployed. This feature aims to show developers an all-in-one overview of live pods statuses and provide basic monitoring of all services deployed with Humanitec.

#### Automatic Deployments

Most of the engineering teams are either running automated deployments or aspire to in the future. Humanitec has all of the functionality required to automate deployments but lacks the ability to perform a deployment based on a trigger. This feature would allow developers to define deployment rules that could be run based on triggers. Rules would be of the form, if a new container image is built on branch _x_, deploy to environment _y_ and would be triggered on an event like: a new container image has been built by a CI pipeline.

### Q1 2020

#### Dynamic Environment Variable Management

Environment management across environments is complex and error-prone. With this feature, environment variables are classified as one of 3 types:

* **Static:** The same for each environment deployed in
* **Dynamic:** Humanitec can infer the different values that a variable should have in each environment via a system of “placeholders” and string formatting
* **Environment Specific:** Developers must either accept or update the value of the variable when being deployed to a different environment

For example, a dynamic environmental variable definition which resolves to the external DNS name of a module called “api-server” would be:

        API_SERVER_NAME = "${modules.api-server.service.externalName}"

#### Deployment Sets

*Deployment Version History*

The full state of each deployment to an environment is recorded as a “deployment set”. Deployment sets can be compared to show differences between them. A previous deployment set can be redeployed to perform a rollback. Cloning one environment to another is done by applying a deployment set from one environment into another. As part of this, the Dynamic Environment Variable Management feature ensures that environmental variables are correctly handled.

*Serialization of Deployment Sets* [to be completed in Q2]

The deployment set is the unit of state that is used to serialize out Helm Charts that describe a particular deployment. In the future, these charts can be directed towards a git repository and so form part of a “GitOps” process.

#### Generalized Module Sources

The current version of Humanitec has a tight dependency on GitHub. This feature relaxes that dependency.

*Connect your CI*

Rather than building containers directly from source code, Humanitec will hook into the end of your CI pipeline. This allows any successfully built and tested container to be used directly in Humanitec.

#### External Modules (3rd Party In-Cluster Components / Services)

Many modern cloud-native applications make use of services and components based on popular open-source projects, for example, Redis or RabbitMQ. With this feature, we aim to build a growing set of curated, ready to deploy packages of these popular components and services. These packages can then be simply deployed into the cluster by developers.
