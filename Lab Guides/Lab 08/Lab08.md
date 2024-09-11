# **Lab 08 - Extending Microsoft Copilot with connector actions (preview)**

**Lab duration** – 20 minutes

**Objective:**

Connector actions let you define connectors that can be invoked from AI
surfaces in Power Platform. For connector actions, you need to identify
the actions enabled for use in the Copilot. You can also capture the
information that large language models require to effectively identify
and utilize the plugin, such as summary and description fields.

In this lab, we will learn how to add a connector action and publish it.

## **Exercise 1: Add a connector action**

### **Task 1: Select the Copilot experience and choose connector action**

1.  Login to the Copilot Studio at
    +++https://copilotstudio.microsoft.com+++ using your tenant
    credentials if not done already.

2.  On the home page, select **Copilots** and select **Copilot for
    Microsoft 365**.

<img src="./media/image1.png" style="width:3.95854in;height:2.81264in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Actions** and then select **+ Add action**.

<img src="./media/image2.png" style="width:4.72247in;height:1.90982in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **connector**.

<img src="./media/image3.png" style="width:6.5in;height:1.925in"
alt="A screenshot of a computer Description automatically generated" />

5.  Select **SharePoint**.

<img src="./media/image4.png" style="width:6.5in;height:4.44653in"
alt="A screenshot of a computer Description automatically generated" />

6.  The **Add a connector action** pane opens. Accept the defaults and
    click on **Next**.

<img src="./media/image5.png" style="width:6.5in;height:4.49375in"
alt="A screenshot of a computer Description automatically generated" />

7.  Select the **Get lists**, accept the other defaults and click on
    **Next**.

<img src="./media/image6.png" style="width:6.5in;height:4.51736in"
alt="A screenshot of a plugin action Description automatically generated" />

8.  **Review** the action’s parameters and click on **Next**.

<img src="./media/image7.png" style="width:6.5in;height:4.48125in"
alt="A screenshot of a computer Description automatically generated" />

9.  The screen again lands in the Add a connector action to enable
    adding more actions. We can select **Next** since we are adding only
    one action here.

<img src="./media/image8.png" style="width:6.5in;height:4.49167in"
alt="A screenshot of a computer Description automatically generated" />

10. In the Review, test and publish your action screen, click on **+ New
    connection**.

<img src="./media/image9.png" style="width:6.5in;height:4.48889in"
alt="A screenshot of a computer Description automatically generated" />

11. Select **Create**.

<img src="./media/image10.png" style="width:5.56279in;height:3.49323in"
alt="A screenshot of a computer Description automatically generated" />

12. Login using your tenant credentials. Once the connection is
    established, select it (if not automatically selected) and then
    click on **Next**.

<img src="./media/image11.png" style="width:6.5in;height:4.48125in"
alt="A screenshot of a computer Description automatically generated" />

13. In the next screen, your connection action gets published.

<img src="./media/image12.png" style="width:6.5in;height:4.51528in"
alt="A screenshot of a computer Description automatically generated" />

14. Once done, you will get a message stating that the **Your**
    **connector action is now published to Copilot for Microsoft 365**.
    Click on **Go to details page** to see the details.

<img src="./media/image13.png" style="width:6.5in;height:4.52986in"
alt="A screenshot of a computer Description automatically generated" />

Your connector action is now published to **Copilot for Microsoft 365**.
It will show up in copilot experiences only if you have a valid Copilot
license.

**Summary:**

In this lab, we have learnt how to add a connector option, viewed the
different types of actions available and publish it.
