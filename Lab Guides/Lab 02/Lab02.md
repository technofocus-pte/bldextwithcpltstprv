## Lab 02 - Enhancing the Real Estate copilot with Gen AI capabilities

**Lab duration** – 80 minutes

**Objective:**

Implement entities, slot filling and variables usage in the Copilot for
Real Estate app. Enhance the copilot created for the Real Estate app to
elevate the customer experience by implementing Generative AI.

## Exercise 1: Use entities to improve the copilot

Microsoft Copilot Studio uses entities to understand user intent. There
are many prebuilt entities included for commonly used information. You
can create custom entities for your specific purpose.

### Task 1: View prebuilt entities

1.  Select **Settings** in the top-right of the screen.

> <img src="./media/image1.png" style="width:6.26806in;height:2.20764in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **Entities** tab. You can see a list of pre-built
    entities.

> <img src="./media/image2.png" style="width:6.26806in;height:3.88125in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 2: Create the property type entity

1.  Select **+ Add an entity** and select **+ New entity**.

> <img src="./media/image3.png" style="width:5.85447in;height:3.77103in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **Closed list** tile.

> <img src="./media/image4.png" style="width:6.26806in;height:3.71319in"
> alt="A screenshot of a web page Description automatically generated" />

3.  Enter the below details

> Name - +++**Property Type**+++
>
> **Enter item** under List items –
>
> +++**Apartment**+++ - Select **Add**
>
> <img src="./media/image5.png" style="width:6.26806in;height:2.71319in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Enter +++**Condominium**+++ in the **Enter item** field and
    select **Add**.

5.  Enter +++**Duplex**+++ in the **Enter item** field and
    select **Add**.

> <img src="./media/image6.png" style="width:5.1461in;height:4.6044in"
> alt="A screenshot of a computer Description automatically generated" />

6.  Select **+ Synonyms** for **Apartment**, enter +++**Flat**+++, then
    select the **+** icon and select **Done**.

> <img src="./media/image7.png" style="width:5.89614in;height:4.6808in"
> alt="A screenshot of a computer Description automatically generated" />

7.  Select **+ Synonyms** for **House**, enter +++**Single-family
    home**+++, then select the **+** icon and select **Done**.

8.  Select **+ Synonyms** for **Condominium**,
    enter +++**Townhouse**+++, then select the **+** icon and
    select **Done**.

9.  Select **Save**.

> <img src="./media/image8.png" style="width:5.11832in;height:4.62524in"
> alt="A screenshot of a computer Description automatically generated" />

10. Select **Close**.

> <img src="./media/image9.png" style="width:6.26806in;height:3.24792in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 3: Create number of bedrooms entity

1.  Select **+ Add an entity** and select **+ New entity**.

> <img src="./media/image10.png" style="width:5.35444in;height:4.05576in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **Regular expression (Regex)** tile.

> <img src="./media/image11.png" style="width:6.26806in;height:3.51875in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Enter the below details and click on **Save**.

- Name  - +++**Number of Bedrooms**+++ 

- Pattern  - +++**\[1-5\]**+++ 

> <img src="./media/image12.png" style="width:1.83343in;height:4.59746in"
> alt="A screenshot of a cell phone Description automatically generated" />

4.  Select **Close**.

> <img src="./media/image13.png" style="width:1.81259in;height:4.6044in"
> alt="A screenshot of a phone Description automatically generated" />

5.  Close the **Settings** pane.

<img src="./media/image14.png" style="width:6.26806in;height:3.33542in"
alt="A screenshot of a computer Description automatically generated" />

### Task 4: Use entities

1.  Select the **Topics** tab. Select the **Book a Real Estate
    Showing** topic.

> <img src="./media/image15.png" style="width:6.26806in;height:3.71597in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **+** icon above the property question node and
    select **Ask a question**.

> <img src="./media/image16.png" style="width:5.50028in;height:4.59746in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Fill in the below details.

- **Enter a message** - +++What type of property do you want to see?+++

- **Identify** – Select **Property Type**

- Select **Select options for user** and check the **Display** option
  for all list values.

