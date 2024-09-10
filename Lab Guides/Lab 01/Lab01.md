# Lab 01: Creating and using Copilot from Copilot Studio for managing a Real Estate Application

**Lab Duration** -- 120 minutes

**Introduction**

Contoso Real Estate specializes in the sale and management of both
commercial and residential properties. Currently, customer information
is efficiently stored within their Dataverse instance, allowing for
streamlined data management. However, the booking process presents a
significant challenge.

At present, customers can only request bookings via phone, leading to an
overwhelmed phone line and long wait times. This situation not only
frustrates customers but also risks losing potential business as many
are unable to connect with the office to request services.

To address these issues, Contoso Real Estate is committed to developing
a comprehensive digital solution. This solution will empower customers
to easily access information about the booking process and submit
booking requests online.

**Objectives**

-   Build a standalone copilot for Contoso Real Estates from Copilot
    Studio (that will allow customers to discover information about the
    real estate booking process and create booking requests for the
    office to review.)

-   Create Topics to set up the logic of the bookings.

-   Create the Dataverse tables required for the bookings.

-   Publish the copilot.

-   Configure the Dynamics 365 workspace and connect the copilot to it.

-   Create a web page using Power Pages and integrate the copilot
    created from Copilot Studio in it.

-   Test the escalation to live agent functionality from the web page.

## Exercise 1: Setting up the Dynamics 365 Customer Service

### Task 1: Sign up for Dynamics 365 Customer Service trial

1.  Login to
    +++<https://dynamics.microsoft.com/en-us/customer-service/overview/>+++
    and click on **Try for free**

![A person in a vest and glasses Description automatically
generated](./media/media/image1.png){width="6.268055555555556in"
height="3.3159722222222223in"}

2.  Enter your Tenant id and click on **Start your free trial**.

![A screenshot of a computer Description automatically
generated](./media/media/image2.png){width="6.268055555555556in"
height="3.801388888888889in"}

3.  Enter the region as **United States**, enter your **Phone number**
    and click on **Submit**.

![A screenshot of a computer Description automatically
generated](./media/media/image3.png){width="4.180769903762029in"
height="5.062760279965004in"}

4.  The **Dynamics 365 Customer Service workspace** opens.

![A screenshot of a computer Description automatically
generated](./media/media/image4.png){width="6.268055555555556in"
height="3.464583333333333in"}

5.  Click on Customer Service workspace to open the **Apps**.

![A screenshot of a computer Description automatically
generated](./media/media/image5.png){width="5.722516404199475in"
height="4.68079615048119in"}

6.  Click on **Customer Service admin center** to open it.

![A screenshot of a computer Description automatically
generated](./media/media/image6.png){width="6.268055555555556in"
height="3.4347222222222222in"}

7.  Select **Routing** under **Customer Support** group.

![A screenshot of a computer Description automatically
generated](./media/media/image7.png){width="6.268055555555556in"
height="2.9680555555555554in"}

8.  On the **Routing** page, under **Record routing**, click **Manage**
    next to **Turn on Unified Routing for Records**.

![A screenshot of a computer Description automatically
generated](./media/media/image8.png){width="6.268055555555556in"
height="2.41875in"}

9.  On the **Service Configuration Settings** page under **Unified
    routing**, make sure that the **Turn on unified routing** toggle is
    set to **Yes**.

**Note**: The **Turn on unified routing** toggle is set to **Yes** only
if consent is already provided by the tenant administrator.

10. Click **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image9.png){width="6.268055555555556in"
height="3.963888888888889in"}

### **Task 2: Manage a user in Omnichannel for Customer Service**

1.  In **Dynamics 365 Customer Service admin center**, in the site map,
    select **User management** under **Customer support** group.

2.  On the **User management** page, select **Manage** next
    to **Users**.

![A screenshot of a computer Description automatically
generated](./media/media/image10.png){width="6.268055555555556in"
height="2.377083333333333in"}

3.  Click the dropdown next to **Enabled Users** and select
    **Omnichannel Users**.

![A screenshot of a computer Description automatically
generated](./media/media/image11.png){width="6.268055555555556in"
height="5.7972222222222225in"}

4.  On the **Omnichannel Users** page, select a user **MOD
    Administrator** in the list.

![A screenshot of a computer Description automatically
generated](./media/media/image12.png){width="6.268055555555556in"
height="2.9090277777777778in"}

5.  On the **MOD Administrator** page, select the **Omnichannel** tab.

![A screenshot of a computer Description automatically
generated](./media/media/image13.png){width="6.268055555555556in"
height="3.4375in"}

6.  Specify the following in the user page.

  -----------------------------------------------------------------------
  **Setting**                                    **Value**
  ---------------------------------------------- ------------------------
  Capacity                                       100

  Default Presence                               available
  -----------------------------------------------------------------------

![A screenshot of a computer Description automatically
generated](./media/media/image14.png){width="6.268055555555556in"
height="2.56875in"}

7.  Select **Save and close**.

![A screenshot of a computer Description automatically
generated](./media/media/image15.png){width="6.268055555555556in"
height="2.5527777777777776in"}

### Task 3: Configure Omnichannel Power Virtual Agent Extension

1.  Open the link,
    +++<https://appsource.microsoft.com/en-cy/product/dynamics-365/mscrm.omnichannelpvaextension?tab=Overview&ref=dynamicsforcrm.com>+++
    and click on Get it now in the Omnichannel Power Virtual Agent
    Extension page.

![A screenshot of a computer Description automatically
generated](./media/media/image16.png){width="6.268055555555556in"
height="2.990972222222222in"}

![A screenshot of a computer Description automatically
generated](./media/media/image17.png){width="4.229384295713036in"
height="4.521065179352581in"}

