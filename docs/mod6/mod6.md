# Setting Up AirSync with Confluence

Now that we have Articles via manual and scrapping using a tool, the next step is to import information from another tool ACME uses inside their organization, Confluence. 


!!! Abstract "Be aware"
    For AirSync with Confluence to work, there are some pre-requisite steps that need to be taken:

    * Admin access to your DevRev org  
    * Confluence Cloud account with admin rights  
    * Ability to generate a Confluence API token

    Without these AirSync can not be run. For more information on AirSync and specifically Confluence, use this link: [https://support.devrev.ai/en-US/devrev/article/BOVjni26-confluence-airsync](https://support.devrev.ai/en-US/devrev/article/BOVjni26-confluence-airsync) 

    For the workshop we will be using a Pre-Created Confluence environment that is controlled by DevRev SEs. The needed information has been sent by email and will **NOT** be shared in this document (including screenshots)\!  


### Step 1: Install the Confluence AirSync Snap-in {#step-1:-install-the-confluence-airsync-snap-in}

➔ Navigate to Snap-ins in the *Integration* section in the Settings panel.  
![](../images/image046.png)

*Image 39\. Location of the Snap-ins.*

➔ In the panel that is shown, click on the **All Snap-ins** tab and in the *Search* bar type **Confluence**. From the results click **Confluence** to go to the specific page for this Snap-in

![](../images/image047.png)

*Image 40\. Getting the Confluence Snapin.*

➔ In the top right corner of the screen that just opened click the **Add** button. In the new screen that opens, toggle the **Article Visibility**

![](../images/image048.png)

*Image 41\. Toggle switch for Article Visibility.*

➔ Click **Save** and **Install Snap-in**. Notice that the button has changed into other options: **Events, Start AirSync** and **Configure**.

![](../images/image049.png)

*Image 42\. Change of options in the Snap-in after Save and Install.*

In Events all items that have a relationship to this Snap-in have been mentioned. It can be used for internal changes that need to be stored for auditing reasons as example, but also to update admins on any possible changes that have been made.  
Configure brings back the toggle switches that have been seen earlier.

### Step 2: Configure the AirSync {#step-2:-configure-the-airsync}

➔ Click **Start AirSync** and you will asked to provide the connection for *Confluence*. 
➔ Click **Confluence**.  

![](../images/image050.png)

*Image 41\. Toggle switch for Article Visibility.*

➔ In the new screen Click the dropdown box. But as there is no connection yet available, select **\+ Add connection**.

![](../images/image051.png)

*Image 43\. Connection selection box.*

➔ In the connection screen use the following information:

1. **Connection name:** Internal Confluence  
2. **Subdomain:** The URL of your Confluence site,\<YOUR\_SITE\>.atlassian.net  
3. **Email:** The email address that belongs to the PAT  
4. **PAT:** The Personal Access Token

---

!!! Danger "Be aware"
    Below screenshots holds **EXAMPLE DATA\!\!\!\!** Use the information from the email you received for the correct information

---

![](../images/image052.png)

*Image 44\. Example Connection setup.*

➔ Click the **Next** button.
➔ In the screen that appears select the data source from the received email and assigns it to the **IT Part**. Leave the rest default.  
➔ Click the **Start** button.  

![](../images/image053.png)

*Image 45\. Setup the source and start the AirSync.*

### Step 3: Map fields between Confluence and DevRev {#step-3:-map-fields-between-confluence-and-devrev}

➔ In the screen that appears the AirSync shows after a few seconds and that **Field Mapping** is needed.

➔ Click the text **Map fields** and follow the steps that are needed to make the initial sync work. You will also get an email with the same sort of message.

![](../images/image054.png)

*Image 46\. Setup Field Mapping notification.*  

![](../images/image055.png){ width=50% }

*Image 47\. Setup Field Mapping notification as email.*

➔ Use the following selections and click the **Next** button to get to the next step:

* Step 1\. No changes  
* Step 2\. No changes  
* Step 3\. No changes  
* Step 4\. No changes  
* Step 5\. For all sub pages click the *two* **Select All** button 

![](../images/image056.png)

*Image 48\. Last step of the Field mapping setup.*

➔ Click **Finish**, a new screen appears stating that the mapping has been submitted successfully. On the last screen he also clicks the Finish button. 

![](../images/image057.png)

*Image 49\. Last step of the Field mapping setup.*

### Step 4: Checking the AirSync {#step-4:-checking-the-airsync}

➔ After a few seconds, the Sync status column has changed into **Completed**. 

![](../images/image058.png)

*Image 50\. The AirSync status.*

➔ By clicking on the line details are shown on the sync that has happened. On the **History** tab it shows what has been mapped from Confluence into DevRev and what happened to the items (CRUD)  

![](../images/image059.png)

*Image 51\. The AirSync historical status details.*

➔ Via the **Analytics** tab, you can see statistics on the articles that have been sync-ed. As it just is sync-ed and it takes approx. 24 hours to see anything, skips this tab for now.

➔ Under the **Mappings** tab, you could could make changes if the information is not correctly imported into DevRev.  

![](../images/image060.png)

*Image 52\. The AirSync field mappings details.*

➔ Under the Settings tab, this is where the following items can be set and/or updated:

1. **Subscribers;** the group/people who need to be updated on anything related to this AirSync  
2. **Periodic sync;** how often should this AirSync run and which way should there be a synchronization (Confluence AirSync can only Pull data into DevRev. Other, like Jira, can be a two-way synchronization). Also notifications can be set up for the periodic sync. Having a periodic sync makes it possible to import newly created items and have the latest and greatest in DevRev.  
3. **Archive;** This will stop the synchronization and the AirSync becomes Archived as state. Sync-ed information will stay and this action can be reverted.  
4. **Delete;** This is a non reverted action\!

![](../images/image061.png)

*Image 53\. The AirSync Settings details*


!!! Example "Why Archive?"
    A use case for Archive might be that due to maintenance the data source is not responding and the Subscribers and people don’t want to get notified due to a known issue. Putting the AirSync into Archive stops all without making any other changes to the settings.  


➔ No changes have to be made.

<hr>

<font color="#FF6C0A" size="+2"><center><B>This concludes this module of the workshop</B></center></font>

<hr>