# Exercise 1 - Setup Azure Resources for RAG Application

## Estimated Duration: 60 Minutes

## Overview
In this exercise, you will set up the foundational Azure resources required to build the RAG application. You will deploy Azure OpenAI Service, set up Azure AI Search and create Document Intelligences. You will also deploy the required models, including a GPT model for generating responses and an embedding model for performing vector-based search. Additionally, you will collect the necessary keys and endpoints that will be used to connect these services in later modules.

By the end of this module, your environment will be fully configured and ready for data processing and application development.


## Lab Objectives
 In this lab, you will perform the following:

- Task 1: Create a Azure OpenAI
- Task 2: Deploy the AI Models
- Task 3: Deploy Azure AI Search 

### Task 1: Create a Azure OpenAI

In this task, you will begin by deploying an Azure OpenAI resource through the Azure portal. This involves creating an OpenAI resource, configuring it with the appropriate settings, and deploying models such as gpt-4.1 and text-embedding-3-large using Azure AI Foundry portal.


1. In the Search bar of the Azure portal, type **Azure OpenAI (1)**, then select **Azure OpenAI (2)**.

    ![](./images/Lab1Images/EX1-01.png)

1. On the Microsoft Foundry | Azure OpenAI, click **+ Create (1)**, and from the dropdown, choose **Azure OpenAI (2)**.

    ![](./images/Lab1Images/EX1-02.png)

1. On the Basics tab of Create Azure OpenAI resource page, enter the following details:

    - Leave the **Subscription (1)** as default.
    - Resource group: **Select Openai- (2)**
    - Region: **Select (3)**.
    - Name: **openai- (4)**
    - Pricing tier: **Standard S0 (5)** .
    - click on **Next (6)**

      ![Picture 1](./images/Lab1Images/EX1-03.png)

1. On the **Network** tab, leave the values as default and click on **Next**.

    ![](./images/Lab1Images/Ex1-04.png)

1. On the **Tags** tab, leave the value as default and click on **Next**.

    ![](./images/Lab1Images/Ex1-05.png)

1. On the **Review + submit** tab, review the configuration, and click on **Create**.
   
    ![](./images/Lab1Images/Ex1-06.png)

1. Once the deployment is complete, click on the **Go to resource** button.

    ![](./images/Lab1Images/Ex1-27.png)

1. On the Azure OpenAI resource, select **Keys & Endpoint (1)** under the **Resource Management** section from the left menu, click **Show Keys (2)**, copy **KEY 1 (3)**, and store them in a notepad for later use.

    ![](./images/Lab1Images/Ex1-28.png)

    


> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.


### Task 2 : Deploy the AI Models

In this task, you will design and implement a chat flow using Microsoft Foundry to interact with a deployed language model. You will test its functionality to ensure accurate and relevant responses and prepare the chat flow for deployment in a production environment.


1. From the left navigation menu, under **My assets**, select **Deployments (1)**.

    ![](./images/Lab1Images/Ex1-09.png)

1. On the **Manage deployments of your models and services**, under Model deployments tab, select **+ Deploy model (2)** and then select **Deploy base model (3)** from the dropdown.

    ![](./images/Lab1Images/Ex1-10.png)

1. On the **Select a model page**, search for **gpt-4.1-mini (1)**, **select gpt-4.1-mini (2)**, select **Confirm (3)** under the gpt-4.1-mini.
  
    ![](./images/Lab1Images/Ex1-11.png)

1. On **Deploy model gpt-4.1-mini**, click on **Customize**.

    ![](./images/Lab1Images/Ex1-12.png)



1. On Deploy model gpt-4.1-mini, follow these instructions to create the deployment:

    - Deployment Name: **gpt-4.1-mini (1)**
    - Deployment type: **Global Standard (2)**
    - Model version: **2025-04-14 (Default) (3)**
    - Tokens per Minute Rate Limit: **10K (4)**
    - Content Filter: **DefaultV2 (5)**
    - Select **Deploy (6)**

    ![](./images/Lab1Images/Ex1-13.png)

1. Once the deployment is complete, on the gpt-4.1-mini page click on Open in playground.

    ![](./images/Lab1Images/Ex1-14.png)

1. Repeat the process to create another deployment.

1. In the Microsoft Foundry portal, navigate to **Deployments (1)**, select **+ Deploy model (2)**, and then choose **Deploy base model (3)**.

    ![](./images/Lab1Images/Ex1-15.png)

1. On the Select a model page, search for **text-embedding-3-large (1)**, select **text-embedding-3-large (2)**, and click **Confirm (3)**.

    ![](./images/Lab1Images//Ex1-16.png)

1. On **Deploy model text-embedding-3-large**, click on **Customize**.

    ![](./images/Lab1Images/Ex1-17.png)

1. - Deployment Name: **text-embedding-3-large (1)**
    - Deployment type: **Global Standard (2)**
    - Model version: **1(Default) (3)**
    - Tokens per Minute Rate Limit: **50K (4)**
    - Content Filter: **DefaultV2 (5)**
    - Select **Deploy (6)**

    ![](./images/Lab1Images/Ex1-18.png)

### Task 3 : Create Azure AI Search

1. On Azure portal, Search for **Azure AI Search (1)**  in the search box and select **AI Search (2)** from the list.

    ![](./images/Lab1Images/Ex1-19.png)


1. On the Microsoft Foundry | AI Search blade, click on **+ Create**.

    ![](./images/Lab1Images/Ex1-20.png)

1. On the **Basics** tab of Create a search service resource page, enter the following details:
    - Subscription: **Default - Pre-assigned subscription (1)**
    - Resource Group: **Select Openai- (2)**
    - Service name: **aisearch- (3)**
    - Location: **Select (4)**
    - Pricing tier: **Standard (5)**
    - Click on **Review + create (6)**

    ![](./images/Lab1Images/Ex1-21.png)

1. Review the configuration, and click on **Create**.

    ![](./images/Lab1Images/Ex1-22.png)


1. On the Azure portal, search **Document intelligences (1)** in the search box and select **Document intelligences (2)** from the list.

    ![](./images/Lab1Images/Ex1-23.png)

1. On the Microsoft Foundry | Document intelligence, click on **+ Create**.
    
    ![](./images/Lab1Images/Ex1-24.png)

1. On the Basics tab, enter the following details:

    - Subscription: **Default-Pre-assigned subscription (1)**
    - Resource group: **Select Openai25(2)**
    - Region:**Select (3)**
    - Name: **Document-intelligence- (4)**
    - Pricing tier: **Standard S0 (1 Call per minute for training API) (5)**
    - Click on **Review + Create (6)**

    ![](./images/Lab1Images/Ex1-25.png)

1. Click on **Review + create** , review the configuration, and click on **Create** .

    ![](./images/Lab1Images/Ex1-26.png)

> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

<validation step="9fc4dcf9-792d-401a-b9ca-7439805c6518" />

## Summary
In this lab, you have completed the following:

- Created a Azure OpenAI Service
- Deployed AI Models
- Deployed Azure AI Search

## You have successfully completed the exercise!

### Now, click on **Next >>** from the lower right corner to move on to the next page.

   ![](./Images/gettingstartedimages/Next.png)