2.  Select the **CustomerService Trial** under **Select an environment**
    and click on **Install**.

![A screenshot of a computer Description automatically
generated](./media/media/image18.png){width="4.771078302712161in"
height="5.05581583552056in"}

3.  In the Dynamics 365 apps page, click on the entries that shows
    **Update available**, **select** the **check box** to agree to the
    terms and click on **Update**.

Make sure to do this for **all** the entries with **Update available**
as the Status.

![A screenshot of a computer Description automatically
generated](./media/media/image19.png){width="6.268055555555556in"
height="3.5805555555555557in"}

![A screenshot of a computer Description automatically
generated](./media/media/image20.png){width="4.8127471566054245in"
height="5.034981408573929in"}

### Task 4: Configure search settings in the Power Platform admin center

1.  Login to +++<https://admin.powerplatform.microsoft.com/>+++ using
    your tenant details. Select **Environments** -\> **CustomerService
    Trial**.

![A screenshot of a computer Description automatically
generated](./media/media/image21.png){width="5.98669072615923in"
height="3.572380796150481in"}

2.  Select the drop down next to **Resource** (in the top pane) and
    select **Dynamics 365 apps**.

![A screenshot of a computer Description automatically
generated](./media/media/image22.png){width="6.268055555555556in"
height="3.134027777777778in"}

3.  Make sure that **Omnichannel for Customer Service** is
    **Installed**.

![A screenshot of a computer Description automatically
generated](./media/media/image23.png){width="6.268055555555556in"
height="3.8513888888888888in"}

4.  Navigate back to the **Environments -\> CustomerService** **Trial**
    page in the admin center. Select **Settings** from the top pane.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image24.png){width="6.268055555555556in"
> height="3.5791666666666666in"}

5.  Select **Product** -\> **Features**.

![A screenshot of a computer Description automatically
generated](./media/media/image25.png){width="6.268055555555556in"
height="4.125694444444444in"}

6.  Toggle **Dataverse Search** and **Single table search** option to
    **ON.**

![A screenshot of a computer Description automatically
generated](./media/media/image26.png){width="6.268055555555556in"
height="3.676388888888889in"}

Scroll down and click on the **Save** button at the bottom right.

![A screenshot of a computer Description automatically
generated](./media/media/image27.png){width="6.268055555555556in"
height="4.300694444444445in"}

## Exercise 2: Setting up Power Apps and Dataverse

### Task 1: Sign up for the Microsoft Power Apps Developer Plan

1.  Navigate to +++https://powerapps.microsoft.com/free/+++ and select
    **Start free**.

![A screenshot of a computer Description automatically
generated](./media/media/image28.png){width="6.268055555555556in"
height="2.975in"}

2.  Under **Let\'s get started**, enter your **email address** in the
    text box, check the agreement box and select **Start free**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image29.png){width="6.268055555555556in"
> height="3.84375in"}

3.  If you see a prompt that you have an existing account with
    Microsoft. Select **Sign in**. Enter your password.

4.  If prompted, Select **Yes** to stay signed in.

5.  Click on **Environment** in the top-right corner of the screen and
    select **CustomerService Trial**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image30.png){width="6.268055555555556in"
> height="1.8041666666666667in"}

### Task 2: Create a solution

1.  From the Power Apps Maker
    Portal(+++<https://make.powerapps.com/>+++), select **Solutions**
    form the left pane.

![A screenshot of a computer Description automatically
generated](./media/media/image31.png){width="6.268055555555556in"
height="2.5680555555555555in"}

2.  Click on **+ New solution**.

![A screenshot of a search engine Description automatically
generated](./media/media/image32.png){width="6.268055555555556in"
height="3.7847222222222223in"}

3.  Enter +++**Bookings**+++ for the Display name and click on **+ New
    publisher**.

![A screenshot of a computer Description automatically
generated](./media/media/image33.png){width="3.312670603674541in"
height="4.312722003499562in"}

4.  Enter the below details and then click on **Save**.

  -----------------------------------------------------------------------
  **Property**                        **Value**
  ----------------------------------- -----------------------------------
  **Display name**                    +++Contoso+++

  **Name**                            +++contoso+++

  **Prefix**                          +++contoso+++
  -----------------------------------------------------------------------

![A screenshot of a computer Description automatically
generated](./media/media/image34.png){width="3.5626826334208226in"
height="4.625237314085739in"}

5.  Select **Contoso (contoso)** under Publisher and then click on
    **Create**.

![A screenshot of a computer Description automatically
generated](./media/media/image35.png){width="2.3334536307961504in"
height="4.625237314085739in"}

6.  Select **Back to solutions** in the top-left of the screen.

![A screenshot of a computer Description automatically
generated](./media/media/image36.png){width="6.268055555555556in"
height="2.425in"}

### Task 3: Set the preferred solution

1.  Under Solutions in the Maker portal, select **Manage** for **Set
    your preferred solution**.

![A screenshot of a computer Description automatically
generated](./media/media/image37.png){width="6.268055555555556in"
height="1.9986111111111111in"}

2.  Select **Bookings (contoso)** under **Unless otherwise specified,
    save my changes in** and select **Apply**.

![A screenshot of a computer screen Description automatically
generated](./media/media/image38.png){width="5.687791994750656in"
height="2.743196631671041in"}

![A screenshot of a computer Description automatically
generated](./media/media/image39.png){width="6.268055555555556in"
height="3.7291666666666665in"}

### Task 4: Create the Real Estate Properties custom table

Follow these steps to create a new custom table in Dataverse for Real
Estate Properties.

1.  From the left navigation pane, select **Tables**, select **New
    table**, and then select **Add columns and data**.

![A screenshot of a computer Description automatically
generated](./media/media/image40.png){width="6.268055555555556in"
height="3.9875in"}

2.  Rename the table from **New Table** to +++**Real Estate
    Property**+++.

![A screenshot of a computer Description automatically
generated](./media/media/image41.png){width="4.937753718285214in"
height="4.646071741032371in"}

3.  Change the name of the column called **New Column** to +++**Property
    Name**+++.

![A screenshot of a computer Description automatically
generated](./media/media/image42.png){width="6.268055555555556in"
height="4.293055555555555in"}

4.  Select the **+ New column** button to add a new column in the
    columns and data pane. In the New column pane, enter the following
    values, and then select **Save**.

    -   Display name: +++**Asking Price**+++

    -   Data type: Currency

> ![A screenshot of a table Description automatically
> generated](./media/media/image43.png){width="5.05581583552056in"
> height="4.500230752405949in"}

5.  Add the following two columns.

  -----------------------------------------------------------------------
  **Display name**                     **Data type**
  ------------------------------------ ----------------------------------
  +++Street+++                         Single line of text (this value is
                                       the default)

  +++City+++                           Single line of text (this value is
                                       the default)
  -----------------------------------------------------------------------

6.  Add another column with the below values

    -   **Display name**: +++Bedrooms+++

    -   **Data type**: Choice

Create the choice values:

-   Under **Choices** you see two entry fields
    titled **Label** and **Value**. Enter **1** under the label. Power
    Apps assigns a value automatically but you can change the value
    to **1**.

<!-- -->

-   Select **+ New choice** and make **2** the new entry for Label
    and **2** for Value.

<!-- -->

-   Select **+ New choice** and make **3** the new entry for Label
    and **3** for Value.

<!-- -->

-   Select **+ New choice** and make **4** the new entry for Label
    and **4** for Value.

<!-- -->

-   Select **+ New choice** and make **5** the new entry for Label
    and **5** for Value.

<!-- -->

-   Select **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image44.png){width="3.2640562117235348in"
height="4.583568460192476in"}

