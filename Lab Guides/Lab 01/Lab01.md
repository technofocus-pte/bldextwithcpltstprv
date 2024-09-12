# Lab 01: Creating and using Copilot from Copilot Studio for managing a Real Estate Application

**Lab Duration** – 120 minutes

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

- Build a standalone copilot for Contoso Real Estates from Copilot
  Studio (that will allow customers to discover information about the
  real estate booking process and create booking requests for the office
  to review.)

- Create Topics to set up the logic of the bookings.

- Create the Dataverse tables required for the bookings.

- Publish the copilot.

- Configure the Dynamics 365 workspace and connect the copilot to it.

- Create a web page using Power Pages and integrate the copilot created
  from Copilot Studio in it.

- Test the escalation to live agent functionality from the web page.

## Exercise 1: Setting up the Dynamics 365 Customer Service

### Task 1: Sign up for Dynamics 365 Customer Service trial

1.  Login to
    +++<https://dynamics.microsoft.com/en-us/customer-service/overview/>+++
    and click on **Try for free**

![](./media/image1.png)

2.  Enter your Tenant id and click on **Start your free trial**.

<img src="./media/image2.png" style="width:6.26806in;height:3.80139in"
alt="A screenshot of a computer Description automatically generated" />

3.  Enter the region as **United States**, enter your **Phone number**
    and click on **Submit**.

<img src="./media/image3.png" style="width:4.18077in;height:5.06276in"
alt="A screenshot of a computer Description automatically generated" />

4.  The **Dynamics 365 Customer Service workspace** opens.

<img src="./media/image4.png" style="width:6.26806in;height:3.46458in"
alt="A screenshot of a computer Description automatically generated" />

5.  Click on Customer Service workspace to open the **Apps**.

<img src="./media/image5.png" style="width:5.72252in;height:4.6808in"
alt="A screenshot of a computer Description automatically generated" />

6.  Click on **Customer Service admin center** to open it.

<img src="./media/image6.png" style="width:6.26806in;height:3.43472in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select **Routing** under **Customer Support** group.

<img src="./media/image7.png" style="width:6.26806in;height:2.96806in"
alt="A screenshot of a computer Description automatically generated" />

8.  On the **Routing** page, under **Record routing**, click **Manage**
    next to **Turn on Unified Routing for Records**.

<img src="./media/image8.png" style="width:6.26806in;height:2.41875in"
alt="A screenshot of a computer Description automatically generated" />

9.  On the **Service Configuration Settings** page under **Unified
    routing**, make sure that the **Turn on unified routing** toggle is
    set to **Yes**.

**Note**: The **Turn on unified routing** toggle is set to **Yes** only
if consent is already provided by the tenant administrator.

10. Click **Save**.

<img src="./media/image9.png" style="width:6.26806in;height:3.96389in"
alt="A screenshot of a computer Description automatically generated" />

### **Task 2: Manage a user in Omnichannel for Customer Service**

1.  In **Dynamics 365 Customer Service admin center**, in the site map,
    select **User management** under **Customer support** group.

2.  On the **User management** page, select **Manage** next
    to **Users**.

<img src="./media/image10.png" style="width:6.26806in;height:2.37708in"
alt="A screenshot of a computer Description automatically generated" />

3.  Click the dropdown next to **Enabled Users** and select
    **Omnichannel Users**.

<img src="./media/image11.png" style="width:6.26806in;height:5.79722in"
alt="A screenshot of a computer Description automatically generated" />

4.  On the **Omnichannel Users** page, select a user **MOD
    Administrator** in the list.

<img src="./media/image12.png" style="width:6.26806in;height:2.90903in"
alt="A screenshot of a computer Description automatically generated" />

5.  On the **MOD Administrator** page, select the **Omnichannel** tab.

<img src="./media/image13.png" style="width:6.26806in;height:3.4375in"
alt="A screenshot of a computer Description automatically generated" />

6.  Specify the following in the user page.

| **Setting**      | **Value** |
|------------------|-----------|
| Capacity         | 100       |
| Default Presence | available |

<img src="./media/image14.png" style="width:6.26806in;height:2.56875in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select **Save and close**.

<img src="./media/image15.png" style="width:6.26806in;height:2.55278in"
alt="A screenshot of a computer Description automatically generated" />

### Task 3: Configure Omnichannel Power Virtual Agent Extension

1.  Open the link,
    +++<https://appsource.microsoft.com/en-cy/product/dynamics-365/mscrm.omnichannelpvaextension?tab=Overview&ref=dynamicsforcrm.com>+++
    and click on Get it now in the Omnichannel Power Virtual Agent
    Extension page.

<img src="./media/image16.png" style="width:6.26806in;height:2.99097in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image17.png" style="width:4.22938in;height:4.52107in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select the **CustomerService Trial** under **Select an environment**
    and click on **Install**.

<img src="./media/image18.png" style="width:4.77108in;height:5.05582in"
alt="A screenshot of a computer Description automatically generated" />

3.  In the Dynamics 365 apps page, click on the entries that shows
    **Update available**, **select** the **check box** to agree to the
    terms and click on **Update**.

Make sure to do this for **all** the entries with **Update available**
as the Status.

<img src="./media/image19.png" style="width:6.26806in;height:3.58056in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image20.png" style="width:4.81275in;height:5.03498in"
alt="A screenshot of a computer Description automatically generated" />