<img src="./media/image17.png" style="width:5.55584in;height:4.51412in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select the variable in **Save user response as** and enter
    +++**PropertyType**+++ for **Variable name**

> <img src="./media/image18.png" style="width:6.26806in;height:4.4in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Select the the **+** icon below the new question node and
    select **Ask a question**.

6.  Enter the below details and click on **Save**.

- **Enter a message** - +++How many bedrooms do you need?+++

- **Identify -** Select **Number of Bedrooms**

- **Save user response as** -
  Enter +++NumberofBedrooms+++ for **Variable name**

> <img src="./media/image19.png" style="width:6.26806in;height:3.75764in"
> alt="A screenshot of a computer Description automatically generated" />

## Exercise 2: Create Copilot actions

Microsoft Copilot Studio can access data in Microsoft Dataverse using
Power Automate cloud flows

### Task 1: Create Power Automate flow to retrieve a property

1.  Select the **Actions** tab from the top menu. Select **+ Add an
    action**.

> <img src="./media/image20.png" style="width:6.22254in;height:4.51412in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Scroll down and select **Create a new flow**.

> <img src="./media/image21.png" style="width:5.64612in;height:4.63913in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Sign in to Power Automate if prompted.

4.  Select **Run a flow from Copilot** in the top-left of the screen and
    enter +++**Get Property**+++ as the flow name.

> <img src="./media/image22.png" style="width:6.26806in;height:4.47153in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Select the trigger step **Run a flow from Copilot** and select **+
    Add an input**.

> <img src="./media/image23.png" style="width:6.26806in;height:3.72847in"
> alt="A screenshot of a computer Description automatically generated" />

6.  Select **Text**.

> <img src="./media/image24.png" style="width:6.26806in;height:2.87222in"
> alt="A screenshot of a computer Description automatically generated" />

7.  Enter the below details

- **Input** – +++Bedrooms+++

- **Please enter your input** - +++Number of Bedrooms+++

> <img src="./media/image25.png" style="width:6.26806in;height:2.38958in"
> alt="A screenshot of a computer Description automatically generated" />

8.  Select the **+** icon between the two steps in the flow and
    select **Add an action**.

> <img src="./media/image26.png" style="width:4.08354in;height:3.05571in"
> alt="A screenshot of a computer Description automatically generated" />

9.  Enter +++**Dataverse**+++ in the **Search** field and select **See
    more** for the Dataverse connector.

> <img src="./media/image27.png" style="width:6.18087in;height:4.29189in"
> alt="A screenshot of a computer Description automatically generated" />

10. Select the **List rows** action.

> <img src="./media/image28.png" style="width:5.10443in;height:4.58357in"
> alt="A screenshot of a list Description automatically generated" />

11. If prompted for authentication, select **OAuth** and select **Sign
    in**. Sign in using your tenant id if prompted.

> <img src="./media/image29.png" style="width:6.26806in;height:3.58056in"
> alt="A screenshot of a login box Description automatically generated" />

12. Select **Real Estate Properties** for table name.

13. Select **Show all**.

14. Enter +++contoso_bedrooms eq+++ in the **Filter Rows** field.

15. Use **Dynamic content** to select the **Bedrooms** parameter and
    select **Add**.

> <img src="./media/image30.png" style="width:6.26806in;height:3.65347in"
> alt="A screenshot of a computer Description automatically generated" />

16. Select the **Respond to Copilot** action and select **+ Add an
    output**.

> <img src="./media/image31.png" style="width:6.26806in;height:3.18056in"
> alt="A screenshot of a computer Description automatically generated" />

17. Select **Text**.

18. Enter the below details

- **Enter a name** - +++PropertyId+++

- **Enter a value to respond with** - select **Insert Expression** and
  enter the following expression:
  +++first(outputs('List_rows')?\['body/value'\])\['contoso_realestatepropertyid'\]+++

> <img src="./media/image32.png" style="width:4.20855in;height:1.58341in"
> alt="A screenshot of a computer Description automatically generated" />

19. Select **Add**.

