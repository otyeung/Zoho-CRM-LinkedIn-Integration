# [LEAD,CAPI] Zoho CRM LinkedIn Integration

This document guides you through integrating Zoho CRM with LinkedIn. It covers two main methods: Lead Sync and the Conversions API.

## Logging In

Navigate to `http://crm.zoho.com/` and log in using your email and password.

![Login screen](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Login/1-Sign%20In.jpg?raw=true)

## Initial Setup: Creating an Integration Chain in LeadChain

Within Zoho CRM, navigate to the LeadChain module. From there, you will initiate a new integration chain.

![Navigating to LeadChain and creating a new chain](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Login/2-Create%20new%20chain.jpg?raw=true)

Now you have a choice of creating either a [Lead Sync Integration](#lead-sync-integration) or a [Conversions API Integration](#conversion-api-integration). This document will guide you through both processes.

## Lead Sync Integration

This section outlines the steps to synchronize leads from LinkedIn to Zoho CRM.

### Pre-requisite

Please ensure you have both LinkedIn Ads account permission (viewer, creative manager, campaign manager or account manager) and the associated company page permission (Lead Gen Forms manager, super admin, content admin, or analyst) before proceeding.

[Lead Gen Permission on LinkedIn](https://www.linkedin.com/help/lms/answer/a421620)

### Create Lead Sync Connector

First, you will need to create a Lead Sync connector within the LeadChain module. This connector will facilitate the flow of lead data from LinkedIn to Zoho CRM.

![Creating a Lead Sync connector in Zoho CRM](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/3-Create%20Lead%20Sync%20connector.jpg?raw=true)

### Configure Lead Sync Connector

After creating the connector, you need to configure its settings.

#### Configure Source and Destination

Connect your LinkedIn account to Zoho CRM and select your LinkedIn Lead Gen Form.

_Please note: Each connector (lead chain) supports only one LinkedIn Lead Gen Form. If you need to synchronize multiple forms, you must create a separate connector (lead chain) for each form._

![Configuring the source (LinkedIn) and destination (Zoho CRM) for the Lead Sync connector](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/4.%20Connect%20Source%20and%20Destination.jpg?raw=true)

#### Configure Field Mapping

Next, you will map the fields from your LinkedIn Lead Gen Form to the corresponding fields in Zoho CRM. This ensures that lead information is accurately transferred.

#### Field Mapping Best Practices

For optimal data synchronization, we recommend mapping the following fields.

**Person Info Fields:**
It is advisable to map these core personal information fields:
| Zoho Field | LinkedIn Field |
|--------------|-------------------------------------------------------------|
| Last Name | Last name |
| Company | Company name |
| First Name | First name |
| Title | Job Role |
| Email | Business Email (use Email if Business Email is unavailable) |
| Country | Country/Region |

**Metadata Fields:**
Mapping these metadata fields will enhance tracking and reporting capabilities:
| Zoho Field | LinkedIn Field |
|------------------|-------------------------|
| Lead Source | LinkedIn (static label) |
| Social Lead ID | Lead Id |
| Ad Campaign Name | Campaign Name |
| Ad | Adset Name |

![Field Mapping Configuration in Zoho for Lead Sync - Part 1](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/5.%20Field%20Mapping%201.jpg?raw=true)

![Field Mapping Configuration in Zoho for Lead Sync - Part 2](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/6.%20Field%20Mapping%202.jpg?raw=true)

![Field Mapping Configuration in Zoho for Lead Sync - Part 3](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/7.%20Field%20Mapping%203.jpg?raw=true)

The fields listed above are commonly used in Zoho CRM. You can map any additional fields relevant to your specific needs.

Once you have completed the field mapping, click **"Save and Publish"**.

#### Send Test Lead

To ensure the integration is working correctly, send a [test lead](https://www.linkedin.com/help/lms/answer/a420737) from your LinkedIn Campaign Manager.

![Generating a test lead in LinkedIn Campaign Manager](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/8.%20Generate%20Test%20Lead.jpg?raw=true)

After sending the test lead, verify its creation in Zoho CRM.

![Verifying the incoming test lead in Zoho CRM](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/9.%20Verify%20Incoming%20Lead.jpg?raw=true)

Finally, confirm that the test lead has been successfully added to the Leads module in Zoho CRM.

![Confirming the test lead is added to the Zoho CRM Leads Module](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/10.%20Verify%20test%20lead%20is%20added%20to%20CRM.jpg?raw=true)

**Congratulations! You have successfully set up the LinkedIn Lead Sync integration with Zoho CRM.**

## Conversion API Integration

This section explains how to set up the Conversions API integration to send conversion events from Zoho CRM to LinkedIn.

### Create Conversion in LinkedIn Campaign Manager

The first step is to create a conversion rule within your LinkedIn Campaign Manager.
Navigate to **Measurement** -> **Conversion Tracking** -> **Create Conversion** -> **Conversion API**.

![Creating a CAPI Conversion in LinkedIn Campaign Manager](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/4-LinkedIn%20Create%20CAPI%20Conversion.jpg?raw=true)

Next, define your CAPI configuration. This involves:

- Giving a descriptive name to your conversion rule (e.g., including source, partner name, table name, or filter criteria).
- Specifying the conversion category.
- Setting the attribution window length and type.

![Defining the CAPI Conversion Configuration in LinkedIn](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/5-LinkedIn%20Define%20CAPI%20configuration.jpg?raw=true)

Select **"Zoho Beta"** as the data source and click **"Next Step"** to proceed.

![Selecting "Zoho Beta" as the Data Source in LinkedIn](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/6-LinkedIn%20Select%20Data%20Source.jpg?raw=true)

Ensure that you have associated the appropriate campaign(s) with your conversion rule (the campaign count must be greater than zero).

![Associating Campaigns with the CAPI Conversion in LinkedIn](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/7-LinkedIn%20Associate%20Campaign.jpg?raw=true)

Once created, the conversion status will initially be **"Unverified"**. This status will change after you send a successful test conversion from Zoho CRM.

![Newly Created CAPI Conversion with "Unverified" Status in LinkedIn](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/8-LinkedIn%20Conversion%20Created.jpg?raw=true)

### Create Conversions API Connector in Zoho CRM

Now, switch to Zoho CRM to create a Conversions API connector within the LeadChain module.

![Creating a Conversions API Connector in Zoho CRM LeadChain](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/3-Create%20LinkedIn%20Conversion%20API%20connector.jpg?raw=true)

### Configure Conversions API Connector Source and Destination

In the connector configuration, specify the Zoho CRM object (e.g., Leads, Contacts) from which you want to synchronize conversion events. Also, select the CAPI conversion name that you previously created in LinkedIn Campaign Manager.

![Configuring Source and Destination for Zoho CAPI Connector](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/9-Zoho%20Connect%20Source%20and%20Destination.jpg?raw=true)

### Configure Conversions API Field Mapping

Map the fields from Zoho CRM to the corresponding fields in the LinkedIn Conversion API.

**Mandatory Fields:**
These fields are essential for the integration to function correctly:
| Fields in LinkedIn Conversion API | Fields in Zoho CRM |
|-----------------------------------|--------------------|
| Event Time | Created Time |
| Email | Email |
| First Name | First Name |
| Last Name | Last Name |

**Recommended Fields:**
Mapping these fields can help improve the match rate and data accuracy:
| Fields in LinkedIn Conversion API | Fields in Zoho CRM |
|-----------------------------------|--------------------|
| Title | Title |
| Company Name | Company |
| Social Lead ID | Social Lead ID |

_Optionally, you can add filters to segment the data being sent, for example, based on `EventTime` (e.g., within the last 90 days) or specific market segments._

![Zoho CAPI Field Mapping Configuration - Part 1](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/10-Zoho%20Field%20Mapping%201.jpg?raw=true)

![Zoho CAPI Field Mapping Configuration - Part 2](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/11-Zoho%20Field%20Mapping%202.jpg?raw=true)

Once you have configured the field mapping and any optional filters, click **"Save and Publish"**.

You should now see the CAPI chain (e.g., for the **"Lead"** object) created and ready to send conversion events from Zoho CRM.

![Zoho CAPI Chain ("Lead") Created Successfully](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/12-Zoho%20CAPI%20chain%20created.jpg?raw=true)

### Send Test Conversion

To validate the setup, you need to send a test conversion from Zoho CRM.

Create a new lead (or the object you selected during configuration) in the respective Zoho CRM module (e.g., **Leads**).

![Creating a Test Lead in Zoho CRM for CAPI Verification](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/13-Zoho%20create%20CAPI%20event.jpg?raw=true)

Fill in the necessary information for the test record and click **"Save"**.

![Filling in Lead Information for the Test Conversion in Zoho CRM](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/14-Zoho%20create%20new%20lead.jpg?raw=true)

Navigate to the CAPI chain you created (e.g., **"Lead"**) within the LeadChain module in Zoho CRM. You should see the CAPI event scheduled for sending.

_Note: Conversion events are synchronized to LinkedIn approximately every 3 hours._

![CAPI Event Scheduled in Zoho LeadChain Dashboard](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/15-Zoho%20CAPI%20event%20scheduled.jpg?raw=true)

After the 3-hour synchronization interval, verify that the event has been sent by checking the Lead Chain dashboard.

![CAPI Event Sent - Verification in Zoho LeadChain Dashboard](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/16-Zoho%20CAPI%20Events%20Sync%20over.jpg?raw=true)

Finally, go back to your LinkedIn Campaign Manager. The status of your CAPI conversion rule should now be **"Active"**, indicating that LinkedIn has successfully received the test conversion data.

![CAPI Conversion Status showing "Active" in LinkedIn Campaign Manager](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/17-LinkedIn%20CAPI%20Conversion%20Active.jpg?raw=true)

**Congratulations! You have successfully set up the LinkedIn Conversions API integration with Zoho CRM.**
