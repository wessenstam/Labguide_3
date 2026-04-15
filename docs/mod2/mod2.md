# Create the Workflow

**Objective**  
Create a workflow that will use a catagorization agent to have the correct AI agent answer the questions in a conversation with a human.

**What you will build**

* Create a PAT
* Create and Configure a Workflow
  * Import a template
  * Conversation created as trigger node
  * HTTP API Call
  * Categorization Agent
  * If Then Logic
  * Assign IT Support agent
  * Assign HR support agent

**Exercise steps**

➔ Log into your assigned lab environment.  

## Get the PAT
As we are gooing to run an HTTP API call to the environment itself, we need a PAT. The HTTP API call needs to authenticate itelf using a Bearer token and the PAT is exactly that.


!!! TIP
    In production it is best to have a AAT (Application Access Token). To have this created, follow the steps on the support site for Developers at https://developer.devrev.ai/api-reference/auth-tokens/create. You still need a PAT to run the API call. Advantage is that the AAT can be created and revoked on the fly. 

    For this workshop, we will leave the AAT for you to test.

➔ In the navigation pane, click **Account** at the top of the navigation pane.

![](../images/image017.png)

  *Image 14. Location of the Account text.*  

➔ In the **Personal access tokens** click the **+ New token** button.

![](../images/image018.png)

  *Image 15. Location of the Personal access token and button.*  

➔ In the screen that apears, provide a user friendly name for the usage and set the expiration time. As example **API Token** and **90 days**, and click **Generate**

![](../images/image019.png)

  *Image 16. Create a Personal access token.*  

➔ After you clicked generate, a warning message is shown that the key will only be shown once!!! Copy the PAT, by using the **Copy** button, to a file or a note and save it. We need it later in the creation of the workflow!!!

![](../images/image020.png)

  *Image 17. The warning and the PAT itself.*  

Now that we have the PAT we can proceed to creating the Workflow

## Create and confgure the workflow

➔ In the navigation pane, navigate to **Workflows**

![](../images/image004.png)

  *Image 14. Location of the Workflows text.*  

### Create a Workflow from a JSON template

From the second part of this workshop trilogy, you should have saved a JSON file of an existing workflow (Agent Playground workflow).

!!! Abstract "Get the needed Workflow JSON template file"

     If you have lost, or forgotten to save the JSON, Use one of the otions below, if you are viewing this workshop online, use the **Download** option. 

    ??? "Get the JSON from environment"
        ➔ There should be a workflow called **Agent Playground workflow**
        
        ![](../images/image021.png){ width=70% }
        
        *Image 18. Agent Playground workflow.*  
        
        ➔ Hoover the mouse over the workflow and click it. This will open the details of the workflow.
        
        ![](../images/image022.png){ width=80% }
        
        *Image 19. The details of the workflow are shown.*  
        
        ➔ Click the **Download** button (:octicons-download-16:) and save the file to a location you can remember as we need the downloaded JSON file in a few.


    ??? "Download"
        [Get the JSON File](../../Agent_Workflow.json)
    
➔ Click on **+ Workflow** in the top right corner.

![](../images/image023.png)

  *Image 20. Location of the + Workflow button.*  

➔ Click the **Import Workflow...** tile.

![](../images/image024.png)

  *Image 21. The Import tile.*  

➔ In the new screen, a file browser, select the JSON you downloaded or had saved and click **Open**

![](../images/image025.png)

  *Image 22. Location of the JSON file to be uploaded.*  

➔ After you clicked **Open** a canvas will open that looks something like the below screenshot.

![](../images/image026.png)

  *Image 23. The canvas from the uploaded JSON file.*  

Now we have a starting point that we need to configure to do what we are looking for.

### Configuring the imported Workflow

➔ Rename the workflow **IT or HR Agent switcher** by double clikcing on the existing name *Agent Playground*. 

![](../images/image028.png)

  *Image 24. Rename the workflow.*  

➔ Hit Enter to save the new name.

➔ In the canvas, click the arrow between the **Conversation Created** and **Talk to Agent** node, and hit the **delete** button on your keyboard.

!!! Abstract "What good looks like" 
    If you have selected it correctly, it will become a dashed line.

![](../images/image027.png)

  *Image 25. Select a connecting arrow between nodes.*  

➔ If you have done it correctly, you now have two seperated nodes on the canvas.

![](../images/image029.png){ width=30% }

  *Image 26. Seperated nodes.*  

➔ Click the **+** symbol at the end of the arrow that is starting on the bottom of the **Conversation Create** node, and select the **Action** node.

