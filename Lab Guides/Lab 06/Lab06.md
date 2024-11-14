# **Lab 06 - Sending messages from a Copilot(classic) to a Teams channel**

**Lab duration** – 30 minutes

**Objective:**

In this lab, we will send message from a Copilot to a Teams channel by
invoking a flow.

## **Exercise 1: Add channel and Team in Microsoft Teams**

1.  Open **Microsoft Teams** from the VM and login using your tenant
    credentials if you have closed it already. Select **Teams** option.

    ![](./media/image1.png)

2.  From the Teams, select **More options** and select **+ -\>**
    **Create team**.

    ![](./media/image2.png)

3.  Name the team as !!**HR Team**!!, channel as !!**HR Experts**!!
    and select **Create**.

    ![](./media/image3.png)

4.  Select **Skip** on ‘Add members to HR Team’ window.

    ![](./media/image4.png)

5.  Select **Skip** on ‘Add members to the HR Experts channel’ window.

    ![](./media/image5.png)

## **Exercise 2: Enhance topic to handle complex queries by escalating to HR experts**

1.  From the Teams app, select the Copilot Studio app(Power Virtual
    Agents), select **Copilots** tab and open the **HR Support
    Copilot**.

    ![](./media/image6.png)

    >[!Note] **Note:** If Copilot Studio shortcut is not found, search for **Copilot Studio/Power Virtual Agents under Apps** and select **Open**)

    ![](./media/image7.png)

2.  Select **Topics** from left pane and return to the topic you created
    earlier(**Employee time off**) and go to the authoring canvas.

    ![](./media/image8.png)

3.  In the **Ask a question node**, add an option named **Extended
    leave**.

    ![](./media/image9.png)

4.  Under the Condition node of Extended leave, add a question node
    asking for a description for the issue and add the text !!**How
    would you describe the issue?***!!*

    ![](./media/image10.png)

5.  Select **User’s entire response** under Identity and save the
    description in a variable named !!**Description**!!.

    ![](./media/image11.png)

6.  Select **Save**.

    ![](./media/image12.png)

7.  Add a node under the question and select **Call an action**. Select
    **Create a flow** which launches the Power Automate within the
    Copilot Studio in Teams.

    ![](./media/image13.png)

8.  Choose the **Power Virtual Agents Flow** Template option.

    ![](./media/image14.png)

    ![](./media/image15.png)

9.  Add a **Text** input field by clicking on **+ Add an input** in the
    first step. Replace the Input by **Description**.

    ![](./media/image16.png)

10. Insert a **new step** and select **Add an action**.

    ![](./media/image17.png)

11. Select **Microsoft Teams** under **Choose an operation**.

    ![](./media/image18.png)

12. Select **Post message in a chat or channel**.

    ![](./media/image19.png)

13. Provide the below details:

    - Post as – **User**

    - Post in – **Channel**

    - Team – **HR Team**

    - Channel – **HR Experts**

    - Message **– Description** from **Dynamic Content**

    ![](./media/image20.png)

14. Rename the flow as !!**Send a message to HR team**!! and click on
    **Save**.

    ![](./media/image21.png)

15. Click on **Close** to close the Power Automate and return to the
    Authoring canvas.

    ![](./media/image22.png)

16. From the Authoring canvas, add a node – **call an action** -\>
    **Send a message to HR team**.

    ![](./media/image23.png)

17. Add in the input as **Description**.

    ![](./media/image24.png)

18. Add in a message node with the message, !!**We notified the expert.
    They’ll reach out shortly**!!.

    ![](./media/image25.png)

19. End the conversation \> End the survey.

    ![](./media/image26.png)

20. Click on **Save** to save the topic.

    ![](./media/image27.png)

21. A success message of **Topic saved** is obtained.

    ![](./media/image28.png)

## **Exercise 3: Test your chatbot**

1.  Select Test your chatbot from the left pane.

    ![](./media/image29.png)

2.  Send a message !!**I need help with time off**!! and select
    Extended leave to answer the chatbot.

    ![](./media/image30.png)

3.  Describe a reason for your leave extension. Here, we have given it
    as !!**I need extended leave of one month for travelling**!!.

    ![](./media/image31.png)

4.  The bot replies with “We notified an expert…..” message.

    ![](./media/image32.png)

    ![](./media/image33.png)

## **Exercise 4: Check the message in Teams.**

1.  Click on Teams from the left menu of the MS Teams app.

    ![](./media/image34.png)

2.  Select the **HR Experts** channel under the **HR Team** team. Notice
    that the message from the user to the bot has been sent here.

    ![](./media/image35.png)

## **Exercise 5: Publish your copilot – Teams**

1.  Go back to Microsoft Copilot Studio app. Select the chatbot **HR
    Support Copilot**.

2.  Select Publish from the left pane.

    ![](./media/image36.png)

3.  Click on **Publish**.

    ![](./media/image37.png)

4.  Select Publish in the **Publish latest content?**

    ![](./media/image38.png)

5.  Success message is obtained as in the screenshot below. Click on the
    **Availability options**.

    ![](./media/image39.png)

6.  The **Add to Contoso** option adds the bot to the specific team.

7.  **Show to my team mates and shared users** makes the bot to appear
    under the Built by colleagues section.

8.  **Show to everyone in the org** submits the request to the admin to
    get the bot listed under the **Built by org** section.

    ![](./media/image40.png)

**Summary:**

In this lab, we have learnt to post a message to the Teams channel from
the bot.
