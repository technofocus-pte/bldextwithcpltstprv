# Lab 03- Using a connection to Azure OpenAI on your data for generative answers

**Lab duration** – 40 minutes

**Objective:**

In this lab, we will learn how to use the Azure Open AI connection in
the copilot to generate answers.

## Exercise 0: Register the required Resource providers

1.  Login to +++<u><https://portal.azure.com/>+++</u>, using the Azure
    account credentials from the Resources tab of the VM.

2.  On **Welcome to Microsoft Azure** dialog box, click on **Maybe
    later** button.

> <img src="./media/image1.png" style="width:6.5in;height:4.425in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Type in +++**Subscriptions**+++ in the search bar and select
    **Subscriptions**.

<img src="./media/image2.png" style="width:6.5in;height:3.69444in"
alt="A screenshot of a computer Description automatically generated" />

4.  Click on your assigned **subscription**.

<img src="./media/image3.png" style="width:6.5in;height:2.57917in"
alt="A screenshot of a computer Description automatically generated" />

5.  From the left menu, click on the **Resource Providers** under
    Settings.

<img src="./media/image4.png" style="width:6.5in;height:4.62153in"
alt="A screenshot of a computer Description automatically generated" />

6.  In the search bar, type +++**Microsoft.Storage**+++, select
    **Microsoft.Storage** from the list below. Click on the three dots
    and select **Register**.

<img src="./media/image5.png" style="width:4.65874in;height:3.0336in"
alt="A screenshot of a computer Description automatically generated" />

> <img src="./media/image6.png" style="width:5.25045in;height:2.95859in"
> alt="A screenshot of a computer Description automatically generated" />

7.  A notification stating **Successfully registered resource provider**
    is obtained once the registration is successful.

8.  Repeat steps 6 and 7 to register the following Resource providers.

    - **Microsoft.Security**

    - **Microsoft.Search**

    - **Microsoft.CognitiveServices**

    - **Microsoft.Sql**

    - **Microsoft.Web**

    - **Microsoft.ManagedIdentity**

## Exercise 1: Create Azure OpenAI resource

1.  From the Azure portal home page, click on **Azure portal menu**
    represented by three horizontal bars on the left side of the
    Microsoft Azure command bar as shown in the below image.

> <img src="./media/image7.png" style="width:6.5in;height:4.69653in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Navigate and click on **+ Create a resource**.

> <img src="./media/image8.png" style="width:6.5in;height:4.78194in"
> alt="A screenshot of a computer Description automatically generated" />

3.  On **Create a resource** page, in the **Search services and
    marketplace** search bar, type **Azure OpenAI**, then press the
    **Enter** button.

> <img src="./media/image9.png" style="width:4.77917in;height:4.19021in"
> alt="A screenshot of a computer Description automatically generated" />

4.  In the Marketplace page, navigate to the Azure OpenAI section, click
    on the Create V chevron button, then click on **Azure OpenAI** as
    shown in the image. (In case, you clicked on the Azure **OpenAI
    section**, then click on the **Create** button on the **Azure OpenAI
    page**).

> <img src="./media/image10.png" style="width:4.8625in;height:5.056in"
> alt="A screenshot of a computer Description automatically generated" />

5.  In the **Create Azure OpenAI** window, under the **Basics** tab,
    enter the following details and click on the **Next** button.

    1.  **Subscription**: Select the assigned subscription

    2.  **Resource group**: click on Create new\> enter **AOAI-RGXX**(XX
        can be a unique number)

    3.  **Region**: Select **East US**

    4.  **Name**: Azure-openai-testXX (XX can be a unique number) (here,
        we entered **Azure-open-test29**)

    5.  **Pricing tier**: Select **Standard S0**

> <img src="./media/image11.png" style="width:6.5in;height:6.46667in"
> alt="A screenshot of a computer Description automatically generated" />
>
> <img src="./media/image12.png" style="width:6.5in;height:6.41667in"
> alt="A screenshot of a computer Description automatically generated" />

6.  In the **Network** tab, leave all the radio buttons in the default
    state, and click on the **Next** button.