> <img src="./media/image33.png" style="width:3.25017in;height:4.64607in"
> alt="A screenshot of a computer Description automatically generated" />

20. Select **+ Add an output**.

21. Select **Text**.

- **Enter a name** - +++PropertyName+++ 

- **Enter a value to respond with** - select **Insert Expression** and
  enter the following expression:
  +++first(outputs('List_rows')?\['body/value'\])\['contoso_propertyname'\]+++

> <img src="./media/image34.png" style="width:6.26806in;height:3.64931in"
> alt="A screenshot of a computer Description automatically generated" />

22. Select **Settings**. Ensure that **Asynchronous Response** is set
    to **Off**.

> <img src="./media/image35.png" style="width:5.33361in;height:4.53496in"
> alt="A screenshot of a computer Description automatically generated" />

23. Select **Save draft**.

> <img src="./media/image36.png" style="width:6.26806in;height:2.91944in"
> alt="A screenshot of a computer Description automatically generated" />

24. Once save, select **Publish**.

> <img src="./media/image37.png" style="width:6.26806in;height:2.91944in"
> alt="A screenshot of a computer Description automatically generated" />

25. Close the Power Automate tab.

### Task 2: Add a Copilot action for retrieving a property

1.  Back in the Copilot Studio page, select **Refresh**.

> <img src="./media/image38.png" style="width:6.26806in;height:2.99931in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **Get Property** flow.

> <img src="./media/image39.png" style="width:5.7503in;height:4.64607in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select **Next** in the **Choose an action** screen**.**.

> <img src="./media/image40.png" style="width:5.61834in;height:4.58357in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Select **Next** in the **Review inputs and outputs** screen.

> <img src="./media/image41.png" style="width:5.68779in;height:4.6044in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Select **Finish** in the **Review and finish** screen.

> <img src="./media/image42.png" style="width:5.51417in;height:4.56273in"
> alt="A screenshot of a computer Description automatically generated" />

6.  Select the **Topics** tab. And select the **Book a Real Estate
    Showing** topic.

> <img src="./media/image43.png" style="width:6.26806in;height:4.17222in"
> alt="A screenshot of a computer Description automatically generated" />

7.  Select the **+** icon below the **How many bedrooms do you need
    question?** node and select **Call an action**. Select the **Get
    Property** flow.

> <img src="./media/image44.png" style="width:6.24338in;height:4.56273in"
> alt="A screenshot of a computer Description automatically generated" />

8.  Select the **NumberofBedrooms** variable for the **Bedrooms** input
    parameter.

> <img src="./media/image45.png" style="width:3.85436in;height:4.58357in"
> alt="A screenshot of a computer Description automatically generated" />

9.  Select the **three dots** in the **Which property do you want to
    see?** question node and select **Delete**.

> <img src="./media/image46.png" style="width:4.81275in;height:3.85436in"
> alt="A screenshot of a computer Description automatically generated" />

10. Select the the **+** icon under the action node and select **Send a
    message**.

11. Fill in the below details

- **Enter a message** - enter +++Property+++

- Select the **Insert variable** icon and select
  the **PropertyName** variable.

> <img src="./media/image47.png" style="width:6.20865in;height:4.53496in"
> alt="A screenshot of a computer Description automatically generated" />

12. Select **Save**.

<img src="./media/image48.png" style="width:6.26806in;height:3.38611in"
alt="A screenshot of a computer Description automatically generated" />

13. Once saved, select **Publish** and select **Publish**.

> <img src="./media/image49.png" style="width:6.26806in;height:3.025in"
> alt="A screenshot of a computer Description automatically generated" />

14. Click on Publish in the Publish confirmation dialog.

<img src="./media/image50.png" style="width:4.72941in;height:1.20145in"
alt="A close-up of a white background Description automatically generated" />

### Task 3: Create Power Automate flow to make a booking

1.  Select the **Actions** tab and select **+ Add an action**.

<img src="./media/image51.png" style="width:6.26806in;height:3.27153in"
alt="A screenshot of a computer Description automatically generated" />

2.  Scroll down and select **Create a new flow**.

