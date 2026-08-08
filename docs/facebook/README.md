# Facebook Login Setup Guide

## Overview

This guide explains the basic setup steps for a website that uses Facebook Login through Meta for Developers. It is written for a non-technical client and is intentionally text-only.

The goal is to help you understand what to do, what information to give to your developer, and which value you usually need to copy from Meta.

## What are we trying to get?

Your developer may ask for this value:

FACEBOOK_CLIENT_ID=

For Facebook Login, this usually maps to the Meta App ID.

Example only:

FACEBOOK_CLIENT_ID=123456789012345

This example is not a real credential. It is only a placeholder format.

## App ID vs App Secret

This is the most important distinction.

App ID
→ identifies the Meta application

App Secret
→ sensitive credential used by the application/server

The App ID is a safe identifier. The App Secret is a secret credential and must be handled carefully.

Do not confuse your App ID with:

- Facebook user ID
- Facebook Page ID
- Business Manager ID
- Ad Account ID
- Pixel ID
- App Secret

## What is a Meta app?

A Meta app is the application record created in Meta for Developers. It is the place where the business configures Facebook Login and related settings for the website.

You do not need to master every Meta product or every developer term. For a normal website login flow, the main goal is usually:

- create the Meta app
- configure Facebook Login
- enter the developer-provided redirect URI
- copy the App ID
- send the App ID to the developer

## Facebook Login for a Website

Facebook Login for a website allows a visitor to sign in with their Facebook account.

It allows a website to confirm that the visitor is who they say they are, using Facebook as the sign-in check.

High-level flow:

Website
↓
Facebook
↓
User logs in
↓
Facebook sends the user back
↓
Website completes login

The developer normally builds the website flow. The client normally creates or configures the Meta app and provides the required app information.

## Client vs Developer Responsibilities

### Developer provides

- Website URL
- Exact OAuth redirect URI
- Any required Meta configuration information
- Required credential list

### Client does

- Access Meta for Developers
- Create or update the Meta application
- Configure website information
- Configure Facebook Login
- Enter the developer-provided redirect URI
- Copy the App ID
- Return the requested credential

### Developer does afterward

- Configure environment variables
- Configure backend/frontend
- Configure App Secret securely if required
- Test authentication
- Handle production deployment

This split matters. The client usually owns the Meta app and the business relationship with Meta. The developer usually handles the actual website implementation.

## Before you start

Have these ready before creating the app:

- Facebook account
- Access to Meta for Developers
- Website URL
- Developer-provided OAuth redirect URI
- Privacy Policy URL
- Terms of Service URL if required
- Business information if Meta requests it
- Developer-specified credential list

The exact requirements can vary depending on the app, requested permissions, and whether the app is still being tested or is intended for public users.

## Step 1 — Open Meta for Developers

Open the official Meta for Developers site:

https://developers.facebook.com/

Then:

1. Log in with the Facebook account that should manage the application.
2. Use a company or business-owned account where appropriate.
3. Complete any registration or account steps Meta asks for.
4. Go to the app dashboard.

Do not share your Facebook password, two-factor authentication codes, recovery codes, or other account secrets with anyone.

## Step 2 — Open the app dashboard

In Meta for Developers, open the app dashboard or My Apps area.

Meta may rename or reposition buttons from time to time, but the goal is to create or open the application tied to this website.

If the website already has a Meta app, use that app instead of creating a duplicate.

## Step 3 — Create a Meta app

Use the current Create App flow in Meta for Developers.

Meta may ask you to choose a use case. For a standard website using Facebook Login, choose the use case that matches authenticating people and requesting data for login.

The exact wording may change in the current Meta dashboard, but the appropriate choice is the one used for Facebook Login for a website or app user authentication.

Do not select a business-specific option unless your developer specifically says the project needs it.

Meta may ask for:

- App name
- Contact email
- Business portfolio information if relevant
- Other setup details required by the current dashboard

The app name is only a label for the app. It is not the same as the App ID.