### Task 4: Configure search settings in the Power Platform admin center

1.  Login to +++<https://admin.powerplatform.microsoft.com/>+++ using
    your tenant details. Select **Environments** -\> **CustomerService
    Trial**.

<img src="./media/image21.png" style="width:5.98669in;height:3.57238in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select the drop down next to **Resource** (in the top pane) and
    select **Dynamics 365 apps**.

<img src="./media/image22.png" style="width:6.26806in;height:3.13403in"
alt="A screenshot of a computer Description automatically generated" />

3.  Make sure that **Omnichannel for Customer Service** is
    **Installed**.

<img src="./media/image23.png" style="width:6.26806in;height:3.85139in"
alt="A screenshot of a computer Description automatically generated" />

4.  Navigate back to the **Environments -\> CustomerService** **Trial**
    page in the admin center. Select **Settings** from the top pane.

> <img src="./media/image24.png" style="width:6.26806in;height:3.57917in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Select **Product** -\> **Features**.

<img src="./media/image25.png" style="width:6.26806in;height:4.12569in"
alt="A screenshot of a computer Description automatically generated" />

6.  Toggle **Dataverse Search** and **Single table search** option to
    **ON.**

<img src="./media/image26.png" style="width:6.26806in;height:3.67639in"
alt="A screenshot of a computer Description automatically generated" />

Scroll down and click on the **Save** button at the bottom right.

<img src="./media/image27.png" style="width:6.26806in;height:4.30069in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 2: Setting up Power Apps and Dataverse

### Task 1: Sign up for the Microsoft Power Apps Developer Plan

1.  Navigate to +++https://powerapps.microsoft.com/free/+++ and select
    **Start free**.

<img src="./media/image28.png" style="width:6.26806in;height:2.975in"
alt="A screenshot of a computer Description automatically generated" />

2.  Under **Let's get started**, enter your **email address** in the
    text box, check the agreement box and select **Start free**.

> <img src="./media/image29.png" style="width:6.26806in;height:3.84375in"
> alt="A screenshot of a computer Description automatically generated" />

3.  If you see a prompt that you have an existing account with
    Microsoft. Select **Sign in**. Enter your password.

4.  If prompted, Select **Yes** to stay signed in.

5.  Click on **Environment** in the top-right corner of the screen and
    select **CustomerService Trial**.

> <img src="./media/image30.png" style="width:6.26806in;height:1.80417in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 2: Create a solution

