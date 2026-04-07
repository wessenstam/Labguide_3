# Website Scrapping for Articles

Now that there are some articles using different methodologies, we are going to test the tool that DevRev SEs use for scraping a website. The idea is to scrape Hastings’website and turn them into articles so they can be used to answer questions.


➔ Open a new tab in your browser and navigate to [https://devrev.community](https://devrev.community)

![](../images/image028.png)

*Image 22\. Overview of tools on devrev.community.*

➔ Open the S.P.I.D.E.R. tool and notice that there is a Personal Access Token needed. 

![](../images/image029.png)

*Image 23\. S.P.I.D.E.R. Pat key required.*

➔ Head back to DevRev environment and click **\< Settings** at the top of the navigation pane

![](../images/image030.png)

*Image 24\. Location of Settings.*

➔ Click the Initials and selects **Settings**.  
    
![](../images/image031.png)

*Image 25\. Location of Settings for PAT.*

➔ Click **\+ New Token** in the *Personal access tokens* section. 

![](../images/image032.png)

*Image 26\. Create a PAT.*

➔ Provide a meaningful name, click **Generate** and copy the PAT.

![](../images/image033.png)

*Image 27\. Generate a PAT.*

➔ The message shows that it can be seen only **once**. Make sure to store it somewhere where it can be reused when needed.

![](../images/image034.png)

*Image 28\. Copy generated PAT.*

➔ Head back to the S.P.I.D.E.R. UI and copy the PAT key, and click **Initialize** **Connection**. Three parameters have to be filled:

1. The URL to crawl  
2. What is the Target Part  
3. How deep should links be followed?

![](../images/image035.png)

*Image 29\. S.P.I.D.E.R. UI .*

➔ Use these parameters:

1. **URL(s) to Crawl**: https://www.hastingsdirect.com   
2. **Target Part**: Insurance (PROD-3)  
3. **Depth**: leave default 4

➔ Click **Start Crawling** button to start the crawl.

![](../images/image036.png)

*Image 29\. S.P.I.D.E.R. UI \- Running crawl session.*

➔ Now that the crawler is running, click the job shown in the Crawler jobs and see the progress by clicking once every while the **Refresh** button in the Recent Articles section. The two articles that have been created earlier for the Insurance part are shown.

![](../images/image037.png)

*Image 30\. S.P.I.D.E.R. UI \- Job details crawl session.*


!!! Example "Be aware"
    The process will take approx. 60 minutes for a full scrap as the site is quite large. In total approx. 300 pages will be pulled in as articles.  

➔ Wait approx. 5 minutes before heading back to the DevRev instance. 

### Organise Articles into Collections {#organise-articles-into-collections}

➔ Back in your instance navigate to **Settings \-\> Knowledge Base** and see the articles that have been scrapped so far.  

![](../images/image038.png)

*Image 31\. Overview of created Articles.*

➔ Click the **Collections** tab and read the description “Organize your articles into hierarchical folders, enhance structure with subfolders, and seamlessly categorize articles for optimal organization.”   
![](../images/image039.png)

*Image 32\. Collections creation.*

➔ Create *two Collections* by clicking the **\+ Collection** button. For the first Collection use the following parameters:

1. **Title:** IT related  
2. **Description:** Helpdesk articles for IT related inquiries  
3. **Publish Collection:** Active

![](../images/image040.png)

*Image 33\. Collection IT-Related creation.*

➔ Click **Create**

➔ For the second Collection use:

1. **Title:** Insurance related  
2. **Description:** Articles for Insurance related inquiries  
3. **Publish Collection:** Active

➔ Now that the two collections are created, articles need to be assigned to them.  

![](../images/image041.png)

*Image 34\. Assign articles to the Collections.*

➔ Clicks the **\+ Add** text to the far right of the line that shows IT related and selects **Add article**  

![](../images/image042.png)

*Image 35\. Add an article to a Collection.*

➔ In the new screen select the **Search** field and types *“Printer”* as we want that IT related article assigned to this collection. Only one item is shown. Select the checkbox and click **Add**

![](../images/image043.png)

*Image 36\. Add an article to a Collection.*

➔ Repeat the earlier steps to Add articles to the collection, but make sure it is set to the **Insurance related** collection, leave the search field *empty*, check the checkbox of all articles that are shown and click **Add** to have them assigned.

![](../images/image044.png)

*Image 37\. Add articles to the Insurance related Collection.*  

➔ After returning in the Collections overview, click the **\>** symbol shown just before the text of the collections. This will show the articles that have been assigned to the respective collections.

![](../images/image045.png)

*Image 38\. Collections and their assigned articles.*

<hr>

<font color="#FF6C0A" size="+2"><center><B>This concludes this module of the workshop</B></center></font>

<hr>