7.  Select the **+ New column** button to add a new column in the
    columns and data pane.

8.  In the New column pane, enter the following values, and then
    select **Save**:

    -   **Display name**: +++Bathrooms+++

    -   **Data type**: Choice

Create the choice values

-   Under **Choices** you see two entry fields
    titled **Label** and **Value**. Enter **1** under the label. Power
    Apps assigns a value automatically but you can change it to **1**.

-   Select **+ New choice** and make **2** the new entry for Label
    and **2** for Value.

-   Select **+ New choice** and make **3** the new entry for Label
    and **3** for Value.

-   Select **+ New choice** and make **4** the new entry for Label
    and **4** for Value.

-   Select **+ New choice** and make **5** the new entry for Label
    and **5** for Value.

-   Select **Save**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image45.png){width="3.791861329833771in"
> height="4.625237314085739in"}

9.  Add another column by selecting the **+ New column** button again in
    the columns and data pane.

In the New column pane, enter the following values, and then
select **Save**:

-   **Display name**: +++**Client**+++

-   **Data type**: Lookup -\> Lookup

-   **Related Table**: Contact

> ![A screenshot of a computer Description automatically
> generated](./media/media/image46.png){width="4.326610892388452in"
> height="4.618292869641295in"}

10. At the bottom of the pane, select **Create**.

![A screenshot of a computer Description automatically
generated](./media/media/image47.png){width="6.268055555555556in"
height="3.1555555555555554in"}

11. Once the table is created, under **Real Estate Property columns and
    data**, enter the following test data:

    -   Property Name: +++**1100 High Villas**+++

    -   Asking Price: +++**250,000**+++

    -   Bathrooms: **3**

    -   Bedrooms: **2**

    -   City: +++**Redmond**+++

    -   Street: +++**Main Avenue**+++

    -   Client: **Select any contact**

> ![A screenshot of a computer Description automatically
> generated](./media/media/image48.png){width="6.268055555555556in"
> height="3.3430555555555554in"}

### Task 5: Create the Bookings table

Follow these steps to create a new custom table in Dataverse for Real
Estate Property Bookings.

1.  From the left navigation pane, select **Tables**, select **New
    table**, and then select **Add columns and data**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image49.png){width="5.15998687664042in"
> height="4.666906167979002in"}

2.  Rename the table as +++**Booking Request**+++.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image50.png){width="4.396059711286089in"
> height="4.604402887139107in"}

3.  Change the name of the column called **New Column** to +++**Booking
    Name**+++.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image51.png){width="6.268055555555556in"
> height="4.272916666666666in"}

4.  Create the following columns with the name and data type as
    specified in the table below. Select **Save**.

> Display name -- +++**Property**+++
>
> Data type -- **Lookup** -\> **Lookup**
>
> Related Table -- **Real Estate Property**
>
> ![A screenshot of a computer Description automatically
> generated](./media/media/image52.png){width="6.268055555555556in"
> height="4.382638888888889in"}
>
> Display name -- +++**Viewer Name**+++
>
> Data type -- **Single line of text**
>
> Display name -- +++**Viewer Email**+++
>
> Data type -- **Single line of text**
>
> Format -- **Email**
>
> Display name -- +++**Booking Date**+++
>
> Data type -- **Date and time**
>
> Display name -- +++**Notes**+++
>
> Data type -- **Multiple lines of text**
>
> ![A screenshot of a computer Description automatically
> generated](./media/media/image53.png){width="5.972529527559055in"
> height="4.583568460192476in"}
>
> ![A screenshot of a computer Description automatically
> generated](./media/media/image54.png){width="3.5140693350831147in"
> height="4.479397419072616in"}
>
> Display name -- +++**Decision**+++
>
> Data type -- **Choice**

-   Label -- +++**Undecided**+++

