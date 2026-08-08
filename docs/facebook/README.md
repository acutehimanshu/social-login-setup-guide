# How to Get Facebook App ID for Website Login

> This guide explains how to create and configure a Meta application for Facebook Login and obtain the App ID required by your website developer.

Facebook Login is managed through Meta's developer platform. Your developer may call the required value:

```text
FACEBOOK_CLIENT_ID=
```

For Facebook Login, this value is generally the application's **App ID**.

The App ID identifies your Meta application. Your developer may use this value in the website configuration as `FACEBOOK_CLIENT_ID`.

Do not confuse the App ID with:

- App Secret
- Facebook Page ID
- Business Manager ID
- Pixel ID
- Ad Account ID
- User ID

These are different things.

## What are we trying to get?

Your developer is usually asking for:

```text
FACEBOOK_CLIENT_ID=
```

For Facebook Login, your developer will usually use the Meta App ID as the Client ID.

Example only:

```text
FACEBOOK_CLIENT_ID=123456789012345
```

Do not copy this example.

The App ID is not:

- Your Facebook password
- Your Facebook user ID
- Your Facebook Page ID
- Your Business Manager ID

## What is a Meta App?

A **Meta App** is a configuration container created in Meta for Developers. It tells Meta which website or application is using Facebook Login.

In simple terms, it is the place where you configure Facebook Login for your website.

A Meta App can contain:

- App ID
- App Secret
- Facebook Login configuration
- Website settings
- OAuth settings
- Other Meta products or features

You do not need to understand every Meta product. For this guide, the main goal is to configure Facebook Login for a website and copy the App ID.

## Before You Start

Make sure you have:

```text
[ ] Facebook account
[ ] Access to Meta for Developers
[ ] Website URL
[ ] Developer-provided OAuth redirect URL
[ ] Privacy Policy URL
[ ] Terms of Service URL if required
[ ] Company/business information if required
[ ] Developer's requested credential list
```

The exact requirements can depend on Meta's current app setup, the products/features being used, requested permissions, and whether the application is still being tested or is ready for public users.

## Ask Your Developer for These Details

Never guess the OAuth Redirect URI.

Ask your developer for the exact values before creating or configuring the Meta App.

| Information | Example | Who provides it |
| --- | --- | --- |
| Website URL | `https://example.com` | Developer |
| OAuth Redirect URI | `https://example.com/auth/facebook/callback` | Developer |
| App Name | `My Website` | Client / Developer |
| Privacy Policy URL | `https://example.com/privacy` | Client / Developer |
| Terms URL | `https://example.com/terms` | Client / Developer |
| Required credential | `FACEBOOK_CLIENT_ID` | Developer |

The **OAuth Redirect URI** is the address where Meta sends the user after Facebook Login. The developer must provide the exact URL.

## Who Does What?

### Client does

```text
Create/configure Meta Developer application
Configure website information
Configure Facebook Login
Provide App ID to developer
```

### Developer provides

```text
Website URL
OAuth Redirect URI
Required credential list
```

### Developer does

```text
Website integration
Backend configuration
OAuth implementation
Client Secret configuration if required
Testing
Production deployment
```

This separation matters. The client should own the Meta application when it belongs to their business, while the developer should handle the website code and login implementation.

## Step 1 — Open Meta for Developers

