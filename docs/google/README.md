# How to Get a Google Client ID for Website Login

This guide explains how a website owner or non-technical client can create the Google login credentials required by a developer.

The goal is to get the Google Client ID for website login. Your developer will use it to configure Google Sign-In, Google OAuth setup, or another Google login flow on your website.

## What is a Google Client ID?

A **Google Client ID** is a unique ID that Google gives to your website or application.

Google needs this ID so it knows which website is asking users to log in with Google. Your developer adds the Client ID to the website so the website can start the Google login process correctly.

A Google Client ID is:

- Not your Google password
- Not your Gmail address
- Not the password for your website
- Not the same thing as a Google account

It normally looks like a long string and often ends with:

```text
.apps.googleusercontent.com
```

## What are we trying to get?

Your developer is usually asking you for this value:

```text
GOOGLE_CLIENT_ID=
```

This is the main value your developer is asking you for.

Depending on how your website is built, your developer may separately need another credential, such as a Client Secret.

Only send additional credentials if your developer specifically requests them through a secure method. Do not paste secrets into GitHub issues, public repositories, public comments, or shared documents that are not protected.

## Before You Start

Make sure you have:

- [ ] Access to a Google account that should own the website's Google login configuration.
- [ ] The website name or company name.
- [ ] The website URL.
- [ ] The exact information requested by your developer.
- [ ] The email address that should receive Google project notifications.
- [ ] The redirect URI or callback URL from your developer, if your website needs one.

Where possible, the Google account used to create this setup should belong to the business, organization, or team that owns the website. Avoid using one employee's personal Google account if the project should belong to the company long term.

## Ask Your Developer for These Details

Ask your developer for these values before opening Google Cloud. Do not guess them.

| Information | What it means | Who provides it |
| --- | --- | --- |
| Website name | Name of the website/application | Developer / Client |
| Production website URL | Main website address | Developer |
| Authorized JavaScript Origin | Website origin Google should trust | Developer |
| Authorized Redirect URI | Where Google should return authentication responses, if used | Developer |
| Support email | Email users can contact about login | Client |
| App name | Name users may see during login | Client |

The exact values depend on how your developer implemented Google login. Some Google login setups need an Authorized JavaScript Origin. Some also need an Authorized Redirect URI. Some browser-based setups may not use the redirect URI field.

## What is an Authorized JavaScript Origin?

An **Authorized JavaScript Origin** is the website address that Google is allowed to trust when login starts from a browser.

In simple terms: Google needs to know which website is allowed to start the Google login process.

Example only:

```text
https://www.example.com
```

Do not copy this example. Your developer should provide the exact production origin.

An origin normally contains:

- Protocol, such as `https://`
- Domain, such as `www.example.com`
- Optional port, where applicable

An origin does not include a page path. For example, it should not include `/login` or `/auth/google/callback`.

## What is an Authorized Redirect URI?

After the user completes login, Google may need to send the browser back to a specific address on your website. That address is called a **Redirect URI** or **Callback URL**.

Example only. Do not copy this unless your developer gives you this exact URL:

```text
https://www.example.com/auth/google/callback
```

Google requires the redirect URI used by the website to match the redirect URI configured in Google Cloud.

A common error is:

```text
redirect_uri_mismatch
```

This usually means the website sent Google a callback address that does not exactly match the address configured in Google Cloud.

Small differences can matter, including:

- `http` instead of `https`
- A different domain
- A different path
- A missing or extra trailing slash

## Step 1 — Open Google Cloud