-   Value -- 1

-   Label -- +++**Accepted**+++

-   Value -- 2

-   Label -- +++**Declined**+++

-   Value -- 3

> Designate **Undecided** as the **Default choice**.

![A screenshot of a computer Description automatically
generated](./media/media/image55.png){width="2.2709503499562556in"
height="4.646071741032371in"}

5.  At the bottom of the pane, select **Create**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image56.png){width="6.268055555555556in"
> height="3.2083333333333335in"}

6.  Ensure that the table is created successfully.

## Exercise 3: Working with Copilot Studio

### Task 1: Sign up for Copilot Studio trial

1.  Open the url +++https://copilotstudio.microsoft.com/+++.

2.  Leave the **Choose your country/region** with the **default** value
    and click on **Get Started**.

![A person sitting at a computer Description automatically
generated](./media/media/image57.png){width="6.268055555555556in"
height="4.521527777777778in"}

3.  Click on **Environments** on the top left and select
    **CustomerService Trial**.

![A screenshot of a computer Description automatically
generated](./media/media/image58.png){width="6.268055555555556in"
height="1.9520833333333334in"}

4.  Select **Skip** if you get a Welcome to Copilot Studio! Prompt**.**

![A screenshot of a computer Description automatically
generated](./media/media/image59.png){width="5.305827865266842in"
height="4.597458442694663in"}

### Task 2: Create the Real Estate Booking Service Copilot

1.  Select **Create** from the left navigation pane and select the **New
    copilot** tile.

![A screenshot of a computer Description automatically
generated](./media/media/image60.png){width="6.268055555555556in"
height="2.714583333333333in"}

2.  Select **Skip to configure**.

![A screenshot of a computer Description automatically
generated](./media/media/image61.png){width="6.268055555555556in"
height="1.7215277777777778in"}

3.  Fill in the below details.

-   Name - +++**Real Estate Booking Service**+++

-   Description - +++**Create bookings for real estate properties**+++

-   Instructions - +++**Create a copilot for topics relating to creating
    bookings for real estate properties+++**

-   Language **--** Select **English**

> ![A screenshot of a computer Description automatically
> generated](./media/media/image62.png){width="6.017560148731409in"
> height="2.8934426946631673in"}

4.  Select the three dots next to the Create button in the top-right of
    the screen and select **Edit advanced settings**.

![A screenshot of a computer Description automatically
generated](./media/media/image63.png){width="3.8474201662292216in"
height="3.0834919072615925in"}

5.  Select the **Bookings** solution and select **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image64.png){width="5.368331146106737in"
height="3.3751738845144357in"}

6.  In the top-right of the screen, select **Create**.

![A screenshot of a computer Description automatically
generated](./media/media/image65.png){width="6.268055555555556in"
height="2.089583333333333in"}

7.  Once the copilot is created, in the Test your copilot pane, enter
    **How do I make a booking?** and click **Enter** and observe the
    response.

![A screenshot of a computer Description automatically
generated](./media/media/image66.png){width="6.268055555555556in"
height="4.432638888888889in"}

### Task 3: Configure Security

1.  Select **Settings** in the top-right of the screen.

![A screenshot of a chat Description automatically
generated](./media/media/image67.png){width="6.268055555555556in"
height="2.563888888888889in"}

2.  Select the **Security** tab and then select
    the **Authentication** tile.

![A screenshot of a computer Description automatically
generated](./media/media/image68.png){width="6.268055555555556in"
height="2.9763888888888888in"}

3.  Select **No authentication** and click on **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image69.png){width="6.268055555555556in"
height="3.173611111111111in"}

4.  Select **Save** in the **Save this configuration** prompt.

![A screenshot of a computer Description automatically
generated](./media/media/image70.png){width="5.271104549431321in"
height="3.583517060367454in"}

5.  Once the Authentication settings are saved, click on the **Close**
    option to close the **Settings** pane.

![A screenshot of a computer Description automatically
generated](./media/media/image71.png){width="6.268055555555556in"
height="3.0875in"}

### Task 4: Remove topics

Sample topics are included with new copilots. Remove these sample
topics. Disable system topics that you don\'t require.

1.  Select the **Topics** tab from the top menu of the Copilot Overview
    page.

![A screenshot of a computer Description automatically
generated](./media/media/image72.png){width="4.729409448818898in"
height="3.7501924759405076in"}

2.  You will land in the **Custom** Topics page.

3.  Select the **three dots** next to the **Lesson 1** topic and select
    **Delete**.

![A screenshot of a computer Description automatically
generated](./media/media/image73.png){width="4.833581583552056in"
height="4.639127296587927in"}

4.  Select **Save** in the confirmation window.

![A white background with black text Description automatically
generated](./media/media/image74.png){width="5.333607830271216in"
height="1.375071084864392in"}

5.  Repeat the delete for Lesson 2 and Lesson 3.

![A screenshot of a computer Description automatically
generated](./media/media/image75.png){width="4.937753718285214in"
height="4.625237314085739in"}

![A screenshot of a computer Description automatically
generated](./media/media/image76.png){width="4.604402887139107in"
height="4.625237314085739in"}

6.  Select the **System** tab. Toggle **Enabled** to **Off** for the
    **Sign in** topic.

![A screenshot of a computer Description automatically
generated](./media/media/image77.png){width="5.847522965879265in"
height="4.639127296587927in"}

### Task 5: Publish and test the copilot

1.  Select **Publish** and select **Publish** again.

![A screenshot of a computer Description automatically
generated](./media/media/image78.png){width="6.268055555555556in"
height="1.854861111111111in"}

2.  Select **Publish** in the **Publish this copilot** dialog.