<img src="./media/image52.png" style="width:5.57668in;height:4.58357in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Run a flow from Copilot** in the top-left of the screen and
    enter Create +++**Booking Request**+++ as the flow name.

<img src="./media/image53.png" style="width:6.26806in;height:3.69375in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select the trigger step **Run a flow from Copilot** and select **+
    Add an input -\> Text**.

<img src="./media/image54.png" style="width:6.26806in;height:3.34236in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image55.png" style="width:6.26806in;height:2.97222in"
alt="A screenshot of a computer Description automatically generated" />

5.  Enter the below details

- Input - +++**PropertyId**+++

- Please enter your input **-** +++**Property**+++

6.  Select **+ Add an input -\> Text**

- Input - +++**ViewerName**+++

- Please enter your input **-** +++**Viewer Name**+++

7.  Select **+ Add an input -\>** **Text**.

- Input - +++**ViewerEmail**+++

- Please enter your input **-** +++**Viewer Email**+++

<img src="./media/image56.png" style="width:6.26806in;height:3.74444in"
alt="A screenshot of a computer Description automatically generated" />

8.  Select the **+** icon between the two steps in the flow and
    select **Add an action**.

<img src="./media/image57.png" style="width:3.26406in;height:2.25012in"
alt="A screenshot of a computer Description automatically generated" />

9.  Enter +++**Dataverse**+++ in the **Search** field and select **See
    more** for the Dataverse connector.

<img src="./media/image58.png" style="width:6.25032in;height:4.5419in"
alt="A screenshot of a computer Description automatically generated" />

10. Select the **Add a new row** action.

<img src="./media/image59.png" style="width:6.22949in;height:4.49329in"
alt="A screenshot of a computer Description automatically generated" />

11. Select **Booking Requests** for table name.

12. Enter +++**Copilot booking**+++ in the **Booking Name** field.

13. Select **Show all**.

<img src="./media/image60.png" style="width:4.89608in;height:4.49329in"
alt="A screenshot of a computer Description automatically generated" />

14. Enter +++contoso_bookingrequests()+++ in the **Property (Real Estate
    Properties)** field, move the cursor within the brackets, and
    use **Dynamic content**.

<img src="./media/image61.png" style="width:3.56268in;height:3.85436in"
alt="A screenshot of a computer Description automatically generated" />

15. Select the **PropertyId** parameter.

<img src="./media/image62.png" style="width:6.26806in;height:3.55417in"
alt="A screenshot of a computer Description automatically generated" />

16. Use **Dynamic content** to select the **ViewerName** parameter for
    the **Viewer Name** field.

<img src="./media/image63.png" style="width:6.26806in;height:3.59583in"
alt="A screenshot of a computer Description automatically generated" />

17. Use **Dynamic content** to select the **ViewerEmail** parameter for
    the **Viewer Email** field.

<img src="./media/image64.png" style="width:6.26806in;height:3.59028in"
alt="A screenshot of a computer Description automatically generated" />

18. The parameters will now look similar to those in the screenshot
    below.

<img src="./media/image65.png" style="width:4.52107in;height:4.5419in"
alt="A screenshot of a computer Description automatically generated" />

19. Select the **Respond to Copilot** action. Select **Settings** and
    ensure that **Asynchronous Response** is set to **Off**.

<img src="./media/image66.png" style="width:6.26806in;height:3.52569in"
alt="A screenshot of a computer Description automatically generated" />

20. Select **Save draft**.

<img src="./media/image67.png" style="width:6.26806in;height:2.72708in"
alt="A screenshot of a computer Description automatically generated" />

21. Once saved, select **Publish**.

<img src="./media/image68.png" style="width:6.26806in;height:2.83264in"
alt="A screenshot of a computer Description automatically generated" />

22. Close the Power Automate tab.

### Task 4: Add a Copilot action for creating a booking request

1.  Back in the Copilot Studio page, select **Refresh**.

<img src="./media/image69.png" style="width:5.58362in;height:4.59746in"
alt="A screenshot of a computer Description automatically generated" />

2.  Select the **Create Booking Request** flow.

