# Interact with Chat App

## Estimated Duration: 30 Minutes

## Overview

In this exercise, you will interact with the deployed chat application to validate the end-to-end Retrieval-Augmented Generation (RAG) workflow. The application uses Azure AI Search to retrieve relevant content from indexed documents and sends the retrieved context to Azure OpenAI Service to generate intelligent responses. This interaction demonstrates how AI can provide accurate, context-aware answers based on enterprise data.


## Lab Objectives

- Task 1: Test the Python app
- Task 2: Cleanup Resources

## Task 1: Test the Python app

In this task, you will test the functionality of the deployed web app by browsing it through the Azure Portal.

1. Open the application URL in browser:
     ```
     https://<your-app-name>.azurewebsites.net
     ```
    ![](./images/Lab4Images/EX-01.png)

    > **Note:** If you encounter any errors while opening the application, restart the application, wait for 2-3 minutes, and then try again.

1. In the chat app, select the **What happens in a performance review?** option, or enter the same text in the chat text box. The app returns the initial response:

    ![](./images/Lab4Images/EX-03.png)

1. In the answer box, select a **citation**:

    ![](./images/Lab4Images/EX-04.png)

1. It opens the right **Citation** pane with three tabbed regions and the focus is on the **Citation** tab:

     ![](./images/Lab4Images/EX-05.png)

    | Tab     |  Description  |
    |----------|-----------|
    | **Thought Process**   | Displays a script of the question/answer interactions in the chat. You can view the content provided by the chat app system, questions entered by the user, and clarifications made by the system assistant.    |
    | **Supporting Content**     | Lists the information used to answer your question and the source material. The number of source material citations is specified by the Developer settings. The default number of citations is 3.    |
    | **Citation** | Shows the original source contain for the selected citation. |

1. When you're done, select the currently selected tab in the right pane. The right pane closes.


1. The **Developer settings** option opens the Configure answer generation pane where you can change settings for the chat app:

    ![](./images/Lab4Images/EX-06.png)

1. The following steps walk you through the process of changing the settings.

    - In the browser, select the **Developer settings** option.

    - Select the **Suggest follow-up questions** checkbox to enable the option, and select **Close** to apply the setting change.

    - In the chat app, reask the question, this time by entering the text in the question box:

    ![](./images/Lab4Images/EX-08.png)
   
1. Select the **Developer settings** option again, and unselect Use **semantic ranker for retrieval** option. Close the settings.

1. Ask the same question again, and notice the difference in the answer from the chat app.

## Task 2: Clean up resources

After you complete the exercise, delete the Azure resources and remove the source code by running the following azd command:

```shell
    azd down --purge --force
```
> **Note** The command switches include:
> - ```purge``` : Deleted resources are immediately purged. This option allows you to reuse the Azure OpenAI tokens per minute (TPM) metric.
> - ```force```: The deletion happens silently, without requiring user consent.

    
> **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
> - If you receive a success message, you can proceed to the next task.
> - If not, carefully read the error message and retry the step, following the instructions in the lab guide. 
> - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

## Summary

In this exercise, you have accomplished the following:

- Succesfully Tested Python APP
- Cleanup the resources

## Conclusion

By completing this lab **RAG Chat Application with Azure OpenAI and Azure AI Search**, you gained practical experience in building intelligent search solutions powered by Azure’s AI services. You began by generating document embeddings with Azure OpenAI to capture semantic meaning and improve search relevance. You then implemented an advanced query and retrieval system using Azure AI Search, enabling efficient semantic search. Additionally, you worked with Document Intelligence to extract structured data from documents and  Finally, you automated the pipeline with Conatiner Apps, streamlining tasks such as document extraction, translation, embedding creation, and query handling. Through this integrated workflow, you developed a scalable knowledge search system that combines natural language understanding, and AI-driven insights to deliver accurate, context-aware results.


# You have successfully completed the Hands-on lab!