Open the official [Meta for Developers website](https://developers.facebook.com/).

1. Open the website.
2. Log in with the Facebook account that should manage the application.
3. Use a company/business-owned account where appropriate.
4. Complete any Meta developer registration or verification steps Meta requests.

Do not share your Facebook password, 2FA code, or recovery codes with your developer.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 2 — Open My Apps

Open the app dashboard from Meta for Developers. Meta commonly refers to this area as **My Apps** or the app dashboard.

Meta periodically changes its developer dashboard. The exact buttons may look slightly different, but the goal is to create a developer application for Facebook Login.

If you already have a Meta App for this website, select it instead of creating a duplicate.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 3 — Create a Meta App

Choose the current option to create a new app.

Meta may ask you to choose a use case or app category. Choose the option that supports Facebook Login for user authentication.

In current Meta setup flows, this may appear as a use case similar to:

```text
Authenticate and request data from users with Facebook Login
```

Use the wording shown in your Meta dashboard. Do not choose Facebook Login for Business unless your developer says the project specifically needs it.

Enter the required application information, such as:

- App name
- Contact email
- Business portfolio, if Meta asks and it applies
- Other setup details Meta requests

The **App name** is a label that helps you and users recognize the application.

The **contact email** should be an email address your business or team checks.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 4 — Add Facebook Login

Add or configure **Facebook Login** for the app.

Facebook Login is the product that lets users log in to your website with their Facebook account.

Meta may show more than one login-related product, such as:

- Facebook Login
- Facebook Login for Business

For a normal consumer website login, the basic Facebook Login product/use case is generally the appropriate choice. Facebook Login for Business is different and should be used only when the developer or business requirement calls for it.

If you are unsure, ask your developer before selecting a business-specific product.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 5 — Configure Website

Meta may ask for your website URL or platform information.

Use the exact production website URL provided by your developer.

Example only:

```text
https://example.com
```

Do not copy this example. Do not invent the website URL.

If your website has separate staging and production environments, ask your developer which URL should be configured.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 6 — Configure App Domains

Meta app settings may include **App Domains**.

App Domains tells Meta which domains are associated with your application.

Example only:

```text
example.com
```

Do not copy this example.

For App Domains, Meta commonly expects the domain itself, not the full URL with `https://`. Follow the format shown in the current Meta dashboard and ask your developer if you are unsure.

Do not add domains you do not own or are not authorized to use.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 7 — Configure Privacy Policy

Meta may require a Privacy Policy URL for applications that use Facebook Login, especially when the app is made available to public users.

Example only:

```text
https://example.com/privacy-policy
```

Do not copy this example. Use the actual website Privacy Policy URL.

If your website does not have a privacy policy yet, ask the business owner and developer before trying to publish the app.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 8 — Configure Terms of Service

Meta app configuration may include a Terms of Service URL.

Example only:

```text
https://example.com/terms
```

Do not copy this example. Use the actual Terms of Service URL if your website has one or if Meta requires it for the current configuration.

Do not assume this field is required for every setup. Follow the current Meta dashboard requirements and ask your developer if you are unsure.

## Step 9 — Configure Valid OAuth Redirect URI

After the user logs in with Facebook, Meta needs to know where to send the user back to the website.

This address is called:

```text
Valid OAuth Redirect URI
```

Example only:

```text
https://example.com/auth/facebook/callback
```

Do not copy this unless your developer gives you this exact URL.

The redirect URI must exactly match the URL used by the website.

Small differences can cause login to fail, including:

- `http` vs `https`
- Wrong domain
- Wrong subdomain
- Wrong path
- Missing or extra trailing slash
- Localhost URL used for production
- Production URL used for local testing

If your developer gives you more than one redirect URI, enter each exact value according to the current Meta dashboard instructions.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Step 10 — Find the App ID

The App ID can usually be found in the Meta application's dashboard or basic app settings.

Copy the App ID and use this format when sending it to your developer:

```text
FACEBOOK_CLIENT_ID=YOUR_META_APP_ID
```

Example only:

```text
FACEBOOK_CLIENT_ID=123456789012345
```

Do not copy this example.

The Meta App ID is the value your developer may use as `FACEBOOK_CLIENT_ID`.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## Do I need to send the App Secret?

The **App Secret** is different from the App ID.

```text
App ID
→ identifies the application

App Secret
→ secret credential used by the application/server
```

Whether the developer needs the App Secret depends on how Facebook Login is implemented.

Do not publish or casually send the App Secret.

If the App Secret is required, transfer it only through the secure method your developer provides.

Never place the App Secret in:

- GitHub
- README files
- Public issues
- Public comments
- Screenshots
- Unprotected shared documents

> **Screenshot:** To be added after manual verification of the current Meta developer interface. Never include a real App Secret in a screenshot.

## Development Mode vs Live Mode

Meta apps can be in different modes while they are being built, tested, and released.

### Development mode

Development mode means the application is still being tested or configured.

Only approved people associated with the app, such as admins, developers, or testers, may be able to use certain app functionality.

This is useful while the developer is testing Facebook Login before the website is available to normal users.

### Live mode

Live mode means the application is available to normal users according to Meta's requirements.

Switching to Live mode may require:

- App configuration
- Privacy Policy
- Business verification where applicable
- App Review for certain permissions/features
- Other Meta requirements

Do not assume every Facebook Login app requires Business Verification or App Review. The requirements depend on the app, permissions, products, and how the login is used.

> **Screenshot:** To be added after manual verification of the current Meta developer interface.

## App Roles and Test Users

Meta applications can have people associated with the application for development and testing.

Depending on the current Meta dashboard, these may include roles such as:

- Admins
- Developers
- Testers

During development, the developer may need to test Facebook Login before the app is made available to everyone.

If Facebook Login works for the developer but not for a normal user, the app may still be in Development mode or the normal user may not have a testing role.

## Does Facebook Login require App Review?

The answer depends on:

- What permissions/data the app requests
- Which Meta products are being used
- Whether the application is being made available to public users

Basic login functionality may not require the same review as advanced permissions or additional Meta products.

Do not assume Facebook Login always requires App Review.

Ask your developer what permissions the website needs. Request only the permissions/data the website actually needs.

## What information does Facebook Login provide?

Facebook Login may provide information about the authenticated user depending on the permissions requested, the user's choices, and current Meta policies.

Your developer should request only the permissions/data that the website actually needs.

Unnecessary permissions can create additional review requirements and may make users less comfortable during login.

## What to Send to Your Developer

For the immediate requirement:

```text
FACEBOOK_CLIENT_ID=YOUR_APP_ID
```

Depending on the implementation, the developer may also request:

```text
FACEBOOK_CLIENT_SECRET=
```

Only provide the App Secret if your developer specifically requests it and gives you a secure transfer method.

The App ID is not the same thing as the App Secret.

## Copy-Paste Handover Template

```text
Facebook Login Setup Completed

FACEBOOK_CLIENT_ID=________________________________
```

```text
Website:
________________________________

Meta App Name:
________________________________

Meta App ID:
________________________________

Facebook Login configured:
Yes / No

OAuth Redirect URI configured:
Yes / No

App mode:
Development / Live

Sent to developer:
Yes / No
```

Do not paste the App Secret into this public template.

## Security

### Identifier

```text
App ID
```

This identifies your Meta application. Your developer may need it as `FACEBOOK_CLIENT_ID`.

### Sensitive credential

```text
App Secret
Facebook access tokens
User access tokens
Passwords
2FA codes
Recovery codes
```

Keep sensitive credentials private.

Never put them into GitHub documentation, public issues, screenshots, public comments, or unprotected shared documents.

## Common Problems

### Problem 1 — Invalid OAuth Redirect URI

Likely causes:

- Redirect URI does not exactly match
- Wrong domain
- Wrong path
- `http` / `https` mismatch
- Production vs localhost mismatch

Ask your developer to compare the exact URL used by the website with the Valid OAuth Redirect URI configured in Meta.

### Problem 2 — Facebook Login works for developer but not normal users

Possible causes:

- App still in Development mode
- User is not an approved role/tester
- App configuration incomplete
- Required review/approval not completed

Ask the developer whether the app is still being tested or is ready for Live mode.

### Problem 3 — App is not available

Check:

- App mode
- Required configuration
- Privacy Policy
- App Review where applicable
- Business verification where applicable

Do not assume business verification or app review is always required. Check what Meta is asking for in the current app dashboard.

### Problem 4 — App ID is not working

Possible causes:

- Wrong App ID
- Wrong Meta application
- Website using a different App ID
- Configuration mismatch

Copy the App ID again from the Meta app dashboard and confirm it with your developer.

### Problem 5 — OAuth error

Ask the developer for the exact error message and screenshot.

OAuth errors are often caused by a mismatch between the website configuration and the Meta Developer configuration.

The client should not debug backend code unless the developer asks for specific information.

## Optional: Facebook Login for Business

Facebook Login for Business is different from basic consumer Facebook Login.

Use it only if your website, product, or developer specifically requires business-oriented Facebook authentication features.

For a normal website where users log in with their Facebook account, basic Facebook Login is usually the relevant product/use case.

## Optional: Meta Business Verification

Some Meta products, features, permissions, or production requirements may require business verification.

Do not assume business verification is always required for every Facebook Login setup.

If Meta asks for business verification, the business owner or authorized company representative should handle it.

## Optional: App Review

Additional permissions or products may require App Review.

App Review is Meta's process for checking whether an app is allowed to use certain permissions or features.

Ask your developer which permissions are required before submitting anything for review.

## Final Checklist

```text
[ ] Facebook/Meta account available
[ ] Meta developer access completed
[ ] Meta app created
[ ] Facebook Login added/configured
[ ] Website URL configured
[ ] App Domain configured if required
[ ] Privacy Policy configured
[ ] Terms URL configured if required
[ ] OAuth Redirect URI configured
[ ] App ID copied
[ ] FACEBOOK_CLIENT_ID prepared
[ ] App Secret identified if developer requires it
[ ] App mode checked
[ ] Testing completed
[ ] Required review/verification completed if applicable
[ ] Developer received required credentials securely
```

## Official Meta Documentation

- [Meta for Developers](https://developers.facebook.com/)
- [Meta app dashboard](https://developers.facebook.com/apps/)
- [Create an app](https://developers.facebook.com/docs/development/create-an-app/)
- [Facebook Login documentation](https://developers.facebook.com/docs/facebook-login/)
- [Facebook Login for the Web](https://developers.facebook.com/docs/facebook-login/web/)
- [Manually Build a Login Flow](https://developers.facebook.com/docs/facebook-login/guides/advanced/manual-flow/)
- [App Roles](https://developers.facebook.com/docs/development/build-and-test/app-roles/)
- [App Modes](https://developers.facebook.com/docs/development/release/)
- [App Review](https://developers.facebook.com/docs/app-review/)
- [Business Verification](https://developers.facebook.com/docs/development/release/business-verification/)

## Related Guides

[Back to Social Login Setup Guide](../../README.md)

[Google Login Setup](../google/README.md)

[Apple Sign in with Apple Setup](../apple/README.md)
