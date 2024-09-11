# **Lab 04_Creating and deploying a Microsoft Copilot Studio copilot from Teams**

**Lab duration** – 30 minutes

**Objective:**

In this lab, you will Install the Copilot Studio app in Microsoft Teams,
create a new copilot in a team and test it.

## **Exercise 1: Install the Copilot Studio app in Microsoft Teams**

1.  Open the link
    +++https://www.microsoft.com/en-in/microsoft-teams/download-app+++
    From a browser. Click on **Download the new Teams app** -\>
    **Download for Windows (64-bit)**

<img src="./media/image1.png" style="width:6.5in;height:5.11944in"
alt="A screenshot of a computer Description automatically generated" />

2.  **Double click** on the **downloaded file** to install the Teams for
    School app.

3.  Follow the prompts to install.

4.  Once installed, **Sign in** using your **office 365 tenant
    credentials**.

> <img src="./media/image2.png" style="width:5.90885in;height:5.14211in"
> alt="A screenshot of a sign in Description automatically generated" />

5.  Click on **Apps**. Search for +++**Copilot Studio**+++ and select
    **Microsoft Copilot Studio** and click on **Add**.

**Note:** If you are not able to find Copilot Studio, you will have to
search for and select **Power Virtual agent** and add it.

<img src="./media/image3.png" style="width:6.5in;height:3.91597in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image4.png" style="width:6.5in;height:3.98264in" />

6.  Click on **Start now**.

<img src="./media/image5.png" style="width:6.5in;height:5.07917in"
alt="A screenshot of a computer Description automatically generated" />

## **Exercise 2: Create a new copilot in a team**

1.  Select **Contoso** and click on **Continue**.

<img src="./media/image6.png" style="width:4.9921in;height:5.28379in"
alt="A screenshot of a chatbot Description automatically generated" />

<img src="./media/image7.png" style="width:6.1172in;height:6.4839in"
alt="A screenshot of a chatbot Description automatically generated" />

2.  In the Create a copilot pane, provide the name of the Copilot as
    +++**HR Support Copilot**+++ and click on **Create**.

<img src="./media/image8.png" style="width:6.5in;height:4.70972in"
alt="A screenshot of a computer Description automatically generated" />

3.  A success message stating, **Your chatbot is provisioned** is
    obtained.

<img src="./media/image9.png" style="width:6.5in;height:2.99792in" />

## **Exercise 3: Build an employee time-off topic for common time-off queries**

1.  Click on **Topics** from the left pane. Click on **+ New topic -\>
    From blank.**

<img src="./media/image10.png" style="width:6.5in;height:1.98958in"
alt="A screenshot of a computer Description automatically generated" />

2.  Click on the **Details** icon.

<img src="./media/image11.png" style="width:6.5in;height:2.33264in"
alt="A screenshot of a computer Description automatically generated" />

3.  In the Details pane, provide the name as +++**Employee time off**+++
    and Description as +++**Employee time off topic for common time-off
    queries**+++.

<img src="./media/image12.png" style="width:3.26695in;height:4.40038in"
alt="A screenshot of a computer Description automatically generated" />

4.  Click on **Save**.

<img src="./media/image13.png" style="width:6.5in;height:1.82986in" />

5.  Click on the **Trigger phases.**

<img src="./media/image14.png" style="width:3.74199in;height:1.89183in"
alt="A screenshot of a computer Description automatically generated" />

6.  Add in a trigger phrase, +++**I need help with time off**+++ and
    click on **+.**

<img src="./media/image15.png"
style="width:6.50069in;height:3.79375in" />

7.  Add in the below trigger phrases.

- +++**Need information on time off**+++

- +++**I need help with time off**+++

- +++**How many days of paid vacation do I have**+++

- +++**What are the national holidays**+++

- +++**I need extended leave**+++

<img src="./media/image16.png" style="width:6.5in;height:5.51319in"
alt="A screenshot of a computer Description automatically generated" />

8.  Add a Message node and enter the text, +++I can help with questions
    related to time-off*+++*.

9.  As an HR employee, you know the most common time-off questions are
    about paid vacation time and national holidays. When a question node
    with user response options is added, the topic automatically gets a
    forked branch for each response.

10. Select the (**+**) icon below the message node, then select **Ask a
    question** to add a question node to the topic.

11. Enter *What information are you looking for?* in the **Ask a
    question** text box. The employee might ask this question.

> <img src="./media/image17.png" style="width:4.22537in;height:5.4088in"
> alt="A screenshot of a chat Description automatically generated" />

12. Under **Options for user**, add +++Paid
    vacation*+++* and +++National Holidays*+++* as two options.

> <img src="./media/image18.png" style="width:3.61698in;height:4.61707in"
> alt="A screenshot of a questionnaire Description automatically generated" />

13. User choices are stored in a variable and the topic branches off,
    based on the option the user chooses. You can rename the variable to
    track it better in the topic.

14. On the variable, under **Save response as**, select the pencil icon
    to edit the variable properties.

15. The **Variable properties** pane opens. Rename the variable
    to +++TimeoffType*+++*. Close the **Variable properties** pane and
    you see the changes reflected in the authoring canvas.

> <img src="./media/image19.png" style="width:5.39213in;height:5.03377in"
> alt="A screenshot of a computer Description automatically generated" />

16. Add a message node for the Paid vacation branch with this message to
    the user: +++**For paid vacation time-off, go to
    www.contoso.com/HR/PaidTimeOff**+++ to submit time-off requests.

<img src="./media/image20.png" style="width:4.24203in;height:5.45881in"
alt="A screenshot of a computer Description automatically generated" />

17. Add a node by selecting the (**+**) icon to end the conversation
    with a survey. Select **End the conversation**, then **End with
    survey**. This survey is the customer satisfaction survey prebuilt
    in the copilot for use in topics.

> <img src="./media/image21.png" style="width:4.07535in;height:4.00035in"
> alt="A screenshot of a chat Description automatically generated" />

18. In the **National Holidays** path, add a message node with the
    following text:

> National holidays for 2020:

1.  New Year's Day: January 1st

2.  Memorial Day: May 25th

3.  Independence day: July 4th

4.  Labor Day: September 7th

5.  Thanksgiving: November 26th - 27th

6.  Christmas Eve and Christmas Day: December 24th - 25th

<img src="./media/image22.png" style="width:3.73366in;height:5.57548in"
alt="A screenshot of a calendar Description automatically generated" />

19. Click on **Save**.

<img src="./media/image23.png" style="width:3.15861in;height:1.9335in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image24.png"
style="width:5.93622in;height:8.92279in" />

## **Exercise 4: Test copilot for expected behavior**

1.  Select the copilot icon at the bottom of the screen to launch the
    test copilot canvas.

2.  Type **I need time off information** into the copilot chat.

3.  Select **Paid vacation**.

4.  You receive the response as per our configuration.

> <img src="./media/image25.png" style="width:3.90034in;height:5.60049in"
> alt="A screenshot of a chat Description automatically generated" />
>
> <img src="./media/image26.png" style="width:3.65032in;height:3.57531in"
> alt="A screenshot of a chat Description automatically generated" />
>
> **Summary:**
>
> In this lab, we have learnt to add the Copilot Studio app to Teams and
> create a classic bot in Teams.
