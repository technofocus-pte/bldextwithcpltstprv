# **Lab 12\_ Sending messages from a Copilot(classic) to a Teams channel**

**Lab duration** – 30 minutes

**Objective:**

In this lab, we will send message from a Copilot to a Teams channel by
invoking a flow.

## **Exercise 1: Add channel and Team**

1.  Open Microsoft Teams from the VM and login using your tenant
    credentials if not done already. Select Teams option.

<img src="./media/image1.png" style="width:6.5in;height:3.91042in"
alt="A screenshot of a computer Description automatically generated" />

2.  From the Teams, select **More options** and select **+ -\>**
    **Create team**.

<img src="./media/image2.png" style="width:3.24195in;height:3.60865in"
alt="A screenshot of a computer Description automatically generated" />

3.  Name the team as +++**HR Team**+++ and select **Create**.

<img src="./media/image3.png" style="width:5.3338in;height:5.31713in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **Skip** on ‘Add members to HR Team’ window.

<img src="./media/image4.png" style="width:6.5in;height:6.44236in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **More options** (…) infront of the **HR Team** and then
    select under **Add channel.**

<img src="./media/image5.png"
style="width:5.42784in;height:8.07404in" />

6.  Provide the Channel name as +++**HR Experts**+++. Choose the Privacy
    as **Private** and click on **Create**.

<img src="./media/image6.png" style="width:6.5in;height:4.8625in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select **Skip** on ‘Add members to the HR Experts channel’ window.

<img src="./media/image7.png" style="width:6.5in;height:4.81528in"
alt="A screenshot of a computer Description automatically generated" />

## **Exercise 2: Enhance topic to handle complex queries by escalating to HR experts**

1.  From the Teams app, select the Copilot Studio app(Power Virtual
    Agents), select **Copilots** tab and open the **HR Support
    Copilot**.

> <img src="./media/image8.png" style="width:6.5in;height:3.82222in" />
>
> **Note:** If Copilot Studio shortcut is not found, search for
> **Copilot Studio/Power Virtual Agents under Apps** and select
> **Open**)

2.  Select **Topics** from left pane and return to the topic you created
    earlier(**Employee time off**) and go to the authoring canvas.

> <img src="./media/image9.png" style="width:6.5in;height:3.57986in"
> alt="A screenshot of a chat Description automatically generated" />

3.  In the **Ask a question node**, add an option named **Extended
    leave**.

> <img src="./media/image10.png" style="width:3.23361in;height:4.80875in"
> alt="A screenshot of a computer Description automatically generated" />

4.  Under the Condition node of Extended leave, add a question node
    asking for a description for the issue and add the text +++**How
    would you describe the issue?***+++*

> <img src="./media/image11.png" style="width:6.5in;height:3.62986in" />

5.  Select **User’s entire response** under Identity and save the
    description in a variable named +++**Description**+++.

> <img src="./media/image12.png" style="width:3.80866in;height:3.29195in"
> alt="A screenshot of a computer screen Description automatically generated" />

6.  Select **Save**.

<img src="./media/image13.png" style="width:6.5in;height:3.27014in"
alt="A screenshot of a computer Description automatically generated" />

7.  Add a node under the question and select **Call an action**. Select
    **Create a flow** which launches the Power Automate within the
    Copilot Studio in Teams.

<img src="./media/image14.png" style="width:6.5in;height:3.84931in"
alt="A screenshot of a computer Description automatically generated" />

8.  Choose the **Power Virtual Agents Flow** Template option.

<img src="./media/image15.png" style="width:6.5in;height:3.97708in" />

<img src="./media/image16.png" style="width:6.5in;height:3.53889in"
alt="A screenshot of a computer Description automatically generated" />

9.  Add a **Text** input field by clicking on **+ Add an input** in the
    first step. Replace the Input by **Description**.

<img src="./media/image17.png" style="width:6.5in;height:1.79583in"
alt="A computer screen shot of a computer error Description automatically generated" />

10. Insert a **new step** and select **Add an action**.

<img src="./media/image18.png" style="width:6.5in;height:3.67847in" />

<img src="./media/image19.png" style="width:6.5in;height:2.99931in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image20.png" style="width:6.5in;height:3.03889in"
alt="A screenshot of a computer Description automatically generated" />

11. Select **Microsoft Teams** under **Choose an operation**.

<img src="./media/image21.png" style="width:6.5in;height:3.77847in" />

12. Select **Post message in a chat or channel**.

<img src="./media/image22.png" style="width:6.5in;height:3.80694in" />

13. Provide the below details:

- Post as – **User**

- Post in – **Channel**

- Team – **HR Team**

