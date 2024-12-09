## Exercise 4 - Detect positive, negative, or neutral sentiment

In this exercise rather than use a pre-built model. We will be creating our own model.

- Using the same in-private browser instance, navigate to the [Power Automate site](https://make.powerautomate.com/) if you are not already there. 


- In the top right of the screen, ensure the Environment is set to **Dev One**.


- Choose **Create** from the navigation. 

    ![](images/create.png)
    
- Then choose **Automated cloud flow**

    ![](images/autocloudflow.png)
    
- In the following prompt select **When a file is created** for the **OneDrive for Business** trigger. Then click **Create**.

    ![](images/onedrive3.png)

- Click the **When a file is created** action.

    ![](images/when-file-created.png)

- There should be one **Trigger** on the page that needs to be configured.

- Select the **Trigger** and select **Root**
    ![](images/select-root.png)

    ![](images/rootselected.png)
    
- Next click on the **+** sign and choose **Add an action**

    ![](images/addaction.png)
    
- In the slideout search for **sentiment** and choose **Analyze positive or negative sentiment in text**. This will add another step to the flow.

    ![](images/sentiment2.png)

- The properties side panel will open. In the **Language** section click on the dropdown and choose **English**

    ![](images/english.png)
    
- In the **Text** field we need to pass in the value provided from **OneDrive**. Specifically the content. Click inside the text field and it will be highlighted with a blue bounding box. Then click on the blue lightning bolt.

    ![](images/lightning.png)
    
- In the popup search for **content** in the text box and then choose **File content**

    ![](images/filecontent.png)
    
- Next click on the **+** sign and choose **Add an action**

    ![](images/add-action-sentiment.png)
    
- Search for **condition** and select **Condition** from the options provided

    ![](images/condition.png)
    
- The resulting condition

    ![](images/condition2.png)
    
- Let's set the **Condition** parameters. Click in the **Choose a value** field and you will notice the blue box. Click on the lightning bolt. Then scroll down and select **Overall text sentiment**. In the second text box put in the word **positive**.

    ![sentencesentiment](images/sentencesentiment.png)
    
- In the **True** path add another **Action**

    ![](images/addactiontrue.png)
    
- Search for **notification** and choose **Send me an email notification**

    ![](images/emailnotification.png)
    
- You will be prompted to create a new connection. Click **Create New**.

    ![](images/notification-connection.png)

- Click in the **Subject** text box and click on the lightning bolt and select **Sentence sentiment**

    ![subject](images/subject.png)

    
- Do exactly the same steps for the **Body** content

- Then repeat the same steps on the **False** path.

- Click on **Save** and wait a few moments until you get a confirmation that the flow has been saved

    ![](images/readytotest.png)
    
- Then click on **Test** and choose the radio button for **Manually** and finally click the **Test** button. Similar to the previous exercise you need to kickoff the test, switch the **OneDrive** and upload one of the sample review files from the downloaded sample data: **AIBuilderLabFiles\Reviews**.

    ![](images/test.png)

    > Note: It may take several minutes for the flow to start after you upload the review to OneDrive. Switch back to the browser tab with your flow to see it start.

- After the flow completes it should resemble the following

    ![](images/completed1.png)
    
- You can also visit the **Outlook** web client to see the notification and text that was sent.

    ![](images/mixed.png)


## Summary

In this exercise, you created a flow that leveraged a pre-created AI Builder model to parse and analyze sentiment data out of uploaded review data all without writing any code.