<img src="./media/image70.png" style="width:5.58362in;height:4.63913in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Next** in the Choose an option screen.

<img src="./media/image71.png" style="width:5.63918in;height:4.6044in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **Next** in the Review inputs and outputs .

<img src="./media/image72.png" style="width:5.66001in;height:4.6044in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **Finish** in the **Review and finish** screen.

<img src="./media/image73.png" style="width:5.66001in;height:4.58357in"
alt="A screenshot of a computer Description automatically generated" />

6.  Select the **Topics** tab and select the **Book a Real Estate
    Showing** topic.

<img src="./media/image74.png" style="width:6.26806in;height:3.79722in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select the the **+** icon below the **What date and time do you want
    to see the property?** node and select **Call an action**.

8.  Select the **Booking Request** flow.

<img src="./media/image75.png" style="width:6.26806in;height:4.36736in"
alt="A screenshot of a computer Description automatically generated" />

9.  Select the **PropertyId** variable for the **PropertyId** input
    parameter.

Select the **Name** variable for the **ViewerName** input parameter.

Select the **EmailAddress** variable for the **ViewerEmail** input
parameter.

> <img src="./media/image76.png" style="width:6.04198in;height:4.56273in"
> alt="A screenshot of a computer Description automatically generated" />

10. Select the the **+** icon below the action node. Select **Topic
    management**, then select **Go to another topic** and select **End
    of conversation**.

<img src="./media/image77.png" style="width:6.26806in;height:3.97639in"
alt="A screenshot of a computer Description automatically generated" />

11. Select **Save**.

<img src="./media/image78.png" style="width:6.26806in;height:4.08056in"
alt="A screenshot of a computer Description automatically generated" />

12. Once saved, select **Publish** and select **Publish** again in the
    confirmation dialog.

<img src="./media/image79.png" style="width:6.26806in;height:2.41667in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image80.png" style="width:5.1461in;height:1.54175in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 3: Test the copilot 

### Task 1: Test the copilot and make a booking request

1.  Select the **Test** button in the top-right of the screen to open
    the testing panel. Select the **three dots** at the top of the
    testing panel in the top-right of the screen. Select **Track between
    topics**.

> <img src="./media/image81.png" style="width:5.85592in;height:4.05944in"
> alt="A screenshot of a computer Description automatically generated" />

2.  When the **Conversation Start** message appears, your copilot starts
    a conversation.

3.  When the **Conversation Start** message appears, your copilot starts
    a conversation.

4.  In response, enter a trigger phrase for the topic that you created:

+++I want to book a real estate showing+++

5.  The copilot responds with the "**What is your name?**" question.

6.  Enter your name.

> <img src="./media/image82.png" style="width:2.47235in;height:4.43773in"
> alt="A screenshot of a chat Description automatically generated" />

7.  Then enter your email when it prompts for the email. After you enter
    the details, an Adaptive Card displays the information that you
    entered, a question asking if the information is correct, and
    options to select **Yes** or **No**. Select **Yes**.

> <img src="./media/image83.png" style="width:2.62513in;height:4.6044in"
> alt="A screenshot of a phone Description automatically generated" />

8.  Select **House** for the type of property prompt.

9.  Enter +++**2**+++ for the number of bedrooms prompts.

<img src="./media/image84.png" style="width:2.68069in;height:4.62524in"
alt="A screenshot of a chat Description automatically generated" />

10. Enter Tomorrow 2:00 PM to the **What date and time do you want to
    see the property?** prompt.

11. Select **Yes** to the **Did that answer your question?** prompt.

12. Select any rating.

13. Select **No** to the **Can I help with anything else?** prompt.

> <img src="./media/image85.png" style="width:2.65986in;height:4.62524in"
> alt="A screenshot of a chat Description automatically generated" />

### Task 2: Verify booking request

1.  Navigate to the Power Apps portal at
    +++**https://make.powerapps.com**+++.

2.  In the left navigation pane, select **Tables** and
    select **Custom**.

3.  Select the **Booking Request** table.