> <img src="./media/image13.png" style="width:5.58101in;height:5.89583in"
> alt="A screenshot of a computer Description automatically generated" />

7.  In the **Tags** tab, leave all the fields in the default state, and
    click on the **Next** button.

> <img src="./media/image14.png" style="width:5.1625in;height:6.08222in"
> alt="A screenshot of a computer Description automatically generated" />

8.  In the **Review+submit** tab, once the Validation is Passed, click
    on the **Create** button.

> <img src="./media/image15.png" style="width:6.48333in;height:7.51667in"
> alt="A screenshot of a computer Description automatically generated" />

9.  Wait for the deployment to complete. The deployment will take around
    10-15 minutes.

<img src="./media/image16.png" style="width:7.13421in;height:3.13265in"
alt="A screenshot of a computer Description automatically generated" />

10. On **Microsoft.CognitiveServicesOpenAI** window, after the
    deployment is completed, click on the **Go to resource** button.

<img src="./media/image17.png" style="width:7.09744in;height:3.27083in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 2- Create an Azure Storage Account and Azure cognitive Search by using the portal

### **Task 1: Cognitive Services Usages Reader for the Azure OpenAI resource**

1.  From the home page of Azure portal(+++https://portal.azure.com+++),
    type in +++**Subscriptions**+++ in the search bar and select
    **Subscriptions**.

<img src="./media/image2.png" style="width:6.5in;height:3.69444in"
alt="A screenshot of a computer Description automatically generated" />

2.  Click on your assigned **subscription**.

<img src="./media/image3.png" style="width:6.5in;height:2.57917in"
alt="A screenshot of a computer Description automatically generated" />

3.  From the left menu, click on the **Access control(IAM).**

<img src="./media/image18.png"
style="width:6.49167in;height:5.41667in" />

4.  On the Access control(IAM) page, Click +**Add** and select **Add
    role assignments.**

<img src="./media/image19.png"
style="width:6.49167in;height:4.45833in" />

5.  Type the **Cognitive Services Usages Reader** in the search box and
    select it. Click **Next**

<img src="./media/image20.png" style="width:6.49167in;height:5.5in" />

6.  In the **Add role assignment** tab, select Assign access to User
    group or service principal. Under Members, click **+Select members**

<img src="./media/image21.png" style="width:6.49167in;height:5.83333in"
alt="A screenshot of a computer Description automatically generated" />

7.  On the Select members tab , search your Azure OpenAI subscription
    and click **Select.**

<img src="./media/image22.png" style="width:4.71667in;height:7.64167in"
alt="A screenshot of a computer Description automatically generated" />

8.  In the **Add role assignment** page, Click **Review + Assign**, you
    will get a notification once the role assignment is complete.

<img src="./media/image23.png" style="width:6.5in;height:5.25in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image24.png" style="width:6.5in;height:5.75in"
alt="A screenshot of a computer Description automatically generated" />

9.  You will see a notification – added as Cognitive Services Usage
    Reader for Azure Pass-Sponsorship.

<img src="./media/image25.png" style="width:5.06667in;height:2.73333in"
alt="A screenshot of a computer Description automatically generated" />

10. In Azure subscription page from the left menu, click on the **Access
    control(IAM).**

<img src="./media/image18.png"
style="width:6.49167in;height:5.41667in" />

11. On the Access control(IAM) page, Click +**Add** and select **Add
    role assignments.**

<img src="./media/image19.png"
style="width:6.49167in;height:4.45833in" />

12. Type the [**Cognitive Services
    Contributor**](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/role-based-access-control#cognitive-services-contributor)
    in the search box and select it. Click **Next**.

<img src="./media/image26.png" style="width:6.5in;height:5.525in" />

13. In the **Add role assignment** tab, select Assign access to User
    group or service principal. Under Members, click **+Select members**

<img src="./media/image27.png" style="width:6.5in;height:6.375in" />

14. On the Select members tab , search your Azure OpenAI subscription
    and click **Select.**

<img src="./media/image22.png" style="width:4.71667in;height:7.64167in"
alt="A screenshot of a computer Description automatically generated" />

15. In the **Add role assignment** page, Click **Review + Assign**, you
    will get a notification once the role assignment is complete.

<img src="./media/image28.png" style="width:6.5in;height:6.74167in" />

<img src="./media/image29.png" style="width:6.5in;height:6.625in" />

16. You will see a notification – added as Cognitive Services Usage
    Reader for Azure Pass-Sponsorship.

<img src="./media/image30.png"
style="width:4.1194in;height:1.88806in" />

17. Click on **Home**, search for +++**Azure OpenAI**+++ in the search
    bar and select **Azure OpenAI.**

> <img src="./media/image31.png" style="width:5.49167in;height:3.95833in"
> alt="A screenshot of a computer Description automatically generated" />

18. Click on your **Azure OpenAI** service.

<img src="./media/image32.png" style="width:6.49167in;height:2.80833in"
alt="A screenshot of a computer Description automatically generated" />

19. From the left menu, click on the **Access control(IAM).**

<img src="./media/image33.png" style="width:6in;height:5.33333in"
alt="A screenshot of a computer Description automatically generated" />

20. On the Access control(IAM) page, Click +**Add** and select **Add
    role assignments**.

<img src="./media/image34.png" style="width:6.5in;height:5.25in"
alt="A screenshot of a computer Description automatically generated" />

21. Type the [**Cognitive Services
    Contributor**](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/role-based-access-control#cognitive-services-contributor)
    in the search box and select it. Click **Next**.

<img src="./media/image35.png" style="width:6.5in;height:4.65in"
alt="A screenshot of a computer Description automatically generated" />

22. In the **Add role assignment** tab, select Assign access to User
    group or service principal. Under Members, click **+Select members**

<img src="./media/image27.png" style="width:6.5in;height:6.15417in"
alt="A screenshot of a computer Description automatically generated" />

23. On the Select members tab , search your Azure OpenAI subscription
    and click **Select.**

<img src="./media/image22.png" style="width:4.71667in;height:7.64167in"
alt="A screenshot of a computer Description automatically generated" />

24. In the **Add role assignment** page, Click **Review + Assign**, you
    will get a notification once the role assignment is complete.

<img src="./media/image28.png" style="width:6.5in;height:6.17083in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image29.png" style="width:6.5in;height:6.1625in"
alt="A screenshot of a computer Description automatically generated" />

25. You will see a notification – added as Cognitive Services Usage
    Reader for Azure Pass-Sponsorship.

<img src="./media/image36.png" style="width:3.6in;height:1.075in"
alt="A screenshot of a computer Description automatically generated" />

### **Task 2: Create an Azure Storage Account by using the portal**

1.  Sign in to the +++**<https://portal.azure.com/>+++**

2.  Click on the **Portal Menu**, then select **+ Create a resource**

<img src="./media/image37.png" style="width:4.57489in;height:3.71667in"
alt="Graphical user interface, application Description automatically generated" />

3.  In the **Create a resource** window search box, type +++**Storage
    account**+++ and then click on the **storage account**.

<img src="./media/image38.png" style="width:6.5in;height:4.44167in"
alt="Graphical user interface, application Description automatically generated" />

4.  In the **Marketplace** page, click on the **Storage account**
    section.

<img src="./media/image39.png" style="width:6.5in;height:3.80347in"
alt="A screenshot of a computer Description automatically generated" />

5.  In the **Storage account** window, click on the **Create** button.

<img src="./media/image40.png" style="width:6.5in;height:3.80347in"
alt="A screenshot of a computer Description automatically generated" />

6.  On **Create a storage account** window, under the **Basics** tab,
    enter the below details to create a storage account and then click
    on **Review + create**

- 

| **Subscription** | Select your Azure OpenAI subscription |
|----|----|
| **Resource group** | Select AOAI-RGXX |
| **Storage account name** | **azureopenaistorageXX**(XX can be a unique number) (here, we entered **azureopenaistorage39**) |
| **Region** | **East US** |
| **Performance** | **Standard: **Recommended for most scenarios (general-purpose v2 account) |
| **Redundancy** | **Locally-redundant storage (LRS)** |

<img src="./media/image41.png"
style="width:5.69216in;height:5.39213in" />

7.  On the **Review** tab, click on the **Create** button.

<img src="./media/image42.png"
style="width:4.89183in;height:5.29735in" />

8.  This new Azure Storage account is now set up to host data for an
    Azure Data Lake. Click on the **Go to resource** button.

<img src="./media/image43.png" style="width:6.5in;height:2.90139in" />

9.  After the account has been deployed, you will find options related
    to Azure Data Lake in the Overview page. In the left-side navigation
    pane, navigate to **Data storage** section, then click on
    **Containers**.

<img src="./media/image44.png"
style="width:4.93704in;height:5.11553in" />

10. On **azureopenaistorageXX \| Containers** page, click on
    **+Container.**

> <img src="./media/image45.png" style="width:6.5in;height:3.75in" />

11. On the New container pane that appear on the right side, enter the
    container **Name** as +++ **source**+++ and click on **Create**
    button.

> <img src="./media/image46.png" style="width:2.975in;height:7.275in" />

12. On **azureopenaistorageXX \| Containers** page, select **source**
    container.

> <img src="./media/image47.png" style="width:6.5in;height:4.175in" />

13. On **source** container page, click on **Upload** button.

> <img src="./media/image48.png" style="width:6.5in;height:3.675in" />

14. In the **Upload blob** pane, click on **Browse for file**, navigate
    to **C:\Labfiles** location and select **TF-AzureOpenAI.pdf**, then
    click on the **Open** button.

> <img src="./media/image49.png" style="width:5.5in;height:4.75in" />
>
> <img src="./media/image50.png" style="width:6.49167in;height:4.075in" />

15. In **Upload blob** pane, click on the **Upload** button.

> <img src="./media/image51.png" style="width:5.425in;height:4.175in" />

16. You will see a notification – **Successfully uploaded blob** when
    the uploaded is succeeded.

> <img src="./media/image52.png"
> style="width:4.66667in;height:2.20833in" />
>
> <img src="./media/image53.png" style="width:6.5in;height:3.36875in" />

### **Task 3: Create an Azure Cognitive Search service in the portal**

1.  From the **azureopenaistorageXX \| Containers** page, click on
    **Home** to go back to Azure portal home page.

> <img src="./media/image54.png" style="width:6.00189in;height:4.386in" />

2.  In Azure portal home page, click on **+ Create Resource**.

> <img src="./media/image55.png"
> style="width:5.2125in;height:2.94416in" />

3.  In the **Create a resource** page search bar, type **Azure AI
    Search** and click on the appeared **azure ai search**.

<img src="./media/image56.png" style="width:6.5in;height:3.64167in" />

4.  Click on **azure ai search** section.

<img src="./media/image57.png"
style="width:6.49167in;height:4.65833in" />

5.  In the **Azure AI Search** page, click on the **Create** button.

> <img src="./media/image58.png" style="width:5.15in;height:3.75833in" />

6.  On the **Create a search service** page, provide the following
    information and click on **Review+create** button.

| **Field**          | **Description**                                |
|--------------------|------------------------------------------------|
| **Subscription**   | Select your Azure OpenAI subscription          |
| **Resource group** | Select your Resource group                     |
| **Region**         | EastUS                                         |
| **Name**           | **mysearchserviceXX** (XXcan be unique number) |
| **Pricing Tier**   | Click on change Price Tire\>select **Basic**   |

<img src="./media/image59.png"
style="width:5.79583in;height:5.28991in" />

<img src="./media/image60.png" style="width:5.4875in;height:4.3745in" />

<img src="./media/image61.png"
style="width:4.63844in;height:4.37083in" />

7.  Once the Validation is passed, click on the **Create** button.

<img src="./media/image62.png"
style="width:4.73836in;height:5.54735in" />

<img src="./media/image63.png" style="width:7.45697in;height:3.25525in"
alt="A screenshot of a computer Description automatically generated" />

8.  After the deployment is completed, click on the **Go to resource**
    button.

<img src="./media/image64.png"
style="width:7.12476in;height:2.95417in" />

9.  In the **mysearchserviceXX** Overview page. In the left-side
    navigation pane, under **Settings** section, select **Semantic
    ranker**.

<img src="./media/image65.png" style="width:6.5in;height:5.48333in" />

10. On the **Semantic ranker** tab**,** select **Free** tile and click
    on the **Select plan.**

<img src="./media/image66.png"
style="width:6.49167in;height:4.95833in" />

11. You will see a notification -**Successfully updated semantic ranker
    to free plan**

<img src="./media/image67.png" style="width:6.5in;height:4.40833in" />

## Exercise-3: Add your data using Azure OpenAI Studio

### **Task 1: Deploy gpt-3-turbo and embedded models in Azure AI Studio**

1.  Open your browser, navigate to the address bar, and type or paste
    the following URL:
    +++[<u>https://oai.azure.com/</u>](https://oai.azure.com/)+++ then
    press the **Enter** button. Login using your **Azure** credentials.

> <img src="./media/image68.png" style="width:6.5in;height:3.59306in"
> alt="A screenshot of a computer Description automatically generated" />
>
> **Note**: If you are directed to the **Azure OpenAI Studio** home
> page, then skip steps from \#2 to \#4, else continue.

2.  In the **Microsoft Azure** window, enter your **Sign-in**
    credentials, and click on the **Next** button.

> <img src="./media/image69.png" style="width:4.18371in;height:4.0713in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Then, enter the password and click on the **Sign in** button**.**

> <img src="./media/image70.png" style="width:4.5in;height:3.56042in"
> alt="A screenshot of a login box Description automatically generated" />

4.  In **Stay signed in?** window, click on the **Yes** button.

> <img src="./media/image71.png" style="width:4.46806in;height:2.98617in"
> alt="Graphical user interface, application Description automatically generated" />

5.  On the **Welcome to Azure OpenAI Studio** dialog box, under the
    **Subscription** field, enter the subscription assigned to you, and
    in the **Resource** field, select the existing AOAI Resource name,
    and then click on the **Use resource** button.

<img src="./media/image72.png" style="width:5.80278in;height:4.97708in"
alt="A screenshot of a computer Description automatically generated" />

6.  Within few minutes **Azure OpenAI Studio** page will appear.

<img src="./media/image73.png" style="width:6.38037in;height:3.59169in"
alt="A screenshot of a computer Description automatically generated" />

7.  On the **Azure OpenAI Studio** homepage, click on **Create new
    deployment** button.

<img src="./media/image74.png" style="width:6.5in;height:6.00833in"
alt="A screenshot of a computer Description automatically generated" />

8.  In the **Deployments** page, click on +**Create new deployment**.

> <img src="./media/image75.png" style="width:4.24432in;height:3.35078in"
> alt="A screenshot of a computer Description automatically generated" />

9.  Enter the below details and click on the **Create** button. 

Model – Select **gpt-35-turbo**

Deployment type – **Standard**

Deployment name - +++**gpt-35-turbo**+++

> <img src="./media/image76.png" style="width:6.36667in;height:5.79167in"
> alt="A screenshot of a computer Description automatically generated" /> You
> will see a notification – **Successfully Created deployment** when the
> deployment is succeeded. (You can also view the notification by
> clicking on the bell icon beside **Azure AI \| Azure AI Studio)**.

<img src="./media/image77.png" style="width:5.47547in;height:2.07101in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 4: Create a Copilot app with custom data

### **Task 1: Create a chatbot with custom data**

1.  Select **Chat** to open the Chat playground.

<img src="./media/image78.png" style="width:2.20019in;height:4.30871in"
alt="A screenshot of a computer Description automatically generated" />

2.  In **Chat playground pane** , under the Assistant setup select **Add
    your data** and then select the **+Add data source** .

<img src="./media/image79.png" style="width:6.45056in;height:4.95043in"
alt="A screenshot of a chat Description automatically generated" />

3.  In the **Add data** page, under **Select or add data source** enter
    the following details and select **Next.**

| **Select data source** | **Select Azure Blob Storage(preview)** |
|----|----|
| **Subscription** | Select your Azure OpenAI subscription |
| **Select Azure Blob storage resource** | Select **azureopenaistorageXX** |
| **Select storage container** | Select **source** |
| **Select Azure AI Search resource** | Select **mysearchserviceXX** |
| **Enter the index name** | **copilot-index** |
| **Indexer schedule** | Once |

<img src="./media/image80.png"
style="width:7.05038in;height:5.52083in" />

***Note**: In case, you encounter an error – **Can‘t manage CORS on this
resource. Please select another storage resource**, then syn your VM
time, as mentioned in Lab \#1, Task \#1.*

4.  In the **Add data** page, on the **Data management** tab select
    **Keyword** under **Search type,** select the chunk size as
    **1024(default).**Then, click on **Next.**

<img src="./media/image81.png" style="width:6.5in;height:5.15833in" />

5.  In **Review and Finish** pane, review the details that you’ve
    entered, and click on **Save and close** button**.**

<img src="./media/image82.png"
style="width:6.49167in;height:5.05833in" />

6.  The data will be added in your Chat Playground. This will take
    approximately 4-5 minutes.

<img src="./media/image83.png" style="width:7.34184in;height:4.26627in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image84.png"
style="width:7.30329in;height:4.12917in" />

7.  In Azure AI Studio **Chat playground**, click on the V chevron
    button beside **Deploy to**, then navigate and click on **A new
    copilot in Copilot Studio(preview)**

***Note:** In case, you did not see **Deploy to** button on your VM,
then use Ctrl+- or Ctrl+minus keyboard shortcut to zoom out and decrease
the font size.*

<img src="./media/image85.png"
style="width:7.26416in;height:3.2875in" />

8.  **Deploy to a copilot in Copilot Studio(preview)** dialog box
    appears, then click on the **Continue in Copilot Studio** button.

<img src="./media/image86.png" style="width:5.525in;height:3.2in" />

9.  you are prompted to **Choose your country/region**, then click on
    the dropdown and select your region, then click on **Start free
    trail** button.

<img src="./media/image87.png" style="width:6.8231in;height:4.4875in" />

<img src="./media/image88.png"
style="width:6.49167in;height:4.36667in" />

10. In the **Create a copilot pane,** enter **Copilot name** as
    **TF-Copilot** and click on **Create** button.

<img src="./media/image89.png"
style="width:6.49167in;height:3.19167in" />

11. Wait for the deployment to complete. The deployment will take around
    **15-16** minutes.

<img src="./media/image90.png" style="width:7.32253in;height:4.10249in"
alt="A screenshot of a computer Description automatically generated" />

12. In the **New features in Copilot Studio** dialog box, click on the
    **Skip** button.

<img src="./media/image91.png" style="width:6.06667in;height:5.525in" />

<img src="./media/image92.png"
style="width:7.17609in;height:3.51444in" />

13. In the Copilot Studio, select **Topics** under the **Overview .**

<img src="./media/image93.png" style="width:6.5in;height:5in" />

14. In the Topics pane , select **System** and under the name filed
    select **Conversational boosting.**

<img src="./media/image94.png"
style="width:7.31108in;height:3.82917in" />

15. Select **Edit** under the **Data sources.**

<img src="./media/image95.png"
style="width:7.23542in;height:3.59449in" />

16. In the **Create generative answers properties** pane, under Azure
    OpenAI Services on your data select **Connection properties** .

<img src="./media/image96.png"
style="width:6.9375in;height:5.25649in" />

17. Under the **Data sources**, in the **Connect data** field enter
    +++**content+++** and click on the **plus(+)** symbol.

<img src="./media/image97.png" style="width:6.5in;height:5.54167in" />

18. In your **Copilot Studio \| TF-Copilot** window, navigate to the
    **Test copilot** pane enter the following text and click on the
    **Submit icon** as shown in the below image.

**TextCopy**

**<span class="mark">How do I get access to Azure OpenAI?</span>**

<img src="./media/image98.png" style="width:6.5in;height:6.88333in" />

19. Similarly, paste the following text in the text box and click on the
    **Send** icon.

**TextCopy**

**What is the expiry date of GPT-35-Turbo version 0301 and GPT-4 version
0314?**

<img src="./media/image99.png"
style="width:4.64583in;height:4.74931in" />

<img src="./media/image100.png"
style="width:7.03185in;height:4.37847in" />

### **Task 2: Delete the deployed models**

1.  In Azure OpenAI Studio, on the left pane, under the **Management**
    section, click on **Deployments**.

> <img src="./media/image101.png" style="width:2.60417in;height:4.28404in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select **gpt-35-turbo0301** deployment name and click on **Delete
    deployment**.

<img src="./media/image102.png"
style="width:7.24233in;height:3.71402in" />

3.  In the **Confirm delete** dialog box, click on the **Delete**
    button. You will see the notification – **Successfully Deleted
    deployment** (In case, you did not see the notification, then click
    on the bell icon beside **Azure AI \| Azure AI Studio**).

> <img src="./media/image103.png" style="width:3.43194in;height:1.81806in"
> alt="A screenshot of a computer Description automatically generated" />
>
> <img src="./media/image104.png"
> style="width:5.93194in;height:2.31042in" />

4.  In Azure OpenAI Studio, on the left pane, under the **Management**
    section, click on **Deployments**.

> <img src="./media/image101.png"
> style="width:2.95833in;height:4.86667in" />

5.  Select **text-embedding-ada-002** deployment name and click on
    **Delete deployment**.

> <img src="./media/image105.png"
> style="width:6.49167in;height:3.725in" />

6.  In the **Confirm delete** dialog box, click on the **Delete**
    button. You will see the notification – **Successfully Deleted
    deployment** (In case, you did not see the notification, then click
    on the bell icon beside **Cognitive Services \| Azure OpenAI
    Studio**).

> <img src="./media/image106.png"
> style="width:3.09167in;height:1.61667in" />

### **Task 3: Delete the Azure storage account, Azure cognitive search and Azure Web app**

1.  To delete the storage account, navigate to Azure portal home page,
    type **Resource groups** in the Azure portal search bar, navigate
    and click on **Resource groups** under **Services**.

> <img src="./media/image107.png" style="width:6.5in;height:4.22569in" />

2.  Click on the assigned resource group.

> <img src="./media/image108.png"
> style="width:6.49167in;height:2.98333in" />

3.  Carefully select storage account, Azure Cognitive Search, Azure web
    app, CosmosDB that you’ve created.

**Note**: Don’t select Azure OpenAI service.

> <img src="./media/image109.png"
> style="width:6.90129in;height:3.10038in" />

4.  In the Resource group page, navigate to
    <span class="mark">the</span> command bar and click on **Delete**.

**Important Note**: Don’t click on **Delete resource group**. If you
don’t see the **Delete** option in the command bar, then click on the
horizontal ellipsis.

<img src="./media/image110.png" style="width:7.23221in;height:3.35038in"
alt="A screenshot of a chat Description automatically generated" />

5.  In the **Delete Resources** pane that appears on the right side,
    enter the **delete** and click on **Delete** button.

> <img src="./media/image111.png"
> style="width:5.43194in;height:7.12847in" />

6.  On **Delete confirmation** dialog box, click on D**elete** button.

> <img src="./media/image112.png"
> style="width:5.06711in;height:5.10044in" />

7.  Click on the bell icon, you’ll see the notification – **Executed
    delete command on 4 selected items.**

> <img src="./media/image113.png"
> style="width:3.625in;height:1.15833in" />
>
> **Summary**
>
> You've created a storage account, container, and Azure cognitive
> service in Azure portal, then you've deployed gpt-3-turbo model in
> Azure AI Studio. You’ve added data in Chat Playground and tested the
> Assistant setup by sending queries in a chat session. Then, you've
> launched a new app and started conversation with the chatbot. You've
> deleted the gpt-3-turbo model, Azure storage account, cognitive search
> service, and the new web app to effectively and efficiently manage the
> Azure OpenAI resources.
