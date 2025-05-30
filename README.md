# Zoho CRM LinkedIn Integration

## Logging In

Go to http://crm.zoho.com/ and login with your email and password

![Login screen](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Login/1-Sign%20In.jpg?raw=true)

## Create new chain

Choose LeadChain module and create new chain

![Create new chain](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Login/2-Create%20new%20chain.jpg?raw=true)

Now you have a choice of creating [Lead Sync Integration](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/tree/main?tab=readme-ov-file#lead-sync-integration) or [Conversions API Integration](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/tree/main?tab=readme-ov-file#conversion-api-integration)

## Lead Sync Integration

### Create Lead Sync connector

![Create Lead Sync connector](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/3-Create%20Lead%20Sync%20connector.jpg?raw=true)

### Configure Lead Sync connector

#### Configure Source and Destination

Connect your LinkedIn account to Zoho CRM and Select your LinkedIn Form, note that you can only select one form per connector (lead chain) If you need to sync multiple forms, you need to create multiple connectors.

![Configure Source and Destination](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/4.%20Connect%20Source%20and%20Destination.jpg?raw=true)

#### Configure Field Mapping

Set up the field mapping specific to the form specified in the previous step. Verify the LinkedIn form fields to the corresponding Zoho CRM fields.

#### Best Pracrice

It's recommended to map the following Person Info fields at a minimum :
| Zoho Field | LinkedIn Field |
| --- | --- |
| Last Name | Last name |
| Company | Company name |
| First Name | First name |
| Title | Job Role |
| Email | Business Email (if Business Email is not available, use Email) |
| Country | Country/Region |

It's recommended to map the following Metadata fields for better tracking and reporting :
| Zoho Field | LinkedIn Field |
| -------------- | ------------------------------ |
| Lead Source | LinkedIn (it's a static label) |
| Social Lead ID | Lead Id |
| Ad Campaign Name | Campaign Name |
| Ad | Adset Name |

![Field Mapping 1]()

![Field Mapping 2]()

![Field Mapping 3]()

The above fields are the most commonly used fields in Zoho CRM. If you have other fields that you want to sync, you can map them as well.

![Configure Field Mapping](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Lead%20Sync%20Connector/5.%20Configure%20Field%20Mapping.jpg?raw=true)

## Conversion API Integration

### Create Conversions API connector

![Create Conversions API connector](https://github.com/otyeung/Zoho-CRM-LinkedIn-Integration/blob/main/Conversions%20API%20Connector/3-Create%20LinkedIn%20Conversion%20API%20connector.jpg?raw=true)

### Configure Conversions API connector
