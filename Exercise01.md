# AI Builder Lab

AI Builder is a Microsoft platform feature that provides a user-friendly interface for building, training, and deploying custom artificial intelligence (AI) models without the need for extensive coding or data science expertise. Integrated with Microsoft Power Platform and Dynamics 365, it empowers users to automate tasks and gain insights from data through AI-driven solutions. Users can leverage pre-built AI models or create their own using the intuitive interface. Common applications include form processing, object detection, predictive modeling, and OpenAI. Overall, AI Builder democratizes AI, making it accessible to a broader audience within organizations. 


## Exercise 1: Working with Documnents


## Overview 

In this exercise, you will download sample data that will be used throughout the rest of the lab. From there, you will use a pre-created AI model to demonstrate how to programmatically parse an invoice in PDF Format. 





### Task #1 - Verify your Microsoft Power Platform trial tenant

1.  Verify that you have your **Microsoft 365 credentials** from the Authorized Lab Host available. 

2.  In a new browser tab, navigate to `https://make.powerapps.com`

3.  Enter the `email address` provided by the Authorized Lab Host. 

4.  Select **Sign in**. 

5.  Enter the `password` provided by the Authorized Lab Host. 

6.  Optionally, select **Yes** to stay signed in.

7.  If prompted, enter `0123456789` for **Phone number** and select **Submit**.

8.  **Refresh** the tab and verify the **Dev One** environment is selected under **Environment** in the top right. 

## Task 2: Download sample data

Throughout the lab, you will need to upload various files to test out AI Builders capabilities.

- Open an new tab and download the sample data file by typing this short url in the browser (inside the VM) [https://tinyurl.com/3zzcr5k5](https://opsgilitylabs.blob.core.windows.net/public/aibuilder/AIBuilderSampleData.zip) and unzip it's contents into the new folder.

## Task 3: Using an AI Model and Flow to Parse invoices

- Choose **AI Hub** from the navigation. If it is not visible you might have to click the **... More** navigation to add it to the menu. 

    ![aihub](images/aihub.png)

- In the top navigation click on **Start free trial** for a 30 trial of AI Builder.

    ![aibuilderfree](images/aibuilderfree.png)
    
- Click on the large **AI Models** button

    ![aimodelsbtn](images/aimodelsbtn.png)
    
- In the main portion of the screen click on the **Documents** tab to filter the results. 

    ![](images/invoices.png)
    
- Finally, select **Extract information from Invoices**

    ![](images/extract-from-invoices.png)


- In the dialog, click on **Use prebuilt model** and choose **Use in a flow** option from the dropdown. This means we will build a re-usable Power Automate Flow to create a re-usable Invoice Flow. 

    ![](images/use-prebuilt-model.png)

    ![](images/useinflow1.png)

- There are several connections required for this demonstration to work. If you have never used that connection before the screen will resemble the following:

    ![](images/signing.png)
    
- Click **Sign in** for each connection. When you click **Sign in** you will see a quick dialog and when you have **Signed in** to all three connectors it will resemble the following with **Green** circled checks:

    ![](images/green.png)
    
- After that is complete you will need to click the **Continue** button

    ![](images/continue.png)
    
- This is using a pre-built model so there are no changes required to the **flow** presented

- Click on **Save** in the upper-right hand corner. Give it few seconds to complete. 

    ![](images/save1.png)\
    
- Then click on the **Test** button at the top right of your screen.

    ![](images/test.png)
    
- You might also get another **Sign in** prompt. Click **Continue**

    ![](images/signin2.png)
    

- Click the **Import** button.

- Open the **AIBuilderLabFiles** folder that has the downloaded sample data. Then open the **DocumentProcessing_Invoices_Adatum** folder and select the **Test** folder. There is only a single invoice in there and it is a pdf file called **Adatum 6.pdf** file. Select it for the import. 

- Then click the **Run flow** button at the bottom

    ![](images/adatum6.png)

- Flow is running. Then click **Done**

    ![](images/runsuccess.png)

- Since there were no changes made the **final** step in the **Flow** sends an email but you should see the following steps with **green** checks next to each step:

    ![](images/green1.png)
    
- Click the step called **Extract information from invoices.** There are two sections available in the step. **Inputs** and **Outputs**. The **Input** section will show a binary section of text that represents the submitted pdf file. In the **Outputs** section you can see all the extracted fields in JSON format (used by developers).

    ![](images/invoiceprocessed.png)

- If you want to see the email click on the **9 square** in the upper right hand corner. Then choose **Outlook** but choose **Open in new tab**

    ![](images/newtab.png)
    
- In **Outlook** open the item title **Invoice processed**

  
    
- Browse all the mapped fields in the email

    ![](images/invoiceemail.png)


    
## Summary

In this exercise, you created a flow that leveraged a pre-created AI Builder model to parse a PDF invoice and emailed the results all without writing any code.
