# Humanitec Change Log

This document provides an overview over the changes we are making over time. Feel free to reach out to us in case of any specific questions.

## Product Update Janaury 8th, 2021

We enjoyed some time off between the years and we hope you did too. Stay tuned for the first product update 2021 which we will publish on January 22nd.

## Product Update December 25th, 2020

- **New:** Add configuration as a file that will be accessible from your container (UI&API).  
![Configuration as a File](_assets/images/2020-12-25_Configuration_as_a_file.png)
- **New:** Specify Service account that a pod should adopt via UI.  
![Specify Service Account](_assets/images/2020-12-25_Specify_Service_Account.png)
- **New:** Create Webhooks Deployment (started/finished) and Environment (created/deleted) events. (UI&API).  
![Create Webhooks](_assets/images/2020-12-25_Create_Webhooks.png)

- **Improved:** Show deployers for all deployments.
- **Improved:** Show who created a resource definition.
- **Improved:** User experience for re-deploying a historical deployment set.

- **Fixed:** It’s not possible to remove command overwrites and args.
- **Fixed:** The overview of deploy changes does not show removed env variables.
- **Fixed:** Container images dropdown for adding a workload is partially hidden.
- **Fixed:** Adding substitute variables for s3bucket.
- **Fixed:** Small UI issues on Firefox.
- **Fixed:** Blinking smiley behavior :-)

## Product Update December 11th, 2020

- **Improved:** Environments are ordered by creation date instead of alphabet.
- **Improved:** Users can choose to delete an environment type and see associated environments.
- **Improved:** A lot of great styling updates!

- **Fixed:** After adding a managed workload (Redis) the workload dropdown selection is not cleared.

## Product Update November 27th, 2020

- **Fixed:** Selecting placeholder from prompt popup causes currently entered text to be ovewritten.
- **Fixed:** After creating a draft from a diff the module detail page is not updated.
- **Fixed:** Envtype list is cut off on static resources page.
- **Fixed:** After deploying the user can directly see the currently running version instead of the draft.
- **Fixed:** Variables are not displayed in the diff if it is removed.
- **Fixed:** S3 bucket should only be available for adding to module when a S3 resource definition exists.
- **Fixed:** user reported issues with user pagination and user invite via Github.

- **Improved:** Based on user feedback, changed *Modules* to *Workloads* across application.

## Product Update November 13th, 2020

- **New:** A "My Apps" screen with all applications that a user has an access to as well as their respective environments. The user can choose to open the required application or an environment directly from the My Apps screen.  
![My App Screen](_assets/images/2020-11-13_My_App_Screen.png)
- **New:** Redirect to "My Apps" after deleting an application.
- **New:** Introduced an error screen for javascript errors and 404s with a redirect to "My Apps".

- **Fixed:** Automated deployments do not show up in UI until they are finished.

- **Improved:** Scroll bars across application.

## Product Update October 30th, 2020

- **New:** Deleting Resource Definitions via the UI. If the resource definition has any active resources associated with it, the user is informed about those resources and their suggested replacements. If the user proceeds with the deletion, the resource definition will be marked with pending deletion until all active resources are redeployed.  
![Delete Resource Defintion](_assets/images/2020-10-30_Delete_Resource_Definition.png)

- **Improved**: Input component for shared value overrides.
- **Improved**: Snippet for Bitbucket integration.

- **Fixed**: Error handling in a case of a blank screen.
- **Fixed**: Allowing users to select “None” for static resources that do not need a driver.
- **Fixed**: Real-time updates for automated deployments.

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