![A screenshot of a computer Description automatically
generated](./media/media/image79.png){width="5.764185258092739in"
height="1.6598075240594925in"}

### Task 6: Demo Website

The Demo website allows users without a license to test your copilot.
You can provide them with the URL to the demo website.

1.  Select the **three dots** next to the **Settings** button in the
    top-right of the screen and select **Go to demo website**.

![A screenshot of a web page Description automatically
generated](./media/media/image80.png){width="6.268055555555556in"
height="1.65625in"}

2.  In the **Type your message** text box, enter **What information is
    needed to book a viewing for a real estate property?** and observe
    the response from the copilot.

![A screenshot of a chatbot Description automatically
generated](./media/media/image81.png){width="6.268055555555556in"
height="3.160416666666667in"}

## Exercise 4: Create and manage topics using Copilot

### Task 1: Create a topic using Copilot

Topics can be created and edited using natural language.

1.  Select your copilot, **Real Estate Booking Service** in the Copilot
    pane on the left-hand side of the Copilot Studio.

![A screenshot of a web page Description automatically
generated](./media/media/image82.png){width="6.268055555555556in"
height="1.7805555555555554in"}

2.  Select the **Topics** tab. Select **Add a topic** and select
    **Create from description with Copilot**.

![A screenshot of a computer Description automatically
generated](./media/media/image83.png){width="6.268055555555556in"
height="2.6590277777777778in"}

3.  Enter the below details and click on **Create**.

-   Name your topic - +++**Customer Details**+++

-   Create a topic to\... - +++**Ask the customer for their name and
    email address**+++

> ![A screenshot of a computer Description automatically
> generated](./media/media/image84.png){width="6.112945100612423in"
> height="3.17499343832021in"}

4.  A new topic displays with the generated trigger phrases and question
    nodes.

5.  Select **Save**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image85.png){width="6.268055555555556in"
> height="3.9055555555555554in"}

### Task 2: Update nodes with natural language

1.  If the **Edit with copilot** pane isn\'t shown on the right-hand
    side of the screen, select the **Copilot** icon in the upper part of
    the authoring canvas.

2.  Select the second question node, **What is your email address?**

3.  In the **Edit with Copilot** panel, in the **What do you want to
    do?** field, enter the following text:

> +++**Update the message in this question node to say thank you to the
> Name variable from the previous node and then proceed to ask the email
> address question**+++

4.  Select **Update**.

![A screenshot of a computer Description automatically
generated](./media/media/image86.png){width="6.268055555555556in"
height="4.263194444444444in"}

5.  Select **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image87.png){width="6.268055555555556in"
height="2.113888888888889in"}

### Task 3: Add nodes with natural language

In addition to adding updating existing nodes, you can use Copilot to
add new ones.

1.  Make sure that no node is selected by clicking in the empty space
    around the nodes.

2.  In the **Edit with Copilot** panel, in the **What do you want to
    do?** field, enter the following text:

+++**Summarize the information collected in an adaptive card**+++

3.  Select **Update**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image88.png){width="6.268055555555556in"
> height="3.127083333333333in"}

4.  A message node with an Adaptive Card is added to the end of the
    topic.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image89.png){width="4.354390857392826in"
> height="4.5418996062992125in"}

5.  Select the Adaptive Card. The Adaptive Card properties should appear
    on the right of the screen.

6.  Copy the below content and paste it as the Adaptive card formula if
    it is not already populated properly.

> **{**
>
> **type: \"AdaptiveCard\",**
>
> **body:**
>
> **\[**
>
> **{**
>
> **type: \"TextBlock\",**
>
> **size: \"Medium\",**
>
> **weight: \"Bolder\",**
>
> **text: \"Summary\"**
>
> **},**
>
> **{**
>
> **type: \"FactSet\",**
>
> **facts:**
>
> **\[**
>
> **{**
>
> **title: \"Full Name\",**
>
> **value: Text(Topic.Name)**
>
> **},**
>
> **{**
>
> **title: \"Email Address\",**
>
> **value: Text(Topic.EmailAddress)**
>
> **}**
>
> **\]**
>
> **},**
>
> **{**
>
> **type: \"TextBlock\",**
>
> **text: \"Thank you for providing the information.\"**
>
> **}**
>
> **\]**
>
> **}**
>
> Your card content should now look like the one in the below image.
>
> ![A screenshot of a computer program Description automatically
> generated](./media/media/image90.png){width="5.729460848643919in"
> height="5.875301837270341in"}

7.  Open the **Edit with Copilot** icon.

![](./media/media/image91.png){width="4.4168941382327205in"
height="4.583568460192476in"}

8.  Make sure that no node is selected by clicking in the empty space
    around the nodes.

9.  In the **What do you want to do?** field, enter the following text
    and then select **Update.**

> **Add a new multiple-choice question to prompt the user if the details
> are correct with two options Yes or No**

![A screenshot of a computer Description automatically
generated](./media/media/image92.png){width="5.291938976377953in"
height="4.514120734908136in"}

10. A new question node is added to the end of the topic with options
    for the user to select.

11. Select **Save**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image93.png){width="6.268055555555556in"
> height="4.116666666666666in"}

### Task 4: Configure the scope of the variables

1.  Select **Variables** to open the Variables pane.

![A screenshot of a computer Description automatically
generated](./media/media/image94.png){width="6.1461493875765525in"
height="3.0626574803149604in"}

2.  Select the right-hand check boxes for the topic variables and click
    on **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image95.png){width="4.646071741032371in"
height="4.604402887139107in"}

## Exercise 5: Create and manage topics manually

### Task 1: Create a topic from blank

1.  Select the **Topics** tab.

2.  Select **Add a topic** and select **From blank**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image96.png){width="6.268055555555556in"
> height="3.4652777777777777in"}

