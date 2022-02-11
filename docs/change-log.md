# Humanitec Change Log

This document provides an overview over the changes we are making over time. Feel free to reach out to us in case of any specific questions.

## Product Update February 11th, 2022

- **Fixed:** The authentication flow for active users accepting invites to a new Organization.

- **Fixed:** A temporary authentication issue related to new users accepting invites.

- **Fixed:** An interaction bug related to discarding deployment clones in the UI.

- **Fixed:** Error messages on the "Create new environment" overlay and the "Account details" form are no longer hidden in the UI.

- **Improved:** Nested values are now supported by the resource `Details` overlay on the App Details- and Workload Details Page of running deployments.

- **Improved:** The error message handling for users attempting to log in without a registered GitHub or Google account.

- **Improved:** Existing `Volume Mounts` are now validated in the UI when being updated.

## Product Update January 21st, 2022

- **New:** Added support for [Service Ports](https://docs.humanitec.com/reference/workload-profiles/features/service) on the Workload Details Page.  
![service ports](_assets/images/2022-01-21_Service_Ports.png)

- **Fixed:** Corrected form validation on the "Accept Invite" page.

- **Fixed:** Switching Organization on the App Details or Workload Details Page no longer causes a "We can't find the app you are looking for" error (403).

- **Fixed:** Defining `Volume Mounts` for shared `Persistent Volume` resources no longer causes a deployment to fail.

- **Fixed:** Several UI issues, including:
  - The user-dropdown on the "Manage deployers for x environment type" overlay as well as the image-dropdown on the "Create new container" overlay are no longer cut off.
  - Removed redundant "More" link on dropdown menus.
  - A number of interaction bugs with discarding deployment clones in the UI.

- **Changed:** Initial input validation is triggered `on submit` instead of `on blur` in the majority of cases.

## Product Update January 7th, 2022

- **Improved:** Custom Workload Profiles based on [supported features](https://docs.humanitec.com/reference/workload-profiles/features) are dynamically displayed and editable in the UI.

- **New:** Added support for [Labels](https://docs.humanitec.com/reference/workload-profiles/features/labels) & [Annotations](https://docs.humanitec.com/reference/workload-profiles/features/annotations) on the Workload Details Page.  
![labels and annotations](_assets/images/2022-01-07_Labels_Annotations.png)

- **New:** Added support for [CronJobs](https://docs.humanitec.com/reference/workload-profiles/features/schedules) on the Workload Details Page.  
![cronjob schedule](_assets/images/2022-01-07_Cronjob_Schedule.png)

- **Fixed:** On the App Details Page, Workload error states are now being indicated on the Workload card.  
![workload card error state](_assets/images/2022-01-07_Workload_Card_Error.png)

- **Fixed:** The edit overlay of Kubernetes cluster resources with the `humanitec/k8s-cluster-eks` driver no longer displays incorrect form parameters.

- **Fixed:** An Environment Type can now be deleted in the UI if an environment with the same ID exists in the active Organization.

- **Fixed:** The "Deploy changes" confirmation overlay no longer reloads after being submitted via keyboard enter.

- **Fixed:** Validation of the "Resource ID" matching criterion on the Resource Management Page.

- **Fixed:** Several UI issues, including:
  - Corrected routing of "Back to" button on the Organization Settings Page.
  - Updated "Learn more" link for Workload level error messages.
  - Removed duplicate Ingress resource type from Resource Management Page.
  - Improved handling of special characters in the Deployment Diff.

## Product Update December 17th, 2021

- **Fixed:** When deleting a shared `Persistent Volume` resource, associated `Volume Mounts` are automatically removed from the Workload as well.

- **Fixed:** Environment variables no longer throw an error for empty values.

- **Fixed:** A Safari browser compatability issue.

## Product Update December 3rd, 2021

- **Fixed:** Creating a new webhook no longer throws an error.

- **Fixed:** It is no longer possible to switch the driver when editing an existing resource definition.

- **Fixed:** A number of smaller interaction bugs with setting resource requirements for CPU and Memory.

- **Fixed:** The help modal is fully accessible on the log in page again.

## Product Update November 17th, 2021

- **New:** Added Cloudflare to the Accounts section in the UI.  
![cloudflare account type](_assets/images/2021-11-17_Cloudflare_Account_Type.png)

- **Changed:** Workloads are added via an overlay which allows users to change the underlying Workload Profile if needed.  
![add workload flow](_assets/images/2021-11-17_Add_Workload_Flow.png)

- **Improved:** A containers maximum and minimum resource requirements for CPU and Memory can now be cleared in the UI. This enables full support for all QoS (Quality of Service) classes in Kubernetes: BestEffort, Burstable and Guaranteed.

- **Fixed:** An interaction bug related to selecting "all images except" on the environment automation component.

- **Fixed:** An interaction bug related to duplicating Workloads.

- **Fixed:** Several UX issues in relation to selecting and deleting draft deployments.

- **Fixed:** The scaling of replicas on the Workload Details Page of a running deployment is no longer limited to two. In addition to that can a Workload temporarily be disabled by scaling its replicas down to 0.

- **Fixed:** Validation for volume mount path now correctly requires a rooted path with at least 1 directory.

- **Improved:** Accessibility according to the Web Content Accessibility Guidelines (WCAG) 2.1:
  - Improved app content for screen readers.
  - Improved keyboard accessibility of submenus and toggles.

## Product Update October 29th, 2021

- **New:** Added support for updating Resource Account credentials.

- **New:** Added a "Status" column to the Organization Members list. After an invitation is sent, the user's status is pending. When the recipient accepts the invitation, their user status switches to active.

- **New:** The user role is now visible on the Profile Settings Page.

- **Fixed:** Reselecting the currently active Organization in the Organization Menu no longer makes a hard refresh of the App Overview Page necessary.

- **Improved:** Users are notified if their currently active environment on the App Details Page has been deleted and are automatically directed to the next environment.

- **Improved:** Keyboard accessibility according to the Web Content Accessibility Guidelines (WCAG) 2.1:
  - (Un-)pinning of Workloads.
  - Editing of Files on the Workload Details Page.

## Product Update October 19th, 2021

- **Changed:** Resources are no longer managed as "Dynamic Resources" and "Static Resources" in the Organization Settings. The implementation of a new Resources Management screen instead allows to manage the provisioning and allocation of resources in one place.  
![resources management](_assets/images/2021-10-19_Resources_Management.png)

- **New:** Next to Environment Types, Resource Definitions can now be matched to Environment Names, Apps as well as Resource IDs in the UI.  
![resources matching](_assets/images/2021-10-19_Resources_Matching.png)

- **Changed:** Organization Settings and Resources Management were moved from the User Menu to the Organization Menu.  
![organization menu](_assets/images/2021-10-19_Organization_Menu.png)

- **Changed:** Accounts are now managed from a separate tab in the Organization Settings. Users can dynamically reference existing accounts when configuring resources from the Resources Management screen.  
![accounts](_assets/images/2021-10-19_Accounts.png)

- **New:** It is now possible to define headers for "HTTP link" Liveness and Readiness probes on the Workload Details Page.  
![http headers](_assets/images/2021-10-19_HTTP_Headers.png)

- **Improved:** If a shared DNS resource is deleted, associated Ingress paths are automatically removed from the according Workloads as well.

- **Improved:** Accessibility according to the Web Content Accessibility Guidelines (WCAG) 2.1:
  - Enhanced keyboard accessibility throughout the application.
  - Improved website content for screen readers.

- **Fixed:** The UI no longer forces updates of secrets when editing an existing Resource Definition.

- **Fixed:** Several interaction bugs when (de-)activating environment automation rules.

- **Fixed:** The "Manage versions" overlay for Images in the Organization Settings no longer throws an error for images without an image tag.

- **Fixed:** Several UI issues, including:
  - The user dropdown on the "Manage deployers" overlay no longer opens by default and blocks the view.
  - The "Active" toggle on the Webhooks component is no longer clickable by users in Developer role.
  - Error states are no longer shared between account configuration overlays.
  - Switching between drafts no longer causes issues on the UI.

## Product Update September 10th, 2021

- **Improved:** Numerous accessibility improvements for keyboard only users.

- **Improved:** Better icons for resources.

- **Fixed:** Corrected validation for namespace and container names.

- **Fixed:** Resources not duplicated when workload duplicated.

- **Fixed:** Placeholders for shared resources not expanded in Config Map.

- **Fixed:** Better handling of long app and environment names.

- **Fixed:** Organization names overflow organization-switcher dropdown.

- **Fixed:** Menus at the bottom of lists are truncated as they go off the screen.

- **Fixed:** Some resource and workload creation actions were not possible for users with some roles.

- **Fixed:** Number of small interaction bugs with managing roles for users.

- **Fixed:** Clone functionality in some cases is missing view of detailed changes.

- **Fixed:** Discard clone causes a page refresh.

## Product Update August 27th, 2021

- **New:** Added support for custom Workload Profiles in the UI. Next to the default profile `default-module` users now have the option to choose a different profile according to their use case. Container images are added in a second step on the Workload Details Page.  
![workload profiles](_assets/images/2021-08-27_Workload_Profiles.png)

- **New:** Resources can now be provisioned on App level. On the Application Details Page, users have the option to add shared resources that can be referenced within the Workloads of their App.  
![shared resources](_assets/images/2021-08-27_Shared_Resources.png)

- **New:** Added support for partial clones. Instead of cloning the entire deployment by default, users can now choose to include / not include certain Workloads in their clone.  
![partial clone](_assets/images/2021-08-27_Partial_Clones.png)

- **New:** Added a `...` settings icon to App cards with shortcuts to "View", "Settings" and "Delete".

- **New:** Users using ad-blockers are now warned that some features will not be available to them in the Humanitec UI. The reason for this is that Humanitec uses a system called Optimizely for UI feature flags. If a user has ad blocking services enabled that block calls to Optimizely, it has to be manually removed from the blacklist in the ad-blocking extension in order to access all Humanitec features.

- **Improved:** Container images are now sorted by date.

- **Improved:** Several UI components have been transformed into link elements that allows users to open them in a separate browser tab.

- **Changed:** The design of several UI components:
  - Increased color contrasts in the light theme.
  - Increased the font size of label elements.
  - Adjusted the design of tooltips.
  - Intensified the border color of Workloads in the "Has changes" state.

- **Changed:** The following wordings:
  - `External resources` has been renamed to `Resource dependencies` on the Workload Details Page.
  - The `Close` button has been replaced with a `Back to ...` button.

- **Fixed:** Draft deployments are now accessible during running deployments.

- **Fixed:** It is no longer possible to create Workloads in deleted Environments.

- **Fixed:** Ports defined for liveness and readiness probes in the container configuration section are now displayed on the Workload Details Page of running deployments.

- **Fixed:** The Deploy button was renamed to Re-Deploy for active deployments.

## Product Update August 13th, 2021

- **Fixed:** Draft deployments can now be accessed while a deployment is in progress.

- **Fixed:** The environment status no longer defaults to "Stopped" after a successful deployment.

- **Fixed:** Several UI issues, including:
  - Entering multiple Placeholder Paths into the Value field of the Variables component no longer breaks the UI.
  - Placeholder Paths in the Value field of the Variables component now support dash characters.
  - The "More Environments" dropdown on the App Details Page no longer overflows for large amount of environments.

- **Improved:** Keyboard accessibility according to the Web Content Accessibility Guidelines (WCAG) 2.1.

## Product Update July 16th, 2021

Nothing to report for todays product update as our team has been taking some well earned time off in the past 2 weeks. The next update will be published on August 13th.

## Product Update July 2nd, 2021

- **New:** Workload cards can now be pinned to the top of the App Details Page. This allows users to set focus on most relevant workloads in the UI.  
![pin workloads to top](_assets/images/2021-07-02_Workload_pinning.png)

- **New:** Dynamic resources can now be connected to Humanitec via Azure accounts.

- **Changed:** The deploy button has been moved into the draft- and deployment list items on the left hand side of the App Details Page.  
![Deploy button](_assets/images/2021-07-02_Deploy_button.png)

- **Improved:** Humanitec's accessibility according to the Web Content Accessibility Guidelines (WCAG) 2.1:
  - Improved keyboard accessibility with focus on links, table-, and list components.
  - Improved navigation flows throughout the application.

- **Fixed:** It is now possible to remove previously specified overrides for the container command in the container configuration of the Workload Details Page.

- **Fixed:** Environment status (Running/Stopped/Failed) and status icon are now in sync on the Environment Settings Page.

- **Fixed:** User names are being shown again on active and past deployments on the App Details Page.

## Product Update June 18th, 2021

- **New:** Added an image build versions overview for each container image registered with Humanitec. This allows to review image versions and filter by commit ID, branch, or tag.  
![image build version overview](_assets/images/2021-06-18_Image_versions_overview.png)

- **New:** Added information on resource details to the Workload Details Page of running deployments.  
![resources details](_assets/images/2021-06-18_Resource_details.png)

- **Fixed:** The environment runtime status is no longer mirrored on all environment tabs of an Application.

- **Fixed:** Deleting a volume resource no longer leaves invalid volume mounts in the Workload but instead removes these automatically.

- **Fixed:** Deleting a DNS resource now automatically removes all associated routing rules defined in the Ingress section of the Workload.

- Several UI fixes, including:
  - **Fixed:** The draft version dropdown on the App Details Page no longer overflows for large amount of draft versions.
  - **Improved:** Added an automatic copy interaction to Ingress routes shown on the Workload Details Page of running deployments.
  - **Improved:** Enhanced error message handling in several parts of the application.

## Product Update June 4th, 2021

- **Changed:** Significantly simplified how to connect CI pipelines (like Bitbucket Pipelines, GitHub Actions, and Circle CI) from the Images tab in Organization settings. The CI pipelines just need to notify Humanitec about new image builds. Check out the docs for [more information](https://docs.humanitec.com/how-to-guides-devops/infrastructure-orchestration/connect-ci-pipelines#add-new-image-sources).  
![connect ci pipelines](_assets/images/2021-06-04_Connect_CI_pipeline.png)

- **Fixed:** Changes made in a Draft are no longer replicated to running and past deployments in the UI.

- **Fixed:** When deleting an App, the Drafts associated with it will no longer show up in subsequently created Apps of the same name.

- **Fixed:** Ingress manifests are no longer missing from exported manifests of running and past deployments with allocated Ingress resources.

- Several UI fixes, including:
  - **Fixed:** When changing a Variable key in a Draft, the old value will now be displayed on the deployment Diff.
  - **Improved:** When adding a file to a Draft, its path is displayed in addition to its mode on the deployment Diff.
  - **Fixed:** Overflowing deployment Diffs and Workload errors are now scrollable.
  - **Improved:** Active deployments that stopped running are marked as "Stopped".

## Product Update May 21st, 2021

- **New:** Added support for path-based routing with Ingress on the Workload Details Page. This feature replaces the Public URL section.
  - DNS resource can now be added in the External Resources section.
  - Routing rules are defined within the newly added Ingress component.  
![path based routing](_assets/images/2021-05-21_Path_Based_Routing.png)

- **Changed:** Design and layout of App Settings. Added a danger zone and removed tabs from the UI to allow for a clearer overview and structure of the screen.

- **Improved:** Extended error message handling via tooltips in the Variables component for invalid placeholder paths.

- **Fixed:** It is now possible to add variables to a workload with multiple containers.

- **Fixed:** Configuration of Webhooks.
  - Closing the triggers-dropdown no longer removes all selected triggers.
  - Existing Webhooks can be disabled/enabled.

## Product Update May 7th, 2021

- **New:** Added support for [third-party container registries](https://humanitec.com/blog/third-party-container-registries-feature-announcement).  
![third-party registries](_assets/images/2021-05-07_Third_Party_Registries.png)

- **Fixed:** It is now possible to cancel the creation of a workload on the application details page.

- **Fixed:** The image dropdown on the Workload Details Page no longer overflows.

- **Improved:** Defined handling of special characters such as "\", '<' or '>' in the variables component on the Workload Details Page.

- **Changed:** The full image name is now shown for automatic deployment comments.

## Product Update April 23rd, 2021

- **New:** Added support for emptyDir volumes.  
![emptyDir volumes](_assets/images/2021-04-23_emptyDir_volumes.png)

- **Improvement:** We reworked the behaviour of the Variables component on the Workload Details Page. Inconsistencies in terms of its navigation and handling were removed to ensure a reliable user experience for entering, editing and saving data.
  - Improved keyboard accessibility.
  - Easier handling of Placeholder Paths.
  - Corrected behaviour for multi-line input.

- **Fixed:** It is no longer possible to cause a failed deployment due to a file being mounted into the root of a container.

- **Fixed:** Many UI inconsistencies.

## Product Update April 9th, 2021

- **New:** Added support for [Persistent Volumes](https://humanitec.com/blog/feature-announcement-persistent-volumes).  
![Persistent Volumes](_assets/images/2021-04-09_Persistant_Volumes.png)  
Mount paths are specied on the workload level.  
![Configure Persistent Volumes](_assets/images/2021-04-09_Configure_Persistent_Volumes.png)

## Product Update April 2nd, 2021

We will shift the product update to April 9th due to the short break over Easter.

## Product Update March 19th, 2021

- **New:** Forms for adding resource definitions now present fields in a more intuitive order and include help text.  
![Form Update](_assets/images/2021-03-21_Form_Update.png)

- **Improvement:** Draft can now be discarded even if it is the only draft. (A new blank draft is created in its place.)

- **Fixed:** Behaviour of clones in the UI is corrected.  Clone includes comment from deployment it was created from and is properly represented in the draft. Code version can be updated in the draft applied to clone.
- **Fixed:** Submitting variable value now possible when suggestions drop-down is shown.
- **Fixed:** Live container statuses sometimes not shown after deployment.

## Product Update March 5th, 2021

- **New:** Pod status is now communicated on the Workload tile in the Active Deployment mode.

- **Fixed:** It is now possible to replace a deleted resource definition with a new one of the same type with overlapping matching criteria while the original one is still in _pending deletion_ state.

## Product Update February 19th, 2021

- **New:** Errors at the Environment level are now surfaced in UI.
- **New:** Aiven added as an Account Type & [documentation](https://docs.humanitec.com/how-to-guides-devops/infrastructure-orchestration/manage-relational-databases/aiven) added for connecting Aiven managed databases.  
![Aiven Managed DBs](_assets/images/2021-02-19_Aiven_Managed_DB.png)

- **Improved:** Environments and Deployments pane in Workload Details screen expanded and Environment Tabs restructured.

- **Fixed:** Clicking outside the Dynamic/Static Resource Definition dialog does not cause all data to be automatically lost.
- **Fixed:** Form for specifying static DNS did not handle TLS certificates correctly.
- **Fixed:** Many UI inconsistencies.

## Product Update February 5th, 2021

- **New:** Workloads can now depend on multiple resources of the same type.  
![Multiple Resources of same Type](_assets/images/2021-02-05_Multiple_Resources.png)
- **New:** Added support for Aiven (Database-as-a-Service provider).  
![Added Aiven Support](_assets/images/2021-02-05_Aiven_Support.png)

- **Changed:** We changed the default deployment behaviour so that workloads no longer wait for a successful readiness probe before terminating the old pods. This means that the state of the namespace will match the requested deployment, but will mean that pods might be in a failed state. These will be reported in the UI. It will also mean deployments complete much faster. We are working on [Blue/Green Deployments](roadmap.md#bluegreen-deployment-strategy) to provide a reliable way of ensuring environment wide consistency.

- **Improved:** Both, our [GitHub Action](https://github.com/Humanitec/build-push-to-humanitec) as well as our [CircleCI Orb](https://circleci.com/developer/orbs/orb/humanitec/humanitec), now support the specification of additional docker arguments (e.g., `build-args`).
- **Improved:** Updated documentation of environment variables & secrets and container configuration.

- **Fixed:** Failing application deletion in the case of deployment errors.
- **Fixed:** Last environment in an application can no longer be deleted.

## Product Update January 22nd, 2021

Here is our first product update 2021. We started with some important new features into the new year.

- **New:** We created an Environment Settings Screen that bundles all environment-specific settings. We moved the *Automation Rules* and environment-specific *Shared values and secrets overrides* into this new screen. We now also allow users to specify a namespace in Kubernetes for each environment. This has been supprted by the API but not by the UI.  
![Environment Confguration Screen](_assets/images/2021-01-22_Environment_Settings_Screen.png)
- **New:** We are now allowing users to delete environments directly from the environment dropdown menu on the App Details Screen.  
![Delete Environments](_assets/images/2021-01-22_Delete_Environments.png)
- **New:** Out-of-the-box support for Amazon S3 buckets as Dynamic Resources.  
![Dynamic S3 Buckets](_assets/images/2021-01-22_Dynamic_S3_Buckets.png)

- **Improved:** Support multi-line values in *Shared values and secrets*.
- **Improved:** Listing of dynamic resources.

- **Fixed:** Adding overrides for shared variables cause console error *Cannot read property 'id' of undefined*.
- **Fixed:** Missing UI elements after creating a new environment.

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