<img src="./media/image86.png" style="width:6.26806in;height:3.38472in"
alt="A screenshot of a computer Description automatically generated" />

4.  Under **Booking Request columns and data** you should see that a
    Copilot booking request is now created.

<img src="./media/image87.png" style="width:6.26806in;height:4.06319in"
alt="A screenshot of a computer Description automatically generated" />

## Exercise 4: Set up Generative AI

In this exercise, you learn how to use the Generative answers feature to
improve your copilot's responses.

### Task 1: Enable Generative AI

1.  Login to the Copilot Studio using your tenant credentials at
    +++<https://copilotstudio.microsoft.com>+++ if not logged in
    already.

2.  Select the Copilot **Real Estate Booking Service**.

> <img src="./media/image88.png" style="width:6.26806in;height:2.13889in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select **Settings** in the top-right of the screen.

> <img src="./media/image89.png" style="width:6.26806in;height:2.125in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Select the **Generative AI** tab.

> Select **Generative** under **How should your copilot decide how to
> respond**.
>
> Select **Medium** for **Copilot content moderation**.
>
> Select **Save**.
>
> <img src="./media/image90.png" style="width:6.26806in;height:2.54375in"
> alt="A screenshot of a computer Description automatically generated" />

5.  **Close** the Settings pane.

<img src="./media/image91.png" style="width:6.26806in;height:2.58889in"
alt="A screenshot of a computer Description automatically generated" />

### Task 2: Enable knowledge

1.  Select your copilot in the Copilot pane on the left-hand side of the
    screen to return to the **Overview** tab.

2.  Verify that general knowledge is enabled in the Knowledge section.

> <img src="./media/image92.png" style="width:4.1391in;height:4.58357in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 3: Add knowledge from a website

1.  Select **+ Add knowledge** under the **Knowledge** section in the
    Overview page of the copilot.

> <img src="./media/image93.png" style="width:4.20855in;height:4.64607in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **Public websites** tile.

> <img src="./media/image94.png" style="width:6.26806in;height:4.04514in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Enter the public website
    link +++https://create.microsoft.com/templates/real-estate+++.
    Select **Add**.

> <img src="./media/image95.png" style="width:6.26806in;height:4.07569in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Give the name +++ Real Estate Website+++ in the Name field and then
    select **Add**.

> <img src="./media/image96.png" style="width:6.26806in;height:4.075in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 4: Add knowledge from Dataverse

1.  Select the **Knowledge** tab. Select **+ Add knowledge**.

> <img src="./media/image97.png" style="width:6.26806in;height:3.675in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select **Dataverse**.

> <img src="./media/image98.png" style="width:6.26806in;height:4.0375in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select the **Real Estate Property** table and select **Next**.

> <img src="./media/image99.png" style="width:6.26806in;height:4.15417in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Preview the data in the next screen and then select **Next**.

> <img src="./media/image100.png" style="width:6.26806in;height:4.11111in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Review the details and click on **Add** in the Review and finish
    screen.

> <img src="./media/image101.png" style="width:6.26806in;height:4.14792in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 5: Add knowledge from files

1.  From the **Knowledge** tab, select **+ Add knowledge**.

> <img src="./media/image102.png" style="width:6.20865in;height:3.22933in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select **Files**.

> <img src="./media/image103.png" style="width:6.26806in;height:4.03889in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select Click to browse and browse to locate the file
    **SummitRealtyCaseStudy.docx** at **C:\LabFiles** and select it.

> <img src="./media/image104.png" style="width:6.26806in;height:4.14514in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Select **Add**.

> <img src="./media/image105.png" style="width:6.26806in;height:4.13889in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 6: Use generative answers in System fallback topic

1.  Select the **Topics** tab and select **System**. Select
    the **Fallback** topic.

> <img src="./media/image106.png" style="width:4.59746in;height:4.64607in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **three dots** in the message node and select **Delete**.

> <img src="./media/image107.png" style="width:4.4794in;height:4.58357in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select the **+** icon under the Condition node, select **Advanced**,
    and select **Generative answers**.