3.  Select **Details** to open the Topic details dialog.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image97.png){width="5.958639545056868in"
> height="4.014095581802275in"}

4.  Fill in the below details and click on **Save**.

-   **Name** - +++Book a Real Estate Showing+++

-   **Display Name --** +++**Book**+++

-   **Description**  - +++Select the property and requested date and
    create a booking request+++

![A screenshot of a computer Description automatically
generated](./media/media/image98.png){width="6.268055555555556in"
height="3.6381944444444443in"}

5.  Select **Details** to close the Topic details dialog.

![A screenshot of a computer Description automatically
generated](./media/media/image99.png){width="6.268055555555556in"
height="2.990972222222222in"}

### Task 2: Add trigger phrases

1.  Select **Edit** under **Phrases** in the **Trigger**. Enter +++**I
    want to book a real estate showing**+++ under **Add Phrases** and
    select the **+** icon.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image100.png){width="5.687791994750656in"
> height="4.43078302712161in"}

2.  Enter the below phrases one by one.

-   +++**Schedule a real estate showing**+++

-   +++**Arrange the viewing for a real estate property**+++

-   +++**Set up an appointment to view a house**+++

-   +++**Plan a property viewing**+++

3.  Once all the phrases are added, select **Save**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image101.png){width="6.268055555555556in"
> height="4.027083333333334in"}

### Task 3: Add a message node

1.  Select the **+** icon under the Trigger node and select **Send a
    message**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image102.png){width="5.646123140857393in"
> height="4.576624015748031in"}

2.  In the **Enter a message** field, enter the following text:

+++Hi, I can help you with booking a real estate property showing.+++

3.  Select **Save**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image103.png){width="6.268055555555556in"
> height="3.7243055555555555in"}

### Task 4: Add a Topic management node

1.  Select the the **+** icon under the send a message node and
    select **Topic management -\> Go to another topic**.

![A screenshot of a chat Description automatically
generated](./media/media/image104.png){width="5.291938976377953in"
height="4.625237314085739in"}

2.  Select the **Customer Details** topic.

![A screenshot of a computer Description automatically
generated](./media/media/image105.png){width="5.604454286964129in"
height="4.646071741032371in"}

3.  Select **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image106.png){width="6.268055555555556in"
height="3.68125in"}

### Task 5: Add condition node 

1.  Select the **+** icon under the topic management node and
    select **Add a condition**.

![A screenshot of a computer Description automatically
generated](./media/media/image107.png){width="4.458562992125985in"
height="4.021040026246719in"}

2.  Select **DetailsCorrect** for variable.

![](./media/media/image108.png){width="6.268055555555556in"
height="3.90625in"}

3.  Select the **Condition** as **is equal to**

4.  Select the **value** as **Yes**.

![A screenshot of a computer Description automatically
generated](./media/media/image109.png){width="6.268055555555556in"
height="3.701388888888889in"}

5.  Select **Save**.

![A screenshot of a computer Description automatically
generated](./media/media/image110.png){width="6.268055555555556in"
height="3.761111111111111in"}

### Task 6: Add question nodes

1.  Select the **+** icon under the left-hand condition node and
    select **Ask a question**. Fill in the below details and click on
    **Save**.

-   Enter a message  - +++Which property do you want to see?+++

-   **Identify** - Select **User\'s entire response**.

-   **Save user response as** -
    Enter +++**PropertyName**+++ for **Variable name**

![A screenshot of a computer Description automatically
generated](./media/media/image111.png){width="6.268055555555556in"
height="3.921527777777778in"}

2.  Select the the **+** icon under the question node and select **Ask a
    question**. Fill in the below details and click on **Save.**

-   **Enter a message** - +++What date and time do you want to see the
    property?+++

-   Identify - Select **Date and Time**

-   **Save user response as** - Enter +++**DateTime**+++ for **Variable
    name**

> ![A screenshot of a computer Description automatically
> generated](./media/media/image112.png){width="6.268055555555556in"
> height="4.088888888888889in"}

### Task 7: Test the copilot

1.  Select the **Test** button in the top-right of the screen to open
    the testing panel. Select the **three dots** at the top of the
    testing panel in the top-right of the screen. Select **Track between
    topics**.

> ![A screenshot of a computer Description automatically
> generated](./media/media/image113.png){width="5.855919728783902in"
> height="4.059438976377953in"}

2.  When the **Conversation Start** message appears, your copilot starts
    a conversation.

3.  In response, enter a trigger phrase for the topic that you created:

+++I want to book a real estate showing+++

4.  The copilot responds with the \"**What is your name?**\" question.

5.  Enter your name.

> ![A screenshot of a chat Description automatically
> generated](./media/media/image114.png){width="2.4723490813648294in"
> height="4.437728565179353in"}

6.  Then enter your email when it prompts for the email. After you enter
    the details, an Adaptive Card displays the information that you
    entered, a question asking if the information is correct, and
    options to select **Yes** or **No**. Select **Yes**.

> ![](./media/media/image115.png){width="2.6251345144356955in"
> height="4.604402887139107in"}

7.  Enter +++555 Oak Lane, Denver, CO 80203+++ to the **Which property
    to you want to see?** prompt.

8.  Enter **Tomorrow 10:00 AM** to the **What date and time do you want
    to see the property?** prompt.

![A screenshot of a chat Description automatically
generated](./media/media/image116.png){width="2.5001279527559057in"
height="4.666906167979002in"}

## Exercise 6: Connect the copilot to Dynamics 365 Customer Service and configure the Escalate topic

### Task 1: Configure the Escalate topic

1.  Select the **Topics** tab and then select the **System** tab. Select
    the **Escalate** topic.

