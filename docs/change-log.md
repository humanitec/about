# Humanitec Change Log

This document provides an overview over the changes we are making over time. Feel free to reach out to us in case of any specific questions.

## Product Update October 16th, 2020

- **New**: UI and API for adding your AKS and EKS clusters.  
![UI and API to add AKS and EKS clusters](_assets/images/2020-10-16_AKS_and_EKS_clusters.png)
- **New**: UI and API for adding S3 Bucket resource definition and defining dependency within your modules.
- **New**: Welcome emails to newly registered users.

- **Improved**: Container runtime status added to application view - users can see at a glance if any of their modules are failing.  
![Container runtime status](_assets/images/2020-10-16_Container_Runtime_Status.png)
- **Improved**: Expandable deployment history view. Users can filter based on deployment comment and find their historical deployments easier.  
![Expandable deployment history](_assets/images/2020-10-16_Expandable_Deployment_History.png)
- **Improved**: CI integration guide - now presented as a wizzard.  
![CI wizzard](_assets/images/2020-10-16_CI_Wizzard.png)

## Product Update October 2nd, 2020

- **New**: Export manifests for your chosen deployment set. Manifests can be downloaded as .yaml files and stored in a repository.  
![UI to export manifests](_assets/images/2020-10-02_UI_Export_Manifests.png)
- **New**: UI support for connecting your own GKE or EKS cluster via Static Resources.  
![UI for GKE or EKS clusters](_assets/images/2020-10-02_UI_GKE_EKS_Clusters.png)

- **Improved**: Possibility to add and confirm contact email through profile settings if it is not retrieved during registration.

## Product Update September 18th, 2020

- **New**: UI for adding AWS accounts for dynamic ressources  
![UI for AWS accounts](_assets/images/2020-09-18_UI_AWS_Accounts.png)
- **Improved**: UI for managing API Tokens
  - See all API Tokens for an organization in one list
  - Create new API Tokens
  - View and revoke existing API Tokens  
![UI for API Tokens](_assets/images/2020-09-18_UI_API_Tokens.png)

## Product Update September 4th, 2020

- **New**: UI for Runtime status
  - View the runtime status for deployed applications and easily debug errors when they occur
  - Users are informed if any of the replicas are failing and the affected deployment and modules are marked with a warning
  - To simplify debugging, container errors are reported for each replica separately and presented to the user together with the container log  
![UI for Runtime status](_assets/images/2020-09-04_UI_Runtime_Status.png)
- **New**: API for deleting resources
- **Improved**: Live container logs
  - Users do not have to refresh to see the latest logs
  - Fixed UI issues and logs formatting
- **Fixed**: Wrong DNS being shown for modules (user reported bug)

## Product Update August 21st, 2020

- **Improved**: Container logs
  - Users can now see logs for each historical deployment
  - Fixed inconstiencies reported by users  
![Container Logs v2](_assets/images/2020-08-21_Container_Logs_v2.png)
- **New**: [Humanitec CircleCI Orb](https://circleci.com/orbs/registry/orb/humanitec/humanitec) for simple integration between CircleCI and Humanitec  
![CircleCI Integration](_assets/images/2020-08-21_CircleCI_Integration.png)

## Product Update August 7th, 2020

UI improvements:

- Separation between *Profile Settings* and *Organization Settings*  
![Separation of Settings](_assets/images/2020-08-04_Separation_of_Settings.png)

Documentation update:

- Release of the API documentation (currently in beta) available [here](https://api-docs.humanitec.com) incl. a first tutorial how to use the Humanitec API  
![Humanitec API Docs](_assets/images/2020-08-04_API_Docs.png)

## Product Update July 24th, 2020

General new features:

- First version of automatic deployments based on user-defined rules  
![Rules for Automatic Deployments](_assets/images/2020-07-24_Automatic_Deyploments_Rules.png)  
![Status Notification for Automatic Deployment](_assets/images/2020-07-24_Automatic_Deployments_Notification.png)

## Product Update July 10th, 2020

General new features:

- Allow users to connect dynamic resources of type Postgres with Google Cloud Platform resource account  
![Connect GCP Postgres](_assets/images/2020-07-10_Connect_GCP_Postgres.png)

UI improvements:

- Better overview over available image versoins  
![List of available images](_assets/images/2020-07-10_Available_Images.png)
- Improved database selector  
![Database Selector](_assets/images/2020-07-10_Database_Selector.png)

New API endpoints:

- API endpoint for deployment automation - allowing users to create, update and delete rules for automated deployments; Humanitec deploy new images automatically based on the defined rules

## Product Update June 26th, 2020

General new features:

- Option to create multiple deployment drafts in an environment  
![Multiple Deployment Drafts](_assets/images/2020-06-26_Multiple_Deployment_Drafts.png)

Onboarding support:

- First version of in-app guide explaining how to deploy your first application with Humanitec  
![In-App Guide](_assets/images/2020-06-26_In-App_Guide.png)

## Product Update June 12th, 2020

General new features:

- Option to create a diff between two deployment sets within one environment  
![Diff Deployments](_assets/images/2020-06-12_Diff_Deployments.png)
- Allow for patching of environments: apply a diff to a deployment set in any environment  
![Patch Environments](_assets/images/2020-06-12_Patch_Environments.png)

Onboarding support:

- Added sample images that allow for a quicker onboarding (e.g., option to deploy first application without connecting own CI pipelines)  
![Sample Images](_assets/images/2020-06-12_Sample_Images.png)

## Product Update May 29th, 2020

General new features:

- Option to clone deployments to another environment  
![Clone Deployment](_assets/images/2020-05-29_Clone_Deployment.png)
- Added Elasticsearch and MariaDB as managed images  
![Managed Images](_assets/images/2020-05-29_Managed_Images.png)
- Allow to switch between drafts and deployments directly from the module configuration view  
![Switch Draft](_assets/images/2020-05-29_Switch_Draft.png)

New features only available via the API:

- Deploy to your own GCP account (API documentation will be pusblished soon on our [docs site](https://docs.humanitec.com))