1.  From the Power Apps Maker
    Portal(+++<https://make.powerapps.com/>+++), select **Solutions**
    form the left pane.

<img src="./media/image31.png" style="width:6.26806in;height:2.56806in"
alt="A screenshot of a computer Description automatically generated" />

2.  Click on **+ New solution**.

<img src="./media/image32.png" style="width:6.26806in;height:3.78472in"
alt="A screenshot of a search engine Description automatically generated" />

3.  Enter +++**Bookings**+++ for the Display name and click on **+ New
    publisher**.

<img src="./media/image33.png" style="width:3.31267in;height:4.31272in"
alt="A screenshot of a computer Description automatically generated" />

4.  Enter the below details and then click on **Save**.

| **Property**     | **Value**     |
|------------------|---------------|
| **Display name** | +++Contoso+++ |
| **Name**         | +++contoso+++ |
| **Prefix**       | +++contoso+++ |

<img src="./media/image34.png" style="width:3.56268in;height:4.62524in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **Contoso (contoso)** under Publisher and then click on
    **Create**.

<img src="./media/image35.png" style="width:2.33345in;height:4.62524in"
alt="A screenshot of a computer Description automatically generated" />

6.  Select **Back to solutions** in the top-left of the screen.

<img src="./media/image36.png" style="width:6.26806in;height:2.425in"
alt="A screenshot of a computer Description automatically generated" />

### Task 3: Set the preferred solution

1.  Under Solutions in the Maker portal, select **Manage** for **Set
    your preferred solution**.

<img src="./media/image37.png" style="width:6.26806in;height:1.99861in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select **Bookings (contoso)** under **Unless otherwise specified,
    save my changes in** and select **Apply**.

<img src="./media/image38.png" style="width:5.68779in;height:2.7432in"
alt="A screenshot of a computer screen Description automatically generated" />

<img src="./media/image39.png" style="width:6.26806in;height:3.72917in"
alt="A screenshot of a computer Description automatically generated" />

### Task 4: Create the Real Estate Properties custom table

Follow these steps to create a new custom table in Dataverse for Real
Estate Properties.

1.  From the left navigation pane, select **Tables**, select **New
    table**, and then select **Add columns and data**.

<img src="./media/image40.png" style="width:6.26806in;height:3.9875in"
alt="A screenshot of a computer Description automatically generated" />

2.  Rename the table from **New Table** to +++**Real Estate
    Property**+++.

<img src="./media/image41.png" style="width:4.93775in;height:4.64607in"
alt="A screenshot of a computer Description automatically generated" />

3.  Change the name of the column called **New Column** to +++**Property
    Name**+++.

<img src="./media/image42.png" style="width:6.26806in;height:4.29306in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select the **+ New column** button to add a new column in the
    columns and data pane. In the New column pane, enter the following
    values, and then select **Save**.

    - Display name: +++**Asking Price**+++

    - Data type: Currency

> <img src="./media/image43.png" style="width:5.05582in;height:4.50023in"
> alt="A screenshot of a table Description automatically generated" />

5.  Add the following two columns.

| **Display name** | **Data type**                                   |
|------------------|-------------------------------------------------|
| +++Street+++     | Single line of text (this value is the default) |
| +++City+++       | Single line of text (this value is the default) |

6.  Add another column with the below values

    - **Display name**: +++Bedrooms+++

    - **Data type**: Choice

Create the choice values:

- Under **Choices** you see two entry fields
  titled **Label** and **Value**. Enter **1** under the label. Power
  Apps assigns a value automatically but you can change the value
  to **1**.

<!-- -->

- Select **+ New choice** and make **2** the new entry for Label
  and **2** for Value.

<!-- -->

- Select **+ New choice** and make **3** the new entry for Label
  and **3** for Value.

<!-- -->

- Select **+ New choice** and make **4** the new entry for Label
  and **4** for Value.

<!-- -->

- Select **+ New choice** and make **5** the new entry for Label
  and **5** for Value.

<!-- -->

- Select **Save**.

<img src="./media/image44.png" style="width:3.26406in;height:4.58357in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select the **+ New column** button to add a new column in the
    columns and data pane.

8.  In the New column pane, enter the following values, and then
    select **Save**:

    - **Display name**: +++Bathrooms+++

    - **Data type**: Choice

Create the choice values

- Under **Choices** you see two entry fields
  titled **Label** and **Value**. Enter **1** under the label. Power
  Apps assigns a value automatically but you can change it to **1**.

- Select **+ New choice** and make **2** the new entry for Label
  and **2** for Value.

- Select **+ New choice** and make **3** the new entry for Label
  and **3** for Value.

- Select **+ New choice** and make **4** the new entry for Label
  and **4** for Value.

- Select **+ New choice** and make **5** the new entry for Label
  and **5** for Value.

- Select **Save**.

> <img src="./media/image45.png" style="width:3.79186in;height:4.62524in"
> alt="A screenshot of a computer Description automatically generated" />

9.  Add another column by selecting the **+ New column** button again in
    the columns and data pane.

In the New column pane, enter the following values, and then
select **Save**:

- **Display name**: +++**Client**+++

- **Data type**: Lookup -\> Lookup

- **Related Table**: Contact

> <img src="./media/image46.png" style="width:4.32661in;height:4.61829in"
> alt="A screenshot of a computer Description automatically generated" />

10. At the bottom of the pane, select **Create**.

<img src="./media/image47.png" style="width:6.26806in;height:3.15556in"
alt="A screenshot of a computer Description automatically generated" />

11. Once the table is created, under **Real Estate Property columns and
    data**, enter the following test data:

    - Property Name: +++**1100 High Villas**+++

    - Asking Price: +++**250,000**+++

    - Bathrooms: **3**

    - Bedrooms: **2**

    - City: +++**Redmond**+++

    - Street: +++**Main Avenue**+++

    - Client: **Select any contact**

> <img src="./media/image48.png" style="width:6.26806in;height:3.34306in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 5: Create the Bookings table

Follow these steps to create a new custom table in Dataverse for Real
Estate Property Bookings.

1.  From the left navigation pane, select **Tables**, select **New
    table**, and then select **Add columns and data**.

> <img src="./media/image49.png" style="width:5.15999in;height:4.66691in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Rename the table as +++**Booking Request**+++.

> <img src="./media/image50.png" style="width:4.39606in;height:4.6044in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Change the name of the column called **New Column** to +++**Booking
    Name**+++.

> <img src="./media/image51.png" style="width:6.26806in;height:4.27292in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Create the following columns with the name and data type as
    specified in the table below. Select **Save**.

> Display name – +++**Property**+++
>
> Data type – **Lookup** -\> **Lookup**
>
> Related Table – **Real Estate Property**
>
> <img src="./media/image52.png" style="width:6.26806in;height:4.38264in"
> alt="A screenshot of a computer Description automatically generated" />
>
> Display name – +++**Viewer Name**+++
>
> Data type – **Single line of text**
>
> Display name – +++**Viewer Email**+++
>
> Data type – **Single line of text**
>
> Format – **Email**
>
> Display name – +++**Booking Date**+++
>
> Data type – **Date and time**
>
> Display name – +++**Notes**+++
>
> Data type – **Multiple lines of text**
>
> <img src="./media/image53.png" style="width:5.97253in;height:4.58357in"
> alt="A screenshot of a computer Description automatically generated" />
>
> <img src="./media/image54.png" style="width:3.51407in;height:4.4794in"
> alt="A screenshot of a computer Description automatically generated" />
>
> Display name – +++**Decision**+++
>
> Data type – **Choice**

- Label – +++**Undecided**+++

- Value – 1

- Label – +++**Accepted**+++

- Value – 2

- Label – +++**Declined**+++

- Value – 3

> Designate **Undecided** as the **Default choice**.

<img src="./media/image55.png" style="width:2.27095in;height:4.64607in"
alt="A screenshot of a computer Description automatically generated" />

5.  At the bottom of the pane, select **Create**.

> <img src="./media/image56.png" style="width:6.26806in;height:3.20833in"
> alt="A screenshot of a computer Description automatically generated" />

6.  Ensure that the table is created successfully.

## Exercise 3: Working with Copilot Studio

### Task 1: Sign up for Copilot Studio trial

1.  Open the url +++https://copilotstudio.microsoft.com/+++.

2.  Leave the **Choose your country/region** with the **default** value
    and click on **Get Started**.

<img src="./media/image57.png" style="width:6.26806in;height:4.52153in"
alt="A person sitting at a computer Description automatically generated" />

3.  Click on **Environments** on the top left and select
    **CustomerService Trial**.

<img src="./media/image58.png" style="width:6.26806in;height:1.95208in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **Skip** if you get a Welcome to Copilot Studio! Prompt**.**

<img src="./media/image59.png" style="width:5.30583in;height:4.59746in"
alt="A screenshot of a computer Description automatically generated" />

### Task 2: Create the Real Estate Booking Service Copilot

1.  Select **Create** from the left navigation pane and select the **New
    copilot** tile.

<img src="./media/image60.png" style="width:6.26806in;height:2.71458in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select **Skip to configure**.

<img src="./media/image61.png" style="width:6.26806in;height:1.72153in"
alt="A screenshot of a computer Description automatically generated" />

3.  Fill in the below details.

- Name - +++**Real Estate Booking Service**+++

- Description - +++**Create bookings for real estate properties**+++

- Instructions - +++**Create a copilot for topics relating to creating
  bookings for real estate properties+++**

- Language **–** Select **English**

> <img src="./media/image62.png" style="width:6.01756in;height:2.89344in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Select the three dots next to the Create button in the top-right of
    the screen and select **Edit advanced settings**.

<img src="./media/image63.png" style="width:3.84742in;height:3.08349in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select the **Bookings** solution and select **Save**.

<img src="./media/image64.png" style="width:5.36833in;height:3.37517in"
alt="A screenshot of a computer Description automatically generated" />

6.  In the top-right of the screen, select **Create**.

<img src="./media/image65.png" style="width:6.26806in;height:2.08958in"
alt="A screenshot of a computer Description automatically generated" />

7.  Once the copilot is created, in the Test your copilot pane, enter
    **How do I make a booking?** and click **Enter** and observe the
    response.

<img src="./media/image66.png" style="width:6.26806in;height:4.43264in"
alt="A screenshot of a computer Description automatically generated" />

### Task 3: Configure Security

1.  Select **Settings** in the top-right of the screen.

<img src="./media/image67.png" style="width:6.26806in;height:2.56389in"
alt="A screenshot of a chat Description automatically generated" />

2.  Select the **Security** tab and then select
    the **Authentication** tile.

<img src="./media/image68.png" style="width:6.26806in;height:2.97639in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **No authentication** and click on **Save**.

<img src="./media/image69.png" style="width:6.26806in;height:3.17361in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **Save** in the **Save this configuration** prompt.

<img src="./media/image70.png" style="width:5.2711in;height:3.58352in"
alt="A screenshot of a computer Description automatically generated" />

5.  Once the Authentication settings are saved, click on the **Close**
    option to close the **Settings** pane.

<img src="./media/image71.png" style="width:6.26806in;height:3.0875in"
alt="A screenshot of a computer Description automatically generated" />

### Task 4: Remove topics

Sample topics are included with new copilots. Remove these sample
topics. Disable system topics that you don't require.

1.  Select the **Topics** tab from the top menu of the Copilot Overview
    page.

<img src="./media/image72.png" style="width:4.72941in;height:3.75019in"
alt="A screenshot of a computer Description automatically generated" />

2.  You will land in the **Custom** Topics page.

3.  Select the **three dots** next to the **Lesson 1** topic and select
    **Delete**.

<img src="./media/image73.png" style="width:4.83358in;height:4.63913in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **Save** in the confirmation window.

<img src="./media/image74.png" style="width:5.33361in;height:1.37507in"
alt="A white background with black text Description automatically generated" />

5.  Repeat the delete for Lesson 2 and Lesson 3.

<img src="./media/image75.png" style="width:4.93775in;height:4.62524in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image76.png" style="width:4.6044in;height:4.62524in"
alt="A screenshot of a computer Description automatically generated" />

6.  Select the **System** tab. Toggle **Enabled** to **Off** for the
    **Sign in** topic.

<img src="./media/image77.png" style="width:5.84752in;height:4.63913in"
alt="A screenshot of a computer Description automatically generated" />

### Task 5: Publish and test the copilot

1.  Select **Publish** and select **Publish** again.

<img src="./media/image78.png" style="width:6.26806in;height:1.85486in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select **Publish** in the **Publish this copilot** dialog.

<img src="./media/image79.png" style="width:5.76419in;height:1.65981in"
alt="A screenshot of a computer Description automatically generated" />

### Task 6: Demo Website

The Demo website allows users without a license to test your copilot.
You can provide them with the URL to the demo website.

1.  Select the **three dots** next to the **Settings** button in the
    top-right of the screen and select **Go to demo website**.

<img src="./media/image80.png" style="width:6.26806in;height:1.65625in"
alt="A screenshot of a web page Description automatically generated" />

2.  In the **Type your message** text box, enter **What information is
    needed to book a viewing for a real estate property?** and observe
    the response from the copilot.

<img src="./media/image81.png" style="width:6.26806in;height:3.16042in"
alt="A screenshot of a chatbot Description automatically generated" />

## Exercise 4: Create and manage topics using Copilot

### Task 1: Create a topic using Copilot

Topics can be created and edited using natural language.

1.  Select your copilot, **Real Estate Booking Service** in the Copilot
    pane on the left-hand side of the Copilot Studio.

<img src="./media/image82.png" style="width:6.26806in;height:1.78056in"
alt="A screenshot of a web page Description automatically generated" />

2.  Select the **Topics** tab. Select **Add a topic** and select
    **Create from description with Copilot**.

<img src="./media/image83.png" style="width:6.26806in;height:2.65903in"
alt="A screenshot of a computer Description automatically generated" />

3.  Enter the below details and click on **Create**.

- Name your topic - +++**Customer Details**+++

- Create a topic to... - +++**Ask the customer for their name and email
  address**+++

> <img src="./media/image84.png" style="width:6.11295in;height:3.17499in"
> alt="A screenshot of a computer Description automatically generated" />

4.  A new topic displays with the generated trigger phrases and question
    nodes.

5.  Select **Save**.

> <img src="./media/image85.png" style="width:6.26806in;height:3.90556in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 2: Update nodes with natural language

1.  If the **Edit with copilot** pane isn't shown on the right-hand side
    of the screen, select the **Copilot** icon in the upper part of the
    authoring canvas.

2.  Select the second question node, **What is your email address?**

3.  In the **Edit with Copilot** panel, in the **What do you want to
    do?** field, enter the following text:

> +++**Update the message in this question node to say thank you to the
> Name variable from the previous node and then proceed to ask the email
> address question**+++

4.  Select **Update**.

<img src="./media/image86.png" style="width:6.26806in;height:4.26319in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **Save**.

<img src="./media/image87.png" style="width:6.26806in;height:2.11389in"
alt="A screenshot of a computer Description automatically generated" />

### Task 3: Add nodes with natural language

In addition to adding updating existing nodes, you can use Copilot to
add new ones.

1.  Make sure that no node is selected by clicking in the empty space
    around the nodes.

2.  In the **Edit with Copilot** panel, in the **What do you want to
    do?** field, enter the following text:

+++**Summarize the information collected in an adaptive card**+++

3.  Select **Update**.

> <img src="./media/image88.png" style="width:6.26806in;height:3.12708in"
> alt="A screenshot of a computer Description automatically generated" />

4.  A message node with an Adaptive Card is added to the end of the
    topic.

> <img src="./media/image89.png" style="width:4.35439in;height:4.5419in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Select the Adaptive Card. The Adaptive Card properties should appear
    on the right of the screen.

6.  Copy the below content and paste it as the Adaptive card formula if
    it is not already populated properly.

> **{**
>
> **type: "AdaptiveCard",**
>
> **body:**
>
> **\[**
>
> **{**
>
> **type: "TextBlock",**
>
> **size: "Medium",**
>
> **weight: "Bolder",**
>
> **text: "Summary"**
>
> **},**
>
> **{**
>
> **type: "FactSet",**
>
> **facts:**
>
> **\[**
>
> **{**
>
> **title: "Full Name",**
>
> **value: Text(Topic.Name)**
>
> **},**
>
> **{**
>
> **title: "Email Address",**
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
> **type: "TextBlock",**
>
> **text: "Thank you for providing the information."**
>
> **}**
>
> **\]**
>
> **}**
>
> Your card content should now look like the one in the below image.
>
> <img src="./media/image90.png" style="width:5.72946in;height:5.8753in"
> alt="A screenshot of a computer program Description automatically generated" />

7.  Open the **Edit with Copilot** icon.

<img src="./media/image91.png"
style="width:4.41689in;height:4.58357in" />

8.  Make sure that no node is selected by clicking in the empty space
    around the nodes.

9.  In the **What do you want to do?** field, enter the following text
    and then select **Update.**

> **Add a new multiple-choice question to prompt the user if the details
> are correct with two options Yes or No**

<img src="./media/image92.png" style="width:5.29194in;height:4.51412in"
alt="A screenshot of a computer Description automatically generated" />

10. A new question node is added to the end of the topic with options
    for the user to select.

11. Select **Save**.

> <img src="./media/image93.png" style="width:6.26806in;height:4.11667in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 4: Configure the scope of the variables

1.  Select **Variables** to open the Variables pane.

<img src="./media/image94.png" style="width:6.14615in;height:3.06266in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select the right-hand check boxes for the topic variables and click
    on **Save**.

<img src="./media/image95.png" style="width:4.64607in;height:4.6044in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 5: Create and manage topics manually

### Task 1: Create a topic from blank

1.  Select the **Topics** tab.

2.  Select **Add a topic** and select **From blank**.

> <img src="./media/image96.png" style="width:6.26806in;height:3.46528in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select **Details** to open the Topic details dialog.

> <img src="./media/image97.png" style="width:5.95864in;height:4.0141in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Fill in the below details and click on **Save**.

- **Name** - +++Book a Real Estate Showing+++

- **Display Name –** +++**Book**+++

- **Description**  - +++Select the property and requested date and
  create a booking request+++

<img src="./media/image98.png" style="width:6.26806in;height:3.63819in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **Details** to close the Topic details dialog.

<img src="./media/image99.png" style="width:6.26806in;height:2.99097in"
alt="A screenshot of a computer Description automatically generated" />

### Task 2: Add trigger phrases

1.  Select **Edit** under **Phrases** in the **Trigger**. Enter +++**I
    want to book a real estate showing**+++ under **Add Phrases** and
    select the **+** icon.

> <img src="./media/image100.png" style="width:5.68779in;height:4.43078in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Enter the below phrases one by one.

- +++**Schedule a real estate showing**+++

- +++**Arrange the viewing for a real estate property**+++

- +++**Set up an appointment to view a house**+++

- +++**Plan a property viewing**+++

3.  Once all the phrases are added, select **Save**.

> <img src="./media/image101.png" style="width:6.26806in;height:4.02708in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 3: Add a message node

1.  Select the **+** icon under the Trigger node and select **Send a
    message**.

> <img src="./media/image102.png" style="width:5.64612in;height:4.57662in"
> alt="A screenshot of a computer Description automatically generated" />

2.  In the **Enter a message** field, enter the following text:

+++Hi, I can help you with booking a real estate property showing.+++

3.  Select **Save**.

> <img src="./media/image103.png" style="width:6.26806in;height:3.72431in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 4: Add a Topic management node

1.  Select the the **+** icon under the send a message node and
    select **Topic management -\> Go to another topic**.

<img src="./media/image104.png" style="width:5.29194in;height:4.62524in"
alt="A screenshot of a chat Description automatically generated" />

2.  Select the **Customer Details** topic.

<img src="./media/image105.png" style="width:5.60445in;height:4.64607in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Save**.

<img src="./media/image106.png" style="width:6.26806in;height:3.68125in"
alt="A screenshot of a computer Description automatically generated" />

### Task 5: Add condition node 

1.  Select the **+** icon under the topic management node and
    select **Add a condition**.

<img src="./media/image107.png" style="width:4.45856in;height:4.02104in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select **DetailsCorrect** for variable.

<img src="./media/image108.png"
style="width:6.26806in;height:3.90625in" />

3.  Select the **Condition** as **is equal to**

4.  Select the **value** as **Yes**.

<img src="./media/image109.png" style="width:6.26806in;height:3.70139in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **Save**.

<img src="./media/image110.png" style="width:6.26806in;height:3.76111in"
alt="A screenshot of a computer Description automatically generated" />

### Task 6: Add question nodes

1.  Select the **+** icon under the left-hand condition node and
    select **Ask a question**. Fill in the below details and click on
    **Save**.

- Enter a message  - +++Which property do you want to see?+++

- **Identify** - Select **User's entire response**.

- **Save user response as** -
  Enter +++**PropertyName**+++ for **Variable name**

<img src="./media/image111.png" style="width:6.26806in;height:3.92153in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select the the **+** icon under the question node and select **Ask a
    question**. Fill in the below details and click on **Save.**

- **Enter a message** - +++What date and time do you want to see the
  property?+++

- Identify - Select **Date and Time**

- **Save user response as** - Enter +++**DateTime**+++ for **Variable
  name**

> <img src="./media/image112.png" style="width:6.26806in;height:4.08889in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 7: Test the copilot

1.  Select the **Test** button in the top-right of the screen to open
    the testing panel. Select the **three dots** at the top of the
    testing panel in the top-right of the screen. Select **Track between
    topics**.

> <img src="./media/image113.png" style="width:5.85592in;height:4.05944in"
> alt="A screenshot of a computer Description automatically generated" />

2.  When the **Conversation Start** message appears, your copilot starts
    a conversation.

3.  In response, enter a trigger phrase for the topic that you created:

+++I want to book a real estate showing+++

4.  The copilot responds with the "**What is your name?**" question.

5.  Enter your name.

> <img src="./media/image114.png" style="width:2.47235in;height:4.43773in"
> alt="A screenshot of a chat Description automatically generated" />

6.  Then enter your email when it prompts for the email. After you enter
    the details, an Adaptive Card displays the information that you
    entered, a question asking if the information is correct, and
    options to select **Yes** or **No**. Select **Yes**.

> <img src="./media/image115.png"
> style="width:2.62513in;height:4.6044in" />

7.  Enter +++555 Oak Lane, Denver, CO 80203+++ to the **Which property
    to you want to see?** prompt.

8.  Enter **Tomorrow 10:00 AM** to the **What date and time do you want
    to see the property?** prompt.

<img src="./media/image116.png" style="width:2.50013in;height:4.66691in"
alt="A screenshot of a chat Description automatically generated" />

## Exercise 6: Connect the copilot to Dynamics 365 Customer Service and configure the Escalate topic

### Task 1: Configure the Escalate topic

1.  Select the **Topics** tab and then select the **System** tab. Select
    the **Escalate** topic.

<img src="./media/image117.png" style="width:6.26806in;height:4.15347in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select the message node of the topic and replace the existing
    content with, +++You will be transferred to a live agent shortly+++

<img src="./media/image118.png" style="width:6.26806in;height:3.74375in"
alt="A screenshot of a computer Description automatically generated" />

3.  Click on the + symbol to add a node next to the Message node.

4.  Select **Topic management** -\> **Transfer conversation**.

<img src="./media/image119.png" style="width:6.26806in;height:4.33611in"
alt="A screenshot of a computer Description automatically generated" />

5.  Give a message +++The customer wants to talk to a live agent+++ in
    the Transfer conversation node.

<img src="./media/image120.png" style="width:6.26806in;height:4.60208in"
alt="A screenshot of a chat Description automatically generated" />

6.  **Save** the Topic.

<img src="./media/image121.png" style="width:6.26806in;height:2.27292in"
alt="A screenshot of a computer Description automatically generated" />

7.  **Publish** the copilot.

<img src="./media/image122.png" style="width:6.26806in;height:2.74653in"
alt="A screenshot of a computer Description automatically generated" />

### Task 2: Connect the copilot to Dynamics 365 Customer Service

1.  Click on the **Overview** option to arrive at the Overview page of
    the copilot.

<img src="./media/image123.png" style="width:6.26806in;height:1.43819in"
alt="A screenshot of a computer Description automatically generated" />

2.  From the copilot page top menu, click on **Channels** (If the
    Channels is not visible, click on the +1 to view the **Channels**
    option)

<img src="./media/image124.png" style="width:6.26806in;height:4.43056in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Dynamics 365 Customer Service** from the Customer
    engagement hub pane.

<img src="./media/image125.png" style="width:6.26806in;height:4.40556in"
alt="A screenshot of a computer Description automatically generated" />

4.  On the Dynamics 365 Customer Service page, click on **Connect**.

<img src="./media/image126.png" style="width:3.52101in;height:4.62524in"
alt="A screenshot of a message Description automatically generated" />

5.  Once you get a **successfully connected** message, click on
    **Close**.

<img src="./media/image127.png" style="width:3.45851in;height:4.66691in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 7: Create workstream and channel in Dynamics 365 admin center

### Task 1: Configure workstream 

1.  Login to +++<https://www.office.com>+++ using your admin tenant id.

2.  Select **Apps** from the left pane.

<img src="./media/image128.png" style="width:6.26806in;height:3.64097in"
alt="A screenshot of a computer Description automatically generated" />

3.  From the list of Apps listed, select **Customer Service admin
    center**.

<img src="./media/image129.png" style="width:6.26806in;height:2.15208in"
alt="A screenshot of a computer Description automatically generated" />

4.  From the admin center page, select **Workstreams** from the left
    pane and then select the **+ New workstream** option.

<img src="./media/image130.png" style="width:5.01415in;height:4.5419in"
alt="A screenshot of a computer Description automatically generated" />

5.  Fill in the below details, scroll down and click on **Create**.

- Name - +++**Real Estate Workstream**+++

- Owner – **MOD Administrator** (Selected by default)

- Type – **Messaging**

- Channel – **Chat**

> <img src="./media/image131.png" style="width:5.16693in;height:4.56273in"
> alt="A screenshot of a chat Description automatically generated" />
>
> <img src="./media/image132.png" style="width:4.95859in;height:4.6044in"
> alt="A screenshot of a chat Description automatically generated" />

6.  Once the workstream is created, click on **Set up chat** to set up
    the chat channel.

<img src="./media/image133.png" style="width:6.26806in;height:1.97847in"
alt="A screenshot of a chat Description automatically generated" />

7.  In the **Live chat setup – Channel details** screen, fill in the
    below details and click on **Next**.

- Name - +++**Real Estate Chat Channel**+++

- Language – **United States**

<img src="./media/image134.png" style="width:3.8127in;height:4.63913in"
alt="A screenshot of a chat box Description automatically generated" />

8.  In the Live chat setup – Chat widget screen, provide the name as
    +++**Real Estate Booking Assistant**+++, accept the other defaults
    and click on **Next**.

<img src="./media/image135.png" style="width:4.52107in;height:4.64607in"
alt="A screenshot of a chat Description automatically generated" />

9.  In the **Live chat setup – Behaviors** screen, accept the defaults
    and click on **Next**.

<img src="./media/image136.png" style="width:6.16004in;height:4.65996in"
alt="A screenshot of a computer screen Description automatically generated" />

10. In the **Live chat setup – User features** screen, toggle **File
    attachment** and **Voice and video calls** options to **off** and
    click on **Next**.

<img src="./media/image137.png" style="width:5.63918in;height:4.6808in"
alt="A screenshot of a computer Description automatically generated" />

11. In the **Live chat setup – Review and finish** screen, select
    **Create channel**.

<img src="./media/image138.png" style="width:5.43778in;height:4.58357in"
alt="A screenshot of a chat setup Description automatically generated" />

12. **Copy** the widget that appears in the **Live chat setup –
    Success** screen and **save** it in a notepad to add it to a webpage
    in the upcoming exercises. Then, click on **Done** to complete the
    configuration.

<img src="./media/image139.png" style="width:6.26806in;height:3.82778in"
alt="A screenshot of a chat Description automatically generated" />

### Task 2: Add the copilot to the workstream

1.  Back in the **Real Estate Workstream** page, scroll down and click
    on **+ Add bot** in the Bot section.

<img src="./media/image140.png" style="width:6.26806in;height:4.02569in"
alt="A screenshot of a computer Description automatically generated" />

2.  From the list of copilots on the Add bot screen, select the **Real
    Estate Booking Service** copilot and click on **Connect**.

<img src="./media/image141.png" style="width:6.26806in;height:3.54306in"
alt="A screenshot of a computer Description automatically generated" />

3.  Ensure that the bot is added to the workstream as in the screenshot
    below.

<img src="./media/image142.png" style="width:6.26806in;height:2.54792in"
alt="A screenshot of a computer Description automatically generated" />

4.  From the left pane, select **Bots**.

<img src="./media/image143.png" style="width:6.26806in;height:3.42569in"
alt="A screenshot of a computer Description automatically generated" />

5.  Ensure that the Real Estate Booking Service copilot is connected.

<img src="./media/image144.png" style="width:6.26806in;height:2.45903in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 8: Create a webpage and test the escalation to agent

1.  Login to +++https://make.powerpages.microsoft.com/+++ using your
    tenant admin credentials.

<img src="./media/image145.png" style="width:6.26806in;height:2.2625in"
alt="A screenshot of a computer Description automatically generated" />

2.  Ensure that you are in CustomerService Trial environment.

3.  Click on Skip in the **Tell us about yourself** page.

<img src="./media/image146.png" style="width:6.26806in;height:3.17986in"
alt="A screenshot of a computer Description automatically generated" />

4.  Scroll down in the next page and click on Start with a template
    option to start creating the site with a template.

<img src="./media/image147.png" style="width:6.26806in;height:1.86875in"
alt="A screenshot of a web page Description automatically generated" />

5.  Select a template and click on **Choose this template**.

<img src="./media/image148.png" style="width:6.26806in;height:3.42778in"
alt="A screenshot of a computer Description automatically generated" />

6.  In the Give your site a name textbox, enter the name as +++**Contoso
    Real Estates**+++, accept the other defaults and click on **Done**.

<img src="./media/image149.png" style="width:6.26806in;height:3.18681in"
alt="A screenshot of a computer Description automatically generated" />

7.  Once the site is created, click on **Edit site header** in the
    **Company name** title.

<img src="./media/image150.png" style="width:4.89608in;height:3.10433in"
alt="A screenshot of a computer Description automatically generated" />

8.  In the **Edit site header** pane, provide the **Site title** as
    **Contoso Real Estates**.

<img src="./media/image151.png" style="width:5.8128in;height:3.85436in"
alt="A screenshot of a website Description automatically generated" />

9.  Click on Edit code in the top right corner of the page.

<img src="./media/image152.png" style="width:6.26806in;height:2.74444in"
alt="A screenshot of a computer Description automatically generated" />

10. Click on **Open Visual Studio Code**.

<img src="./media/image153.png" style="width:4.83358in;height:1.70148in"
alt="A screenshot of a computer Description automatically generated" />

11. Click **Allow**.

<img src="./media/image154.png" style="width:5.24332in;height:1.43757in"
alt="A black screen with white text Description automatically generated" />

12. The Home page of the web page opens up in the Visual Studio Code.

<img src="./media/image155.png" style="width:6.26806in;height:3.08125in"
alt="A screenshot of a computer program Description automatically generated" />

13. Scroll to the end of the file. Add the script copied while creating
    the workstream, after eh last line of this file.

<img src="./media/image156.png" style="width:6.26806in;height:3.46736in"
alt="A screen shot of a computer screen Description automatically generated" />

14. Save the file, close the Visual Studio Code tab and return to the
    Power pages. Click on **Sync**.

<img src="./media/image157.png" style="width:6.26806in;height:4.05278in"
alt="A screenshot of a computer Description automatically generated" />

15. Once the Sync is completed, select **Preview** -\> **Desktop.**

<img src="./media/image158.png" style="width:6.26806in;height:2.9875in"
alt="A screenshot of a computer Description automatically generated" />

16. Your web page opens in a new tab. Find the **Real Estate copilot**
    embedded to the page at the bottom right of the web page. **Click**
    on it.

<img src="./media/image159.png" style="width:6.26806in;height:3.56806in"
alt="A close-up of a building Description automatically generated" />

17. Enter +++Talk to agent+++.

<img src="./media/image160.png" style="width:3.00015in;height:4.63913in"
alt="A screenshot of a phone Description automatically generated" />

18. On the Customer Service workspace page, you will get a **chat
    request**. Accept it.

<img src="./media/image161.png" style="width:6.26806in;height:3.21597in"
alt="A screenshot of a computer Description automatically generated" />

19. Once accepted, the chat screen opens up with the message that we had
    given in the Escalate topic. We can also add any other information
    provided by the user here to the live agent.

<img src="./media/image162.png" style="width:2.79181in;height:4.58357in"
alt="A screenshot of a chat Description automatically generated" />

20. Simulate the chat between the live agent and the customer if you
    wish to see how it works and then ends.

<img src="./media/image163.png" style="width:4.20855in;height:6.22254in"
alt="A screenshot of a chat Description automatically generated" />

<img src="./media/image164.png" style="width:3.74325in;height:5.66696in"
alt="A screenshot of a chat Description automatically generated" />

**Summary**

In this lab, we have learnt to

- Build a copilot from the Copilot Studio and create topics in it.

- Test the copilot from the Copilot Studio and publish it to the demo
  web site.

- Publish the copilot to Dynamics 365 workspace and integrate the it in
  a web page.

- Configure and test the escalation to a live agent.