![A screenshot of a computer Description automatically
generated](./media/media/image117.png){width="6.268055555555556in"
height="4.153472222222222in"}

2.  Select the message node of the topic and replace the existing
    content with, +++You will be transferred to a live agent shortly+++

![A screenshot of a computer Description automatically
generated](./media/media/image118.png){width="6.268055555555556in"
height="3.74375in"}

3.  Click on the + symbol to add a node next to the Message node.

4.  Select **Topic management** -\> **Transfer conversation**.

![A screenshot of a computer Description automatically
generated](./media/media/image119.png){width="6.268055555555556in"
height="4.336111111111111in"}

5.  Give a message +++The customer wants to talk to a live agent+++ in
    the Transfer conversation node.

![A screenshot of a chat Description automatically
generated](./media/media/image120.png){width="6.268055555555556in"
height="4.602083333333334in"}

6.  **Save** the Topic.

![A screenshot of a computer Description automatically
generated](./media/media/image121.png){width="6.268055555555556in"
height="2.2729166666666667in"}

7.  **Publish** the copilot.

![A screenshot of a computer Description automatically
generated](./media/media/image122.png){width="6.268055555555556in"
height="2.7465277777777777in"}

### Task 2: Connect the copilot to Dynamics 365 Customer Service

1.  Click on the **Overview** option to arrive at the Overview page of
    the copilot.

![A screenshot of a computer Description automatically
generated](./media/media/image123.png){width="6.268055555555556in"
height="1.4381944444444446in"}

2.  From the copilot page top menu, click on **Channels** (If the
    Channels is not visible, click on the +1 to view the **Channels**
    option)

![A screenshot of a computer Description automatically
generated](./media/media/image124.png){width="6.268055555555556in"
height="4.430555555555555in"}

3.  Select **Dynamics 365 Customer Service** from the Customer
    engagement hub pane.

![A screenshot of a computer Description automatically
generated](./media/media/image125.png){width="6.268055555555556in"
height="4.405555555555556in"}

4.  On the Dynamics 365 Customer Service page, click on **Connect**.

![A screenshot of a message Description automatically
generated](./media/media/image126.png){width="3.521013779527559in"
height="4.625237314085739in"}

5.  Once you get a **successfully connected** message, click on
    **Close**.

![A screenshot of a computer Description automatically
generated](./media/media/image127.png){width="3.458511592300962in"
height="4.666906167979002in"}

## Exercise 7: Create workstream and channel in Dynamics 365 admin center

### Task 1: Configure workstream 

1.  Login to +++<https://www.office.com>+++ using your admin tenant id.

2.  Select **Apps** from the left pane.

![A screenshot of a computer Description automatically
generated](./media/media/image128.png){width="6.268055555555556in"
height="3.640972222222222in"}

3.  From the list of Apps listed, select **Customer Service admin
    center**.

![A screenshot of a computer Description automatically
generated](./media/media/image129.png){width="6.268055555555556in"
height="2.152083333333333in"}

4.  From the admin center page, select **Workstreams** from the left
    pane and then select the **+ New workstream** option.

![A screenshot of a computer Description automatically
generated](./media/media/image130.png){width="5.014146981627297in"
height="4.5418996062992125in"}

5.  Fill in the below details, scroll down and click on **Create**.

-   Name - +++**Real Estate Workstream**+++

-   Owner -- **MOD Administrator** (Selected by default)

-   Type -- **Messaging**

-   Channel -- **Chat**

> ![A screenshot of a chat Description automatically
> generated](./media/media/image131.png){width="5.166932414698163in"
> height="4.562734033245844in"}
>
> ![A screenshot of a chat Description automatically
> generated](./media/media/image132.png){width="4.958588145231846in"
> height="4.604402887139107in"}

6.  Once the workstream is created, click on **Set up chat** to set up
    the chat channel.

![A screenshot of a chat Description automatically
generated](./media/media/image133.png){width="6.268055555555556in"
height="1.9784722222222222in"}

7.  In the **Live chat setup -- Channel details** screen, fill in the
    below details and click on **Next**.

-   Name - +++**Real Estate Chat Channel**+++

-   Language -- **United States**

![A screenshot of a chat box Description automatically
generated](./media/media/image134.png){width="3.8126957567804025in"
height="4.639127296587927in"}

8.  In the Live chat setup -- Chat widget screen, provide the name as
    +++**Real Estate Booking Assistant**+++, accept the other defaults
    and click on **Next**.

![A screenshot of a chat Description automatically
generated](./media/media/image135.png){width="4.521065179352581in"
height="4.646071741032371in"}

9.  In the **Live chat setup -- Behaviors** screen, accept the defaults
    and click on **Next**.

![A screenshot of a computer screen Description automatically
generated](./media/media/image136.png){width="6.160038276465442in"
height="4.6599617235345585in"}

10. In the **Live chat setup -- User features** screen, toggle **File
    attachment** and **Voice and video calls** options to **off** and
    click on **Next**.

![A screenshot of a computer Description automatically
generated](./media/media/image137.png){width="5.639178696412948in"
height="4.68079615048119in"}

11. In the **Live chat setup -- Review and finish** screen, select
    **Create channel**.

![A screenshot of a chat setup Description automatically
generated](./media/media/image138.png){width="5.437779965004374in"
height="4.583568460192476in"}

12. **Copy** the widget that appears in the **Live chat setup --
    Success** screen and **save** it in a notepad to add it to a webpage
    in the upcoming exercises. Then, click on **Done** to complete the
    configuration.

![A screenshot of a chat Description automatically
generated](./media/media/image139.png){width="6.268055555555556in"
height="3.827777777777778in"}

### Task 2: Add the copilot to the workstream

1.  Back in the **Real Estate Workstream** page, scroll down and click
    on **+ Add bot** in the Bot section.