## Step 4 — Add Facebook Login

Once the app is created, add or configure Facebook Login.

For a normal website, you usually want the basic Facebook Login option used for website sign-in.

Meta may also show options such as Facebook Login for Business. Do not use a business-specific option unless the developer or business requirement clearly calls for it.

## Step 5 — Configure the website

Meta may ask for the website URL or platform details.

Use the exact production URL your developer gives you.

Example only:

https://example.com

Do not invent a URL. Use the real website URL only.

If you have separate development and production URLs, ask the developer which one should be configured.

## Step 6 — Website URL, App Domain, and redirect URI

These three items are related but not the same.

Website URL
→ the public address of the website

App domain
→ the domain associated with the app in Meta

OAuth redirect URI
→ the exact address where Facebook sends the user back after login

Example only:

Website URL:
https://example.com

App Domain:
example.com

OAuth redirect URI:
https://example.com/auth/facebook/callback

These should match the real production site information provided by the developer. They are not interchangeable.

### App Domains

Some Meta app configuration screens include App Domains. The exact field name can change over time and may appear differently in the current dashboard.

Use the real domain owned by the business. For example, if the website is hosted at example.com, that is the kind of value Meta expects in the domain-related field.

Do not add domains you do not own or are not authorized to use.

## Step 7 — Configure Privacy Policy

Meta may require a Privacy Policy URL for apps that use Facebook Login, especially when the app is available to public users.

Example only:

https://example.com/privacy-policy

Use the real Privacy Policy URL for the website, not the example.

If the business does not yet have a Privacy Policy, the business owner and developer should confirm how this should be handled before the app is used publicly.

Do not assume this is always required for every possible Meta setup, but current Meta app configuration commonly expects a valid Privacy Policy URL when the app is being used more broadly or when additional requirements apply.

## Step 8 — Terms of Service

Terms of Service may also appear in the app settings, depending on the current Meta setup and business requirements.

This is not always required for a basic website login, but it may be required or recommended depending on the configuration, app permissions, and Meta requirements.

Use the real Terms of Service URL only if the website has one and Meta requires it.

## Step 9 — Configure the OAuth redirect URI

This is one of the most important parts of the setup.

The redirect URI is the exact address where Facebook sends the user back after authentication.

Example only:

https://example.com/auth/facebook/callback

Important:

Never guess this URL. Ask the developer for the exact value.

The redirect URI must match the website's configuration exactly. Common mismatches include:

- HTTP vs HTTPS
- Wrong domain
- Wrong subdomain
- Wrong path
- Missing or extra trailing slash
- Localhost used in production
- Production URL used in local testing

If the developer gives you more than one possible redirect URI, enter each exact value as directed by the current Meta dashboard.

## Step 10 — Copy the App ID

After the app and Facebook Login settings are configured, open the app dashboard and find the App ID.

This is the value your developer usually needs as the Facebook login client ID.

Send it to the developer in this format:

FACEBOOK_CLIENT_ID=YOUR_META_APP_ID

Example only:

FACEBOOK_CLIENT_ID=123456789012345

This is an example only. Do not use it as a real credential.

## Do I need to send the App Secret?

The App Secret is different from the App ID.

App ID
→ identifies the Meta application

App Secret
→ sensitive credential used by the application/server

Whether the developer needs the App Secret depends on the login implementation.

The App Secret should never be published in:

- README files
- GitHub repositories
- Public issues
- Public chat threads
- Public screenshots
- Unprotected documents

If the developer specifically requests the App Secret, send it only through the secure method they provide.

## Development Mode vs Live Mode

Meta apps can be in different states while they are being configured and tested.

### Development

Development mode is used while the app is being built and tested.

This is when the developer is testing the login flow and checking the app configuration.

Access may be restricted to people with the right app roles or testing access.

### Live

Live mode is used when the app is intended for ordinary public users.

The app may need to move to Live mode before real users can use it. This may depend on:

