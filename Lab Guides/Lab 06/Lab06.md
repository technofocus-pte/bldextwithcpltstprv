**Lab 06 - Creating conversational actions for Microsoft Copilot**

**Lab duration** – 20 minutes

**Objective**

Microsoft Copilot provides out of the box experiences to engage with
content and resources from across your organization. In some situations,
answers and interaction with external systems are required. With
Microsoft Copilot Studio, you can author a conversational topic that can
be published as a Copilot Plugin. Once your Tenant Admin approves the
Plugin, it can be added to your organization's M365 Chat experiences.

The actions will be available in the Microsoft Copilot in production, if
the organization has valid license for the same.

In this lab, we will learn how to create a Conversational action.

## **Exercise 1: Create a Conversational action**

1.  Login to +++**https://copilotstudio.microsoft.com/**+++ using your
    tenant credentials if not already logged in.

2.  Select **Copilot for Microsoft 365**.

<img src="./media/image1.png" style="width:6.23387in;height:5.16711in"
alt="A screenshot of a computer Description automatically generated" />

3.  Select **Actions**.

<img src="./media/image2.png" style="width:6.26806in;height:3.59444in"
alt="A screenshot of a computer Description automatically generated" />

4.  Select **+ Add an action**.

<img src="./media/image3.png" style="width:5.22545in;height:4.08369in"
alt="A screenshot of a computer program Description automatically generated" />

5.  Select **Conversational** in the **New action** pane.

<img src="./media/image4.png" style="width:6.26806in;height:2.08056in"
alt="A screenshot of a computer Description automatically generated" />

6.  Provide the name for the action as !!**Conversational action**!!.
    Select **Create**.

<img src="./media/image5.png" style="width:4.68374in;height:4.85875in"
alt="A screenshot of a conversational action Description automatically generated" />

<img src="./media/image6.png" style="width:4.53373in;height:4.95876in"
alt="A screen shot of a phone Description automatically generated" />

7.  Once ready, the created action opens in Authoring canvas. Select
    **Topics**.

<img src="./media/image7.png" style="width:5.60049in;height:5.40047in"
alt="A screenshot of a computer Description automatically generated" />

8.  Name the topic as !!Holidaylist!!

<img src="./media/image8.png" style="width:6.5in;height:3.49722in"
alt="A screenshot of a computer Description automatically generated" />

9.  In the Trigger node’s description, provide a clear description of
    how the conversational plugin can help the user and what it can
    do. Let this topic help the user to find the list of holidays in the
    year 2024.

Type +++**This plugin helps to retrieve the list of holidays for the
year 2024.**+++ in the Trigger node’s description.

<img src="./media/image9.png" style="width:6.26806in;height:3.13125in"
alt="A screenshot of a computer Description automatically generated" />

This description has functional purpose and is used by the Microsoft
Copilot to determine whether to invoke your plugin or not.

10. Add a message node with the list of holidays.

    - New Year's Day - January 1

    - Martin Luther King, Jr.'s Birthday (Third Monday of January) -
      January 15, 2024

    - Washington's Birthday or Presidents' Day (third Monday of
      February) - February 19

    - Memorial Day (last Monday of May) - May 27

    - Juneteenth Day - June 19

    - Independence Day - July 4

    - Labor Day (first Monday of September) - September 2

    - Columbus Day (Second Monday of October) - October 14

    - Veterans Day or Veterans Day - November 11

    - Thanksgiving Day (fourth Thursday of November): November 28

    - Christmas Day - December 25

<img src="./media/image10.png" style="width:3.90867in;height:5.49214in"
alt="A screenshot of a calendar Description automatically generated" />

11. Click on **Save** to save the plugin.

<img src="./media/image11.png" style="width:6.26806in;height:2.07847in"
alt="A screenshot of a computer Description automatically generated" />

<img src="./media/image12.png" style="width:5.20878in;height:3.61698in"
alt="A screenshot of a chat box Description automatically generated" />

## **Exercise 2: Publishing your conversational action to Microsoft Copilot**

1.  Publishing your conversational plugin creates a new plugin in the
    Dataverse registry for your Tenant. Once available there, your
    tenant admin needs to approve your plugin to be available to users
    in the Microsoft Copilot plugins catalog.

2.  Click on **Publish**.

> <img src="./media/image13.png" style="width:6.26806in;height:1.75417in"
> alt="A screenshot of a computer Description automatically generated" />

3.  Select **Publish.**

<img src="./media/image14.png" style="width:6.26806in;height:3.25486in"
alt="A screenshot of a computer program Description automatically generated" />

4.  Select **Publish** on **Publish latest content** dialog.

<img src="./media/image15.png" style="width:6.26806in;height:2.20972in"
alt="A screenshot of a computer Description automatically generated" />

5.  The publish status is shown on the screen.

<img src="./media/image16.png" style="width:6.26806in;height:3.32431in"
alt="A screenshot of a computer Description automatically generated" />

Note: The publish should complete quickly. The actual availability in
the Microsoft Admin Center can take up to 4 hours.

**Important:** **:** For the admin to get it listed in the admin center,
the company will have to hold a valid Copilot license.

6.  Your Admin can find the **Dataverse and Microsoft Copilot
    Studio** integrated app in the Microsoft Admin Center
    under **Settings**, then **Integrations to be reviewed and
    approved**.

7.  Once your Tenant admin approves the Dataverse and Microsoft Copilot
    Studio integrated app, it should appear in the user's list of
    plugins in their Microsoft Copilot UI.

**Summary:**

In this lab, we have learnt how to create a conversational action and to
publish it.