Open the official [Google Cloud Console](https://console.cloud.google.com/).

Sign in with the Google account that should own or manage this Google login setup.

If your company uses Google Workspace, ask your team which account should own the project before continuing.

> **Screenshot:** To be added after manual verification of the current Google Cloud interface.

## Step 2 — Create or select a Google Cloud project

A **Google Cloud project** is a container Google uses to hold settings, credentials, and configuration for an application.

For this guide, the project will hold the Google OAuth credentials for your website.

If your business already has a Google Cloud project for this website, select that project. If not, create a new project.

Example project name only:

```text
My Website Login
```

Do not use the example name unless it makes sense for your business. Use a clear name that helps your team recognize the website later.

## Step 3 — Open Google Auth Platform

Open the [Google Auth Platform overview](https://console.cloud.google.com/auth/overview) in Google Cloud.

Google Auth Platform is where Google manages authentication settings for your application. **Authentication** means confirming who a user is, such as letting a user sign in with their Google account.

Google Auth Platform includes areas such as:

- Branding
- Audience
- Data Access
- Clients

For getting the Google OAuth Client ID, the most important area is **Clients**. You may also need to complete Branding, Audience, and Data Access settings before or during client creation.

> **Screenshot:** To be added after manual verification of the current Google Cloud interface.

## Step 4 — Set up your application information

Google may ask for application information that users can see during the Google login or consent experience.

### App name

The **App name** is the name users may see when they log in or approve access.

Use a name that clearly represents your website, company, or application. Do not use a name that could confuse users into thinking your app is owned by Google.

### User support email

The **User support email** is an email address users can contact if they have questions about login or the application.

Use an address that your business or team checks regularly.

### Developer contact information

Google may use developer contact information to send important project notices.

Use an email address that your business or technical team can monitor.

### Website/application information

Google may ask for website links such as a homepage, privacy policy, or terms of service, especially for production applications.

Ask your developer or business owner which links should be used.

## Step 5 — Configure who can use the application

Google Auth Platform uses **Audience** settings to control who can authorize or use the application.

You may see options such as:

| Option | Simple meaning |
| --- | --- |
| Internal | Only users inside your Google Cloud Organization can use the app. This is usually for company-only or organization-only apps. |
| External | Users with Google Accounts outside your organization may use the app. This is usually the relevant choice for a public website. |

For a public website, **External** is generally the appropriate audience. Still, the business owner and developer should choose based on the real users of the application.

Google may also show a publishing status such as Testing or In production. Testing can be useful before launch, while production is for a live application. The right choice depends on the website and the permissions being requested.

## Step 6 — Data Access

**Data Access** is where Google manages scopes.

A **scope** is permission to access a particular type of Google information. For example, a scope might allow an app to read a user's basic profile information or email address.

Do not randomly add permissions.

Use only the permissions requested by your developer or application.

If the website only needs Google Sign-In, do not add unnecessary Google API permissions. Additional permissions, especially sensitive or restricted scopes, can trigger more Google requirements, warnings, or verification.

## Step 7 — Create the OAuth Client

An **OAuth Client** is the Google credential that identifies your website when it uses Google login.

Open:

```text
Google Auth Platform
↓
Clients
↓
Create Client
↓
Application type: Web application
```

Choose **Web application** because this guide is for a website login setup.

When Google asks for the client name, use a clear label so your team can recognize it later.

Example client name only:

```text
Website Login
```

Do not use this example if your team has a different naming standard.

> **Screenshot:** To be added after manual verification of the current Google Cloud interface.

## Step 8 — Add the Authorized JavaScript Origin

When Google asks for **Authorized JavaScript origins**, enter the exact origin your developer provided.

Use this placeholder while asking your developer:

```text
YOUR_DEVELOPER_PROVIDED_ORIGIN
```

Example only:

```text
https://www.example.com
```

Do not add a random URL here. Do not copy the example.

For production, this should be the real production website origin provided by your developer.

Local development values such as `localhost` may be used during development, but production and local development values are different. Do not add localhost unless your developer asks for it.

## Step 9 — Add Authorized Redirect URI (if your developer requires it)

Some Google login implementations use a redirect or callback endpoint. Others use a browser-based flow that does not require you to enter a redirect URI in this field.

If your developer gives you a Redirect URI, enter it exactly as provided.

Example only:

```text
https://www.example.com/auth/google/callback
```

Do not copy this example unless your developer gives you this exact URL.

The redirect URI must match the website's Google login configuration. If it does not match, Google may show:

```text
redirect_uri_mismatch
```

## Step 10 — Create the Client

After the required fields are complete, click the button Google provides to create the client.

Google will generate the OAuth credential for your website.

## Step 11 — Copy your Google Client ID

After the client is created, it should appear in the Clients area of Google Auth Platform.

Open the new web application client and copy the Client ID.

Use this format when sending it to your developer:

```text
GOOGLE_CLIENT_ID=your-generated-client-id
```

Do not invent a Client ID. Copy the value from Google Cloud.

The Client ID normally looks like a long string and often ends with:

```text
.apps.googleusercontent.com
```

## Do I need to send the Client Secret?

A **Client Secret** is different from the Client ID.

Think of the Client ID like the application's username. A Client Secret is more like the application's password. It must be protected.

Whether your website needs the Client Secret depends on how the developer implemented Google authentication.

Some browser-based Google Sign-In setups use the Client ID and do not need you to send a Client Secret. Some server-side implementations may need a Client Secret.

If your developer needs the Client Secret, send it only through the secure method they provide. Never publish it in this GitHub repository, a public issue, a public comment, or an unprotected document.

## What to Send to Your Developer

The minimum requested value is usually:

```text
GOOGLE_CLIENT_ID=YOUR_CLIENT_ID
```

If the developer separately requested another credential, use the secure method they provided.

Do not send secrets through public GitHub issues, public repositories, README files, public comments, or unprotected shared documents.

## Copy-Paste Handover Template

```text
Google Login Setup Completed

GOOGLE_CLIENT_ID=________________________________
```

```text
Website:
________________________________

Google project:
________________________________

Google OAuth client:
________________________________

Redirect URI configured:
Yes / No / Not required

Sent to developer:
Yes / No
```

Do not paste a Client Secret into this template.

## Common Problems

### Problem 1 — redirect_uri_mismatch

This means the redirect URI or callback URL used by the website does not exactly match the redirect URI configured in Google Cloud.

Ask your developer to compare the website's actual Google callback URL with the value entered in Google Auth Platform.

Check for:

- `http` vs `https`
- Different domain
- Different path
- Missing or extra trailing slash
- Local testing URL used on the live website

### Problem 2 — Google login works locally but not on production

Local development and production usually use different origins and redirect URIs.

For example, a developer may test with localhost, but the live website uses the real domain.

Ask your developer which production origin and redirect URI should be added.

### Problem 3 — Client ID is not working

Possible causes:

- The wrong Client ID was copied.
- The Client ID belongs to the wrong Google Cloud project.
- The OAuth client was not created as a Web application.
- The website is configured with a different origin or redirect URI.
- The Google Cloud configuration does not match how the developer implemented login.

### Problem 4 — User sees an unverified/test warning

Google may show warnings or require verification depending on the app's audience, publishing status, branding, scopes, and production requirements.

This does not always mean something is broken. It may mean the app is still in testing, the app requests permissions that need review, or production settings are incomplete.

Ask your developer which permissions are required and whether Google verification is needed for your use case.

## Security

### Safe to understand/share

```text
Client ID
```

A Client ID is an identifier. It is generally not treated like a password, but it should still only be shared as part of the application's legitimate configuration.

### Keep private

```text
Client Secret
Private keys
Access tokens
Refresh tokens
Passwords
2FA codes
Recovery codes
```

Never publish private values in GitHub, public issue trackers, screenshots, public chat channels, or documentation.

## Final Checklist

```text
[ ] Google account available
[ ] Google Cloud project created/selected
[ ] Google Auth Platform configured
[ ] App information configured
[ ] Audience configured
[ ] Required data access configured
[ ] Web application OAuth client created
[ ] Authorized JavaScript Origin configured if required
[ ] Redirect URI configured if required
[ ] Google Client ID copied
[ ] Developer received the required credential
[ ] No password/OTP/private key was shared
```

## Official Google Documentation

- [Google Auth Platform overview](https://support.google.com/cloud/answer/15548748)
- [Get started with the Google Auth Platform](https://support.google.com/cloud/answer/15544987)
- [Manage OAuth clients](https://support.google.com/cloud/answer/15549257)
- [Sign in with Google setup for web](https://developers.google.com/identity/gsi/web/guides/get-google-api-clientid)
- [Google API Client ID for web authorization](https://developers.google.com/identity/oauth2/web/guides/get-google-api-clientid)
- [OAuth 2.0 for web server applications](https://developers.google.com/identity/protocols/oauth2/web-server)
- [Manage app audience](https://support.google.com/cloud/answer/15549945)
- [Manage app data access](https://support.google.com/cloud/answer/15549135)
- [OAuth app verification help](https://support.google.com/cloud/answer/13463073)

## Related Guides

- [Back to Social Login Setup Guide](../../README.md)
- [Apple Sign in with Apple Setup](../apple/README.md)
- [Facebook Login Setup](../facebook/README.md)