- Channel – **HR Experts**

- Message **– Description** from **Dynamic Content**

<img src="./media/image23.png" style="width:6.5in;height:4.29375in"
alt="A screenshot of a computer Description automatically generated" />

14. Rename the flow as +++**Send a message to HR team**+++ and click on
    **Save**.

> <img src="./media/image24.png" style="width:6.5in;height:3.36389in"
> alt="A screenshot of a computer Description automatically generated" />

15. Click on **Close** to close the Power Automate and return to the
    Authoring canvas.

<img src="./media/image25.png" style="width:6.5in;height:1.83194in"
alt="A screenshot of a computer Description automatically generated" />

16. From the Authoring canvas, add a node – **call an action** -\>
    **Send a message to HR team**.

<img src="./media/image26.png" style="width:6.5in;height:3.90347in"
alt="A screenshot of a computer Description automatically generated" />

17. Add in the input as **Description**.

<img src="./media/image27.png" style="width:5.00043in;height:3.61698in"
alt="A screenshot of a computer Description automatically generated" />

18. Add in a message node with the message, +++**We notified the expert.
    They’ll reach out shortly**+++.

<img src="./media/image28.png" style="width:4.60873in;height:2.36687in"
alt="A screenshot of a computer Description automatically generated" />

19. End the conversation \> End the survey.

<img src="./media/image29.png" style="width:4.79208in;height:2.43354in"
alt="A screenshot of a chat Description automatically generated" />

20. Click on **Save** to save the topic.

<img src="./media/image30.png" style="width:6.5in;height:1.76319in"
alt="A screenshot of a computer Description automatically generated" />

21. A success message of **Topic saved** is obtained.

<img src="./media/image31.png" style="width:6.5in;height:1.94931in"
alt="A screenshot of a computer Description automatically generated" />

## **Exercise 3: Test your chatbot**

1.  Select Test your chatbot from the left pane.

<img src="./media/image32.png" style="width:2.90858in;height:5.36713in"
alt="A screenshot of a computer Description automatically generated" />

2.  Send a message +++**I need help with time off**+++ and select
    Extended leave to answer the chatbot.

<img src="./media/image33.png" style="width:4.12536in;height:5.36713in"
alt="A screenshot of a chat Description automatically generated" />

3.  Describe a reason for your leave extension. Here, we have given it
    as +++**I need extended leave of one month for travelling**+++.

<img src="./media/image34.png" style="width:4.14203in;height:4.45039in"
alt="A screenshot of a chat Description automatically generated" />

4.  The bot replies with “We notified an expert…..” message.

<img src="./media/image35.png" style="width:4.51706in;height:4.70041in"
alt="A screenshot of a chatbot Description automatically generated" />

> <img src="./media/image36.png" style="width:3.12918in;height:4.03436in"
> alt="A screenshot of a chat Description automatically generated" />

## **Exercise 4: Check the message in Teams.**

1.  Click on Teams from the left menu of the MS Teams app.

<img src="./media/image37.png"
style="width:3.57531in;height:5.30879in" />

2.  Select the **HR Experts** channel under the **HR Team** team. Notice
    that the message from the user to the bot has been sent here.

<img src="./media/image38.png" style="width:6.5in;height:4.90139in"
alt="A screenshot of a computer Description automatically generated" />

## **Exercise 5: Publish your copilot – Teams**

1.  Go back to Microsoft Copilot Studio app. Select the chatbot **HR
    Support Copilot**.

2.  Select Publish from the left pane.

<img src="./media/image39.png" style="width:4.97543in;height:3.867in"
alt="A screenshot of a chat Description automatically generated" />

3.  Click on **Publish**.

<img src="./media/image40.png" style="width:6.5in;height:2.66736in" />

4.  Select Publish in the **Publish latest content?**

<img src="./media/image41.png" style="width:5.4088in;height:1.45013in"
alt="A close-up of a computer screen Description automatically generated" />

5.  Success message is obtained as in the screenshot below. Click on the
    **Availability options**.

<img src="./media/image42.png" style="width:6.1672in;height:5.36713in"
alt="A screenshot of a computer Description automatically generated" />

6.  The **Add to Contoso** option adds the bot to the specific team.

7.  **Show to my team mates and shared users** makes the bot to appear
    under the Built by colleagues section.

8.  **Show to everyone in the org** submits the request to the admin to
    get the bot listed under the **Built by org** section.

<img src="./media/image43.png" style="width:6.5in;height:6.19792in"
alt="A screenshot of a computer Description automatically generated" />

**Summary:**

In this lab, we have learnt to post a message to the Teams channel from
the bot.