- app configuration
- requested permissions
- app review requirements
- business verification requirements
- other Meta requirements

Do not assume every Facebook Login app needs all of these steps. Requirements depend on the app's setup and the permissions/features it requests.

## Does Facebook Login require App Review?

Not automatically.

The answer depends on what the app requests and who will use it.

Meta's official documentation explains that App Review is required when the app will be used by people without a role on the app, and it may also be required for certain permissions or features.

For many basic website login setups, the required review is minimal or not needed for the basic public_profile and similar login scenarios. But advanced permissions or extra features may trigger review.

The right answer is:

App Review is required only when Meta requires it for the permissions or app access the website is requesting.

## Does my business need Meta Business Verification?

Not always.

Business verification can be required depending on the app, permissions, features, and business configuration.

Meta's current guidance says business verification can be required for advanced access or certain app requirements. For ordinary website login, it is not automatically required for every basic setup.

If Meta asks for business verification, the business owner or authorized company representative should complete it.

## App roles and testing

Meta applications can include people with different roles for development and testing. Depending on the current Meta dashboard, these roles may be labeled in different ways, but they generally include admin and developer-type access.

During development, the developer may ask the client to add test users or app roles so the app can be tested before public release.

If Facebook Login works for the developer but not for a normal user, the most common causes are:

- app is still in Development mode
- the user is not in the required app role or testing access
- the app has not yet been made available to public users
- permissions or review requirements are still pending

## What to send to your developer

The main handover usually looks like this:

FACEBOOK_CLIENT_ID=YOUR_META_APP_ID

If your developer specifically requests the App Secret or another credential, use the secure transfer method they provide.

Do not send secrets in a public README, public chat, public issue, screenshot, or other non-private location.

## Troubleshooting

### Problem 1 — Invalid OAuth redirect URI

What the client sees:

Facebook Login fails after clicking the login button.

What it usually means:

The website's redirect URI does not exactly match the value configured in Meta.

What the client can check:

- HTTP vs HTTPS
- Wrong domain
- Wrong subdomain
- Wrong path
- Missing or extra trailing slash
- Localhost used in production
- Production URL used in local testing

When to contact the developer:

Ask the developer to compare the exact URL used by the website to the redirect URI in Meta.

### Problem 2 — App is still in development mode

What the client sees:

The developer can log in, but other users cannot.

What it usually means:

The app may still be restricted to people with app roles or testing access.

What the client can check:

- App mode
- Whether the app is intended for public users
- Whether the user has the required role or access

When to contact the developer:

Ask whether the app is still being tested or whether it is ready to move to Live mode.

### Problem 3 — Wrong App ID

What the client sees:

The developer says the Facebook Client ID is wrong or does not match the website.

What it usually means:

The wrong Meta app was selected, or the wrong App ID was copied.

What the client can check:

- Correct Meta app selected
- App ID copied from the correct app dashboard
- Website code or config is pointing at the correct app

When to contact the developer:

Ask the developer to confirm the exact App ID that should be used.

### Problem 4 — Privacy Policy or business requirement not met

What the client sees:

Meta asks for additional app details or blocks public use.

What it usually means:

The app may still be missing required information, such as a valid Privacy Policy URL or a business-related requirement.

What the client can check:

- Privacy Policy URL exists
- URL is correct and public
- Business information is complete if Meta asks for it

When to contact the developer:

Ask whether the current Meta requirement belongs to the business, the app, or the permission setup.

### Problem 5 — Review or verification requirement

What the client sees:

Meta asks for app review, verification, or additional business information.

What it usually means:

The app may be requesting permissions, products, or features that require additional Meta review or business verification.

What the client can check:

- Requested permissions
- App mode
- Meta dashboard messages
- Whether the app is intended for public users

When to contact the developer:

Ask the developer which permissions are actually needed and whether the app is in a review or verification phase.

### Problem 6 — Permission or scope issue

What the client sees:

Login succeeds, but the website does not receive the expected user information.