![A screenshot of a computer Description automatically
generated](./media/media/image140.png){width="6.268055555555556in"
height="4.0256944444444445in"}

2.  From the list of copilots on the Add bot screen, select the **Real
    Estate Booking Service** copilot and click on **Connect**.

![A screenshot of a computer Description automatically
generated](./media/media/image141.png){width="6.268055555555556in"
height="3.5430555555555556in"}

3.  Ensure that the bot is added to the workstream as in the screenshot
    below.

![A screenshot of a computer Description automatically
generated](./media/media/image142.png){width="6.268055555555556in"
height="2.5479166666666666in"}

4.  From the left pane, select **Bots**.

![A screenshot of a computer Description automatically
generated](./media/media/image143.png){width="6.268055555555556in"
height="3.4256944444444444in"}

5.  Ensure that the Real Estate Booking Service copilot is connected.

![A screenshot of a computer Description automatically
generated](./media/media/image144.png){width="6.268055555555556in"
height="2.4590277777777776in"}

## Exercise 8: Create a webpage and test the escalation to agent

1.  Login to +++https://make.powerpages.microsoft.com/+++ using your
    tenant admin credentials.

![A screenshot of a computer Description automatically
generated](./media/media/image145.png){width="6.268055555555556in"
height="2.2625in"}

2.  Ensure that you are in CustomerService Trial environment.

3.  Click on Skip in the **Tell us about yourself** page.

![A screenshot of a computer Description automatically
generated](./media/media/image146.png){width="6.268055555555556in"
height="3.1798611111111112in"}

4.  Scroll down in the next page and click on Start with a template
    option to start creating the site with a template.

![A screenshot of a web page Description automatically
generated](./media/media/image147.png){width="6.268055555555556in"
height="1.86875in"}

5.  Select a template and click on **Choose this template**.

![A screenshot of a computer Description automatically
generated](./media/media/image148.png){width="6.268055555555556in"
height="3.4277777777777776in"}

6.  In the Give your site a name textbox, enter the name as +++**Contoso
    Real Estates**+++, accept the other defaults and click on **Done**.

![A screenshot of a computer Description automatically
generated](./media/media/image149.png){width="6.268055555555556in"
height="3.1868055555555554in"}

7.  Once the site is created, click on **Edit site header** in the
    **Company name** title.

![A screenshot of a computer Description automatically
generated](./media/media/image150.png){width="4.896084864391951in"
height="3.104326334208224in"}

8.  In the **Edit site header** pane, provide the **Site title** as
    **Contoso Real Estates**.

![A screenshot of a website Description automatically
generated](./media/media/image151.png){width="5.8127985564304465in"
height="3.8543646106736658in"}

9.  Click on Edit code in the top right corner of the page.

![A screenshot of a computer Description automatically
generated](./media/media/image152.png){width="6.268055555555556in"
height="2.7444444444444445in"}

10. Click on **Open Visual Studio Code**.

![A screenshot of a computer Description automatically
generated](./media/media/image153.png){width="4.833581583552056in"
height="1.701476377952756in"}

11. Click **Allow**.

![A black screen with white text Description automatically
generated](./media/media/image154.png){width="5.243324584426946in"
height="1.437574365704287in"}

12. The Home page of the web page opens up in the Visual Studio Code.

![A screenshot of a computer program Description automatically
generated](./media/media/image155.png){width="6.268055555555556in"
height="3.08125in"}

13. Scroll to the end of the file. Add the script copied while creating
    the workstream, after eh last line of this file.

![A screen shot of a computer screen Description automatically
generated](./media/media/image156.png){width="6.268055555555556in"
height="3.467361111111111in"}

14. Save the file, close the Visual Studio Code tab and return to the
    Power pages. Click on **Sync**.

![A screenshot of a computer Description automatically
generated](./media/media/image157.png){width="6.268055555555556in"
height="4.052777777777778in"}

15. Once the Sync is completed, select **Preview** -\> **Desktop.**

![A screenshot of a computer Description automatically
generated](./media/media/image158.png){width="6.268055555555556in"
height="2.9875in"}

16. Your web page opens in a new tab. Find the **Real Estate copilot**
    embedded to the page at the bottom right of the web page. **Click**
    on it.

![A close-up of a building Description automatically
generated](./media/media/image159.png){width="6.268055555555556in"
height="3.5680555555555555in"}

17. Enter +++Talk to agent+++.

![A screenshot of a phone Description automatically
generated](./media/media/image160.png){width="3.0001541994750656in"
height="4.639127296587927in"}

18. On the Customer Service workspace page, you will get a **chat
    request**. Accept it.

![A screenshot of a computer Description automatically
generated](./media/media/image161.png){width="6.268055555555556in"
height="3.2159722222222222in"}

19. Once accepted, the chat screen opens up with the message that we had
    given in the Escalate topic. We can also add any other information
    provided by the user here to the live agent.

![A screenshot of a chat Description automatically
generated](./media/media/image162.png){width="2.791809930008749in"
height="4.583568460192476in"}

20. Simulate the chat between the live agent and the customer if you
    wish to see how it works and then ends.

![A screenshot of a chat Description automatically
generated](./media/media/image163.png){width="4.208549868766404in"
height="6.222541557305337in"}

![A screenshot of a chat Description automatically
generated](./media/media/image164.png){width="3.743248031496063in"
height="5.666957567804024in"}

**Summary**

In this lab, we have learnt to

-   Build a copilot from the Copilot Studio and create topics in it.

-   Test the copilot from the Copilot Studio and publish it to the demo
    web site.

-   Publish the copilot to Dynamics 365 workspace and integrate the it
    in a web page.

-   Configure and test the escalation to a live agent.
