# Humanitec Roadmap

This document provides a high-level view on our product roadmap for this and upcoming quarters.

It is divided up into things we are currently working on *Now*, what we'll be looking at *Next* and things we will be looking into at a *Later* point in time.

## What we're working on Now

### Agent Based Approach for Deploying to Private Clusters

A common approach used by SaaS products to access private resources is an agent. The agent runs inside the private infrastructure and calls out to Humanitec. This means that nothing in the private infrastructure is exposed to the public internet. This is considered best practice from a security perspective as nothing is exposed publicly and the operations team have complete control over what the agent has access to. It is also easier to administer than other approaches supported by Humanitec including bastion hosts and VPNs. The Humanitec Agent will give operations teams a flexible, easy to configure and secure way of using Humanitec with private infrastructure.

### Deployment Pipelines

It is often the case that additional actions need to be performed before or after deployments. For example, tests can be run to verify the environment and if they pass the deployment can be automatically promoted to the next environment. A deployment pipeline defines a set of steps that specify how a service is deployed, verified or rolled back. This feature aims to allow actions to be run based on the outcome of a deployment or to orchestrate additional actions.

### Resource Classes

Platform teams often offer multiple variations of the same type of resource, such as externally accessible S3, versioned S3, and sensitive data S3. Developers want to be able to specialise resource types in a systematic way, defining whether they want the "external" or "sensitive" version of the S3 resource. Resource classes enable the specialization of resource types by adding an optional "class" property that can be matched using specific criteria.

### Improved System Health Status Messaging

At some point, both developers and platform engineers will need to troubleshoot a failing system. Status messaging in the Humanitec UI is being reworked to increase visibility and support users when troubleshooting. This includes the health of an environment, deployment statuses as well as workload runtime statuses. Errors should be visible to the user at first sight and detailed error messaging should be found by digging deeper.

## What we're working on Next

### Real-time Deployment Logs

This feature aims to enhance transparency and simplify troubleshooting by introducing live logs for deployments in progress. By exposing individual deployment steps, users can track the real-time provisioning of workloads and resources. This functionality offers a clear view of tasks currently in progress, those successfully completed, or those that have encountered issues. Ultimately, it enhances the deployment experience by providing users with detailed insights into the deployment process.

### Scalable Access Management

As the user base of an organization in Humanitec continues to grow, the task of overseeing and controlling user access becomes increasingly challenging. Staying on top of user changes and guaranteeing their alignment with internal user management systems puts additional cognitive load on platform teams and is prone to errors. Our objective in enhancing access management within Humanitec is to reduce the need for manual interventions.

### Versioned Resource Definitions

Resource definitions are changed over time as part of routine maintenance or development of an Internal Developer Platform, involving modifications such as updating resource definitions for example. The storage of versions for updated or deleted resource definitions enables a series of use cases. This includes the ability to track the version of a resource definition in use for a specific deployment or the option to regenerate a previous resource graph in case of a required roll back, offering more granular control when it comes to managing resources with Humanitec.

## What we'll be looking at Later

### Fleet Management

Larger deployments of Humanitec use organizations as tenants to manage independent teams. For example, different Product groups within a company might each have their own individual Humanitec Organization. This becomes difficult for Platform Teams to manage as they need to stay on top of multiple Humanitec Organizations. Fleet Management is a series of tools for Platform Teams to manage multiple Humanitec Organizations centrally. This allows them to do things keep base configurations consistent or roll out updates to infrastructure in a controlled and managed way.

### Canary Deployment Strategy

The Canary deployment strategy is a popular way of performing zero-downtime deployments. It involved deploying new services and routing a very small slice of traffic to test it. Live traffic is slowly transitioning across to the new services while monitoring them. At the same time, the old services are scaled-down and the new services are scaled up. This continues until all the traffic is running on the new services. This strategy can be considered more sophisticated than “rolling update” and “blue/green” strategies. It also requires the application to be architected such that it is possible to reliably split traffic between 2 versions of the same service without causing errors to end-users.

### Debug Flow Tools

As applications become more complex, it is harder to run the full application locally on the developer’s laptop. Moving development environments into the cloud solves that problem but makes it very hard to debug services under development. Humanitec is investigating a range of technical fixes to help developers bridge the gap between the local machine and the cloud.

### Team Performance Monitoring

Humanitec is sitting on a large amount of data and so has the potential to provide valuable insights about team performance. It would be relatively straightforward to measure time from “commit to production” for example.