> <img src="./media/image108.png" style="width:4.75024in;height:4.58357in"
> alt="A screenshot of a computer screen Description automatically generated" />

4.  Select the **Input** field, select **System** in the **Select a
    variable** pane. Select **Activity.Text** from it.

> <img src="./media/image109.png" style="width:5.95864in;height:3.97243in"
> alt="A screenshot of a computer Description automatically generated" />

5.  Select **Edit** under **Data sources**.

> <img src="./media/image110.png" style="width:4.99331in;height:4.62524in"
> alt="A screenshot of a computer Description automatically generated" />

6.  Select **Search only selected sources**.

> <img src="./media/image111.png" style="width:4.39606in;height:4.63913in"
> alt="A screenshot of a computer Description automatically generated" />

7.  Select the **SummitRealtyCaseStudy** document. Deselect **Allow the
    AI to use its own general knowledge**.
    Select **Medium** for **Content moderation**.

> <img src="./media/image112.png" style="width:4.56273in;height:4.66691in"
> alt="A screenshot of a computer Description automatically generated" />

8.  Select **Save**.

> <img src="./media/image113.png" style="width:5.62529in;height:4.41689in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 7: Configure Security

1.  Select your copilot in the Copilot pane on the left-hand side of the
    screen to return to the **Overview** tab.

2.  From the copilot page top menu, click on **Channels** (If the
    Channels is not visible, click on the +1 to view the **Channels**
    option)

<img src="./media/image114.png" style="width:6.26806in;height:4.43056in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Dynamics 365 Customer Service** from the Customer
    engagement hub pane.

<img src="./media/image115.png" style="width:6.26806in;height:4.40556in"
alt="A screenshot of a computer Description automatically generated" />

4.  On the Dynamics 365 Customer Service page, click on **Disconnect**.

<img src="./media/image116.png" style="width:3.51407in;height:4.66691in"
alt="A screenshot of a phone Description automatically generated" />

5.  Once done, **close** the Dynamics 365 Customer Service pane.

> <img src="./media/image117.png" style="width:3.60435in;height:4.70163in"
> alt="A screenshot of a phone Description automatically generated" />

6.  Select **Settings** in the top-right of the screen.

> <img src="./media/image118.png" style="width:6.26806in;height:2.59931in"
> alt="A screenshot of a computer Description automatically generated" />

7.  Select the **Security** tab and then select
    the **Authentication** tile.

> <img src="./media/image119.png" style="width:5.47945in;height:4.0766in"
> alt="A screenshot of a computer Description automatically generated" />

8.  Select Authenticate with Microsoft **(Entra ID authentication in
    Teams and Power App)**.

9.  Select **Save**.

> <img src="./media/image120.png" style="width:6.26806in;height:3.94097in"
> alt="A screenshot of a computer Description automatically generated" />

10. Select **Save**.

> <img src="./media/image121.png" style="width:4.82664in;height:3.16683in"
> alt="A screenshot of a computer Description automatically generated" />

11. Select **Close**.

> <img src="./media/image122.png" style="width:6.26806in;height:2.69792in"
> alt="A screenshot of a computer Description automatically generated" />

12. Select your copilot in the Copilot pane on the left-hand side of the
    screen to return to the **Overview** tab.

13. Select **Publish** and select **Publish**.

> <img src="./media/image123.png" style="width:6.26806in;height:2.18056in"
> alt="A screenshot of a computer Description automatically generated" />

### Task 8: Test the copilot's knowledge

1.  Select the **Test** button in the top-right of the screen to open
    the testing panel.

> <img src="./media/image124.png" style="width:6.26806in;height:4.24931in"
> alt="A screenshot of a computer Description automatically generated" />

2.  Select the **three dots** at the top of the testing panel in the
    top-right of the screen.

3.  Select **Track between topics**.

4.  Select the **Start a new conversation** icon at the top of the
    testing panel.

5.  Explore the copilot and see how it uses the different knowledge
    sources.

**Summary:**

In this lab, we have learnt to

- Use entities and slot filling

- Implement Flow actions

- Add knowledge to the copilot

- Enable Generative AI