![](../images/image030.png){ width=30% }

  *Image 27. Add workflow node.*  

➔ In the new screen, search *HTTP* and click the **HTTP** tile you see as result.

![](../images/image031.png){ width=30% }

  *Image 28. HTTP node.*  

➔ In the side pane use the following parameters:

1. **Auth Token:** Follow the below steps:

      - Click **+ Add connection** 

        ![](../images/image032.png){ width=50% }

        *Image 29. Add Connection.*  
    
       - Click the **DevRev** tile.
       
           ![](../images/image033.png)

           *Image 30. DevRev tile.*  

        - **Make public:** Toggeled to **on**.
        - **Connection Name:** A user friendly name (ex. *DevRev Environment Connection*).
        - **Person access token:** The token you created earlier.

           ![](../images/image034.png)

           *Image 31. Connection configuration.*
        - Click **Next**.

2. In the side pane, select the created Connection under **Auth Token**.

    ![](../images/image035.png)

    *Image 32. The Auth Token.* 

3. In the **Url** field use https://api.devrev.ai/timeline-entries.list and click the **Save** button.

    ![](../images/image036.png)

    *Image 33. The URL for the HTTP API call.* 

    !!!Danger "BE AWARE!!"
        When you copy or type the URL, make sure that the text is not a "Code" selection (:material-code-block-tags:). If you see something like *MD* mentioned, make sure to deselect the Code icon. If you don't do this, the HTTP API will throw an error!!!

4. Change the Auth Type field to **Bearer**.

    ![](../images/image037.png)

    *Image 34. The Auth Type HTTP API call.* 


5. Change the *Method* to **POST**

    ![](../images/image038.png)

    *Image 35. The Method for the HTTP API call.* 

6. Click the **+ Add attribute** at the bottom of the side pane and select **Body**, and click somewhere in the side pane to have the attribute available.

    ![](../images/image039.png)

    *Image 36. The Body for the HTTP API call.* 

7. In the Body field, type the following information **{"object":""}**. Put the cursor in the middel of the two double quotes and click **Insert variable** just below the field.

    ![](../images/image040.png)

    *Image 37. Configuring the Body. Location of the cursor and the Insert variable for the HTTP API call.* 

8.  Select **Conversation > Output > ID** (all the way at the bottom of the extra side pane)

    ![](../images/image041.png)

    *Image 38. The location of the needed variable for the HTTP API call.* 

9. Your body should now look **exactly** like the below screenshot.

    ![](../images/image042.png)

    *Image 39. The full Body for the HTTP API call.* 

➔ All not mentioned sections, leave them default.

### Test the HTTP API call

Now that we have the HTTP API call configured, we have the possibility to test it. 

➔ In the top of the side pane, you see a **Play** button (:material-play-outline:). click this button

![](../images/image043.png)

  *Image 40. The test button.*  

➔ An extra new side pane opens. Use the following parameters to test the HTTP API call:

1. **Auth Token**: Select the earlier created Connection. 

    !!! Warning
        If you don't see your connection being shown, you have forgotten to toggle the **Make Public** switch!!! To get that sorted, navigate to **AirSync** and in the top right corner is a button called **Connections**. Click the button, this will show ALL connections. One of the is the earlier created connection. On the far right of that connection name are **three dots**. Click the dots and select **Share**. Then toggle the **Anyone in demowe** switch.

        Now return to **Workflows > Select the Draft tile** at the top of the screen and you will find your Workflow you were working on before. Click it and you're back in the Canvas. Click the **HTTP** node and the **Play** button to return to the testing the HTTP API call.


2. In the **Id** field, select one of the **Conversations Ids**.

    ![](../images/image044.png)

    *Image 41. The test fields.*  

3. Now click the **Execute** button and the Putput should show information.

    ![](../images/image045.png)

    *Image 41. The output of the test run.*  

    !!! Abstract "Most common issues"
        When no data is returned, but an error thrown, here are the most common issues:

        1. The Auth Token is not set in the test pane
        2. The Address is the Uri field is incorrect
        3. The Body is not correctly set up.

        Check these three items and if all seems ok, ask for help.

### Ask AI node

➔ To return to the canvas, click the double arrows pointing right at the top of the side pane just above HTTP and its icon.

![](../images/image046.png)

  *Image 42. Collapsing the side pane.*  

➔ Click the **+** symbol on the bottom side of the *HTTP node* to add an **Action node**

![](../images/image047.png){ width=30% }

  *Image 43. Add workflow node.*  

➔ 



<hr>

<font color="#FF6C0A" size="+2"><center><B>This concludes this module of the workshop</B></center></font>

<hr>