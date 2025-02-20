---
title: Configuring Production Pipelines
description: Configuring Production Pipelines
index: yes
---

# Configuring a Production Pipeline {#configure-production-pipeline}

The Deployment Manager is responsible for configuring the Production Pipeline.

>[!NOTE]
>A Production Pipeline cannot be setup until a program creation is complete, Git repository has at least one branch, and a Production and Stage environment set is created.

Before you start to deploy your code, you must configure your pipeline settings from the [!UICONTROL Cloud Manager].

>[!NOTE]
>You can change the pipeline settings after initial set up.

## Adding a New Production Pipeline {#adding-production-pipeline}

Once you have setup your program and have at least one environment using [!UICONTROL Cloud Manager] UI, you are ready to add a production pipeline.

Follow these steps to configure the behavior and preferences for your production pipeline:

1. Navigate to the **Pipelines** card from the **Program Overview** page.
Click on **+Add** and select **Add Production Pipeline**. 

   ![](/help/implementing/cloud-manager/assets/configure-pipeline/add-prod-1.png)

1. **Add Production Pipeline** dialog box displays. Enter the pipeline name.

   Additionally, you can also set up **Deployment Trigger** and **Important Metric Failures Behavior** from **Deployment Options**. Click on **Continue**.

   ![](/help/implementing/cloud-manager/assets/configure-pipeline/prod-pipeline-add2.png)


   You can define the deployment triggers to start the pipeline.

    * **Manual** - using the UI manually start the pipeline.
    * **On Git Changes** - starts the CI/CD pipeline whenever there are commits added to the configured git branch. Even if you select this option, you can always start the pipeline manually.  

      During pipeline setup or edit, the Deployment Manager has the option of defining the behavior of the pipeline when an important failure is encountered in any of the quality gates.

       This is useful for customers who have the desire for more automated processes. The available options are:

    You can define the important failure metrics behavior to start the pipeline.

      * **Ask every time** - This is the default setting and requires manual intervention on any Important failure.
      * **Fail Immediately** - If selected, the pipeline will be cancelled whenever an Important failure occurs. This is essentially emulating a user manually rejecting each failure.
      * **Continue Immediately** - If selected, the pipeline will proceed automatically whenever an Important failure occurs. This is essentially emulating a user manually approving each failure.

1. The **Add Production Pipeline** dialog box includes a second tab labeled as **Source Code**. You can either select **[Front End Code](/help/implementing/cloud-manager/configuring-pipelines/introduction-ci-cd-pipelines.md#front-end)** or **[Full Stack Code](/help/implementing/cloud-manager/configuring-pipelines/introduction-ci-cd-pipelines.md#full-stack-pipeline)**. 

   ![](/help/implementing/cloud-manager/assets/configure-pipeline/prodpipeline-fullstack1.png)

   If you selected **Front End Code**, you must select the **Repository**, **Git Branch** and **Code Location**, as shown in the figure below:
    ![](/help/implementing/cloud-manager/assets/configure-pipeline/prodpipeline-fullstack1.png)

   If you selected **Full Stack Code**, you must select the **Repository**, **Git Branch** and **Production Deployment Options** (details below), as shown in the figure:
   ![](/help/implementing/cloud-manager/assets/configure-pipeline/prodpipeline-fullstack2.png)

   **Production Deployment Options:**

      * **Pause before Deploying to Production**: This option allows the deployment to pause before production.
      * **Scheduled**: This option allows the user to enable the scheduled production deployment.

   >[!IMPORTANT]
   >If a Full Stack Code pipeline already exists for the selected environment, this selection will be disabled.
   >![](/help/implementing/cloud-manager/assets/configure-pipeline/full-stack-disabled.png)

   >[!NOTE]
   >Before you start configuring the Front End pipelines, see [AEM Quick Site Creation Journey](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites-journey/quick-site/overview.html) for an end to end workflow through the easy-to-use AEM Quick Site Creation tool. This documentation site will help you streamline the front-end development of your AEM Site and quickly customize your site with no AEM backend knowledge.

1. Click on **Continue** once you selected the options from the **Source Code** tab.
  
1. The **Add Production Pipeline** dialog box includes a third tab labeled as **Experience Audit**. This option provides a table for the URL paths that should always be included in the Experience Audit. 

   ![](/help/implementing/cloud-manager/assets/configure-pipeline/add-prod-audit.png)

   >[!IMPORTANT]
   >You must click on **Add Page** to define your own custom link. Page path must start with `/`.
   >![](/help/implementing/cloud-manager/assets/configure-pipeline/add-prod-audit2.png)
 

   Click **Add New Page** to provide a URL path to be included in the Experience Audit.

   For instance, if you would like to include `https://wknd.site/us/en/about-us.html` in the Experience Audit, enter the path `/us/en/about-us.html` in this field and click **Save**.

   ![](/help/implementing/cloud-manager/assets/configure-pipeline/add-prod-audit3.png)

   The URL that appears in the table will be:
   
   `https://publish-p12361-e112003.adobeaemcloud.com/us/en/about-us.html`

   ![](/help/implementing/cloud-manager/assets/configure-pipeline/add-prod-audit4.png)

   A maximum of 25 rows can be included. If there are no pages submitted by the user in this section, the homepage of the site will be included in the Experience Audit by default.
 
   Refer to [Understanding Experience Audit Results](/help/implementing/cloud-manager/experience-audit-testing.md) for more details.

    >[!NOTE]
    > The pages that are configured will be submitted to the service and evaluated according to the performance, accessibility, SEO (Search Engine Optimization), best practice, and PWA (Progressive Web App) tests. 
    
1. Click on **Save**. The newly created production pipeline now displays in the **Pipelines** card.

   The pipeline is shown on the card on the home screen with four actions, as shown below:

      ![](/help/implementing/cloud-manager/assets/configure-pipeline/prod-created.png)
   
   * **Add** - allows adding of a new pipeline.
   * **Show All** - allows the user to view all the pipelines.
   * **Access Repo Info** - allows the user to get the information necessary to access Cloud Manager Git repository.
   * **Learn More** - navigates to understanding the CI/CD pipeline documentation resource. 