What it usually means:

The app may not be requesting the correct permission, or the permission may require review.

What the client can check:

- Requested permissions
- Whether the user granted them
- Whether the permission is approved or needs review

When to contact the developer:

Ask the developer to confirm the minimum required permissions for the website.

### Problem 7 — Wrong Meta application

What the client sees:

The website and Meta app do not seem to match.

What it usually means:

The developer may be testing a different app than the one the business believes is active.

What the client can check:

- App name
- App ID
- Account used for the app
- Current website URL

When to contact the developer:

Ask the developer to confirm which Meta app is connected to the website.

## Security

Safe identifier:

App ID

Sensitive values:

App Secret
Access tokens
User access tokens
Passwords
2FA codes
Recovery codes

Never share sensitive values publicly.

Never ask users to publish:

- App Secret
- tokens
- passwords
- recovery data

Only official app credentials and secure transfer methods should be used.

## FAQ

### What is a Facebook App ID?

It is the identifier for the Meta app. Your developer may use it as FACEBOOK_CLIENT_ID.

### Is Facebook App ID the same as Facebook user ID?

No. A Facebook user ID identifies a person. A Facebook App ID identifies the Meta app used by the website.

### Is Facebook App ID the same as App Secret?

No. They are different values.

App ID
→ identifies the Meta application

App Secret
→ sensitive credential used by the application/server

### Do I need a Facebook Page?

Not always. A basic Facebook Login setup is about the Meta app, not necessarily a Facebook Page. If a Page is required, the developer will tell you.

### Do I need Meta Business Manager?

Not always. It depends on the app, business, and Meta requirements. Basic customer login may not require a full business-setup workflow.

### Do I need Business Verification?

Not always. Business verification depends on the app, features, permissions, and Meta requirements.

### Does Facebook Login require App Review?

Not always. It depends on the permissions and features the app requests and whether public users will use it.

### Why does Facebook Login work for me but not other users?

The app may still be in Development mode, or only people with the right app role or testing access may be able to use it.

### What is an OAuth Redirect URI?

It is the exact address where Facebook sends the user back after login.

Example only:

https://example.com/auth/facebook/callback

Do not guess it. Ask the developer for the exact value.

### Can I use localhost during development?

Developers may use localhost for local testing, but production setups usually use a real public domain. Do not add localhost unless the developer specifically asks for it.

### What should I send to my developer?

Usually:

FACEBOOK_CLIENT_ID=YOUR_META_APP_ID

If the developer specifically asks for the App Secret or another credential, provide it only through the secure method they give you.

## Final checklist

- [ ] Meta account available
- [ ] Developer access completed
- [ ] Meta application created
- [ ] Facebook Login configured
- [ ] Website configured
- [ ] Required domain configuration completed
- [ ] Privacy Policy configured if required
- [ ] Terms URL configured if required
- [ ] OAuth Redirect URI configured
- [ ] App ID copied
- [ ] FACEBOOK_CLIENT_ID prepared
- [ ] App Secret requirement confirmed
- [ ] Development/Live status checked
- [ ] App Review requirements checked
- [ ] Business verification requirements checked
- [ ] Developer received required values securely

## Official Meta references

- Meta for Developers: https://developers.facebook.com/
- Meta app dashboard: https://developers.facebook.com/apps/
- Create an app: https://developers.facebook.com/docs/development/create-an-app/
- Facebook Login: https://developers.facebook.com/docs/facebook-login/
- Facebook Login for the Web: https://developers.facebook.com/docs/facebook-login/web/
- App Review: https://developers.facebook.com/docs/app-review/
- App roles: https://developers.facebook.com/docs/development/build-and-test/app-roles/
- Business Verification: https://developers.facebook.com/docs/development/release/business-verification/

## Related guides

[Back to Social Login Setup Guide](../../README.md)

[Google Login Setup](../google/README.md)

[Apple Sign in with Apple Setup](../apple/README.md)
