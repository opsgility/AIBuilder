## Exercise 3 - Extract information from receipts


- Using the same in-private browser instance, navigate to the [Power Apps site](https://make.powerapps.com/) site.  

- In the top right of the screen, ensure the Environment is set to **Dev One**.

- Choose **AI Hub** from the navigation. If it is not visible you might have to click the **... More** navigation to add it to the menu. 

    ![aihub](images/aihub.png)

- Click on the large **AI Models** button

    ![aimodelsbtn](images/aimodelsbtn.png)

- In the main portion of the screen click on the **Documents** tab to filter the results. 

- Finally, select **Extract information from receipts**

    ![](images/textfromreceipts.png)
    
- In the dialog, click on **Use prebuilt model** and choose **Use in a flow** option from the dropdown. This means we will build a re-usable Power Automate Flow to create a re-usable Flow to Extract all the text in photos and PDF documents (OCR). 

- Select the **Track expenses by scanning receipts to your OneDrive for Business** template that is already pre-created.

    ![](images/expenses.png)

- Very similiar to the previous exercise validate that you see green checks next to all the connections. Then click **Continue**

    ![](images/continue2.png)
    
    > Note: If you get an error on the OneDrive for Business like the following graphic. The issue is because OneDrive hasnt been provisioned yet.
    
    ![onedriveerror](images/onedriveerror.png)
    
    > Note: Then go to the Nine square button in the upper left hand corner. Right click on **OneDrive** and choose **Open in new tab**. Wait a few moments and you should see **Your OneDrive is ready**
    
    ![openinnewtab](images/openinnewtab.png)
    
    > Note: Click on the three dots to attempt a re-connect again. All checks should be green now.
    
    ![reconnect](images/reconnect.png)
    
- Before configuring the **Flow** click on the nine square in the upper-right hand corner. Then select the three dots next to **OneDrive** and choose **Open in new tab**

    ![](images/onedrivetab.png)
    
- In OneDrive click on the **Add new** button and choose **Files upload**

- Upload the following file **Receipts.xlsx** from the Lab Downloads file in the **AIBuilderLabFiles\ReceiptsProcessing_Contoso** folder.

- Return to the **Flow** tab in the browser

- There are two steps that need additional configuration. Select the first step called **When a file is created**. When selected the properties panel will open. Click on the **folder** icon and choose **Root** to select the top level folder in **OneDrive**.

    ![](images/rootselected.png)
    
- Now select the fourth, and last step, called **Add a row into a table**. **Note:** this does require the file to uploaded from the previous step. 

    ![](images/add-a-row.png)

   
- In the properties panel choose the **Document Library** and select **OneDrive**

    ![](images/onedrive2.png)
    
- Next click on the folder icon and select the **Receipts.xlsx** file previously uploaded.

- In the **Table** dropdown select **Table1** which is defined in the Excel spreadsheet that was uploaded to OneDrive.

    ![](images/ttable1.png)


- The view after configured.

    ![](images/add-table-final.png)

    
- In the **Advanced parameters** section you should see some pre-populated values. Click on the **Show all** link. This will show all the potential values available.

    ![](images/showall.png)
    
- From the **DateTime Format** dropdown choose **ISO 8601**

    ![](images/iso.png)

- Add additional parameters to fill in the Excel Spreadhsheet you can use the following animation to assist.

    ![](images/parmsmapping.gif)
    

- Click on **Save** in the upper right-hand corner

    ![](images/save1.png)
    
- Remove the following unnecessary options by clicking the X button. Then click **Save** again.

    ![](images/remove-fields.png)

  
- Then click on **Test** and choose the radio button for **Manually** and finally click the **Test** button. This will start the flow to monitor for uploaded files to OneDrive.

    ![](images/test3.png)
    

- Switch back to the OneDrive tab and upload one of the sample receipts from the C:\LabFiles\ReceiptsProcessing_Contoso folder. 

- This shows the completed **Flow**

    ![](images/receiptsflow.png)
    
- Now switch back to the **OneDrive** tab and open the **Receipts.xlsx** file

- Depending on the parameters added and file chosen you might see different values

    ![](images/receiptout.png)

    > The values were parsed from the uploaded reciept and stored in the spreadsheet.

    

## Summary

In this exercise, you created a flow that leveraged a pre-created AI Builder model to parse data out of uploaded reciepts and saved the results in a spreadsheet all without writing any code.
