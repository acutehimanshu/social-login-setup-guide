# How to Get Apple Client ID for Website Login

## Overview

> This guide explains how to configure Sign in with Apple for a website and obtain the Services ID that your developer may use as the Apple Client ID.

Apple website login is more complicated than some other social login providers because Apple requires the website to be connected to an Apple application in the Apple Developer account.

For website Sign in with Apple, the value commonly used as the client identifier is the **Services ID**. Your developer may call this value:

```text
APPLE_CLIENT_ID=
```

The important distinction is this:

```text
APPLE_CLIENT_ID = Services ID for website Sign in with Apple
```

Do not confuse the Services ID with an App ID, Bundle ID, Team ID, Key ID, or private key.

## What are we trying to get?

The main value your developer may ask for is:

```text
APPLE_CLIENT_ID=
```

For website Sign in with Apple, this value is normally the Services ID created in Apple Developer.

Example only. Do not copy this value:

```text
com.example.website
```

Depending on the website's implementation, your developer may also need:

```text
APPLE_TEAM_ID=
APPLE_KEY_ID=
APPLE_PRIVATE_KEY=
```

Your developer should tell you exactly which additional credentials are required by the website's implementation.

Do not send private credentials unless the developer specifically requests them and provides a secure transfer method.

## What is an Apple Services ID?

A **Services ID** is an identifier Apple uses for a website or web service that communicates with Apple services such as Sign in with Apple.

For website Sign in with Apple, the Services ID becomes the client identifier. This is the value your developer may put into the website as:

```text
APPLE_CLIENT_ID=
```

A Services ID is different from:

| Term | Simple meaning |
| --- | --- |
| Apple Developer account | The Apple account or team that owns the configuration. |
| App ID | Identifies an Apple app in the Apple Developer account. |
| Bundle ID | A unique identifier for an Apple app, often used inside an App ID. |
| Team ID | Identifies your Apple Developer team. |
| Key ID | Identifies a private key created in Apple Developer. |

## Why is Apple Login more complicated?

Google login often looks like this:

```text
Google:
Website
 ↓
OAuth Client
 ↓
Client ID
```

Apple website login usually has more pieces:

```text
Apple:
Apple Developer Account
 ↓
Existing App / App ID
 ↓
Sign in with Apple enabled
 ↓
Services ID
 ↓
Website Domain
 ↓
Domain Verification
 ↓
Return URL
 ↓
Optional/required server credentials depending on implementation
```

In simple terms: Apple wants the website login to be associated with an existing Apple app or App ID. The Services ID is then configured for the website domain and Return URL.

## Before You Start

Make sure you have:

```text
[ ] Apple Developer account
[ ] Appropriate Account Holder/Admin access
[ ] Existing Apple App ID
[ ] Sign in with Apple enabled for the app
[ ] Website domain
[ ] Exact return/callback URL from developer
[ ] Developer's requested credential list
```

Apple's current documentation says registering a Services ID requires the **Account Holder** or **Admin** role.

If you do not have the right access, ask the company's Apple Developer Account Holder/Admin to complete these steps.

## Ask Your Developer for These Details Before Starting

Never guess the Return URL.

Ask your developer for the exact values before making changes in Apple Developer.

| Information | Example | Who provides it |
| --- | --- | --- |
| Website domain | `example.com` | Developer |
| Website URL | `https://example.com` | Developer |
| Return URL | `https://example.com/auth/apple/callback` | Developer |
| Services ID format | `com.company.website` | Developer / Client |
| Apple Client ID variable | `APPLE_CLIENT_ID` | Developer |
| Additional credentials required | Team ID / Key ID / Private Key | Developer |

The **Return URL** is the address where Apple sends the user after Apple login. It must be an absolute URL, which means it includes:

- Scheme, such as `https://`
- Host, such as `example.com`
- Path, such as `/auth/apple/callback`

## Client vs Developer Responsibilities

### Client does

```text
Create/configure Apple Developer resources
```

### Developer provides

```text
Website domain
Return URL
Required credential list
```

### Developer does

```text
Server-side authentication
Client secret generation
JWT generation
Private key integration
Backend configuration
```

This separation matters. The client should own the Apple Developer resources, while the developer should handle the website implementation.

## Step 1 — Open Apple Developer

Open the official [Apple Developer account page](https://developer.apple.com/account/).

1. Sign in.
2. Use the Apple Developer account that belongs to the company or team.
3. Do not use a personal account if the company should own the configuration.

Do not give your Apple password, 2FA code, or recovery codes to your developer.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 2 — Make sure you have the right access

Apple's current documentation requires the **Account Holder** or **Admin** role for registering a Services ID.

If you cannot access the required configuration, do not try to bypass permissions.

Ask the company's Apple Developer Account Holder/Admin to complete these steps.

## Step 3 — Find the existing App ID

An **App ID** identifies an Apple application in the Apple Developer account.

This is normally related to the company's Apple app, such as an iOS app, macOS app, tvOS app, or watchOS app.

Do not randomly create a new App ID.

For website Sign in with Apple, Apple requires the website's Services ID to be associated with an existing primary App ID that has Sign in with Apple enabled.

Open:

```text
Certificates, Identifiers & Profiles
↓
Identifiers
```

Find the relevant App ID for the company's application.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 4 — Make sure Sign in with Apple is enabled

Open the relevant App ID and check its capabilities.

A **capability** is an Apple feature that an app is allowed to use.

Follow this general path:

```text
Certificates, Identifiers & Profiles
↓
Identifiers
↓
Relevant App ID
↓
Capabilities
↓
Sign in with Apple
```

Make sure **Sign in with Apple** is enabled.

Apple allows an App ID to be configured as a primary App ID or grouped with an existing primary App ID.

A **primary App ID** is the main Apple application identifier that can be associated with your website's Services ID.

If the existing application already has a primary App ID, use it. Do not change grouping settings unless the developer or Apple Developer Account Holder/Admin confirms that it is necessary.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 5 — Create a Services ID

Follow Apple's current flow:

```text
Certificates, Identifiers & Profiles
↓
Identifiers
↓
+
↓
Services IDs
↓
Continue
```

This starts the process of creating the Services ID for the website.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 6 — Enter a description

The description is a label that helps you recognize the Services ID later.

Example only:

```text
Website Login
```

Use a description that makes sense for your company or website.

## Step 7 — Enter the Services ID

Apple requires a unique identifier for the Services ID. Apple describes this as a reverse-domain-style string.

Example only:

```text
com.example.website
```

Do not copy the example.

Your developer may provide the exact identifier. If your developer has already specified:

```text
APPLE_CLIENT_ID=
```

ask them whether they want the Services ID to use a specific identifier.

Do not invent identifiers without understanding the company's naming style or application setup.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 8 — Register the Services ID

Review the information.

If everything is correct, click **Register**.

After registration, the Services ID will appear in the list of identifiers.

## Step 9 — Configure Sign in with Apple

Now configure the Services ID for website login.

Follow Apple's current flow:

```text
Select the Services ID
↓
Select Sign in with Apple
↓
Configure
```

This connects the website identifier to the Apple application.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 10 — Select the primary App ID

Apple will ask which primary App ID is associated with the website.

Select the company's existing primary App ID that has Sign in with Apple enabled.

Do not create a new application just because the list is confusing.

If the correct App ID does not appear, stop and ask the developer or Apple Developer Account Holder/Admin before continuing.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 11 — Add the website domain

Apple needs to know which website or domain is associated with Sign in with Apple.

Apple's current documentation says website configuration can include domains, subdomains, and return URLs.

Example domain only:

```text
example.com
```

Example subdomain only:

```text
login.example.com
```

Do not copy these examples. Do not add a domain you do not own or are not authorized to use.

Your developer should provide the exact domain.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 12 — Verify the website domain

Apple's current Sign in with Apple documentation says domains and subdomains used for website authentication must be registered and verified.

**Domain verification** means proving to Apple that your team controls the website domain or is authorized to use it.

Apple needs this so a random person cannot connect Sign in with Apple to a domain they do not own.

Use only the exact production domain or subdomain your developer provides. Do not guess.

Examples only:

```text
example.com
```

```text
login.example.com
```

Do not copy these examples.

Follow the verification and configuration instructions shown in Apple Developer for your account.

If the website or domain configuration requires technical help, ask your developer to assist.

Ask your developer to confirm when the domain has been verified.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 13 — Add the Return URL

The **Return URL** is the address where Apple sends the authentication response after the user signs in.

Example only:

```text
https://example.com/auth/apple/callback
```

Use the exact Return URL provided by your developer.

Apple requires the URL to be absolute and include:

- Scheme, such as `https://`
- Host, such as `example.com`
- Path, such as `/auth/apple/callback`

These are not the same:

```text
https://example.com
```

```text
https://example.com/auth/apple/callback
```

The developer must provide the correct URL.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## Step 14 — Save the website configuration

Follow Apple's current sequence:

```text
Done
↓
Continue
↓
Review
↓
Save
```

After saving, the Services ID should be associated with the selected primary App ID, website domain, and Return URL.

## Step 15 — Find your Apple Client ID

For website Sign in with Apple, the Services ID is used as the client identifier.

Use this format when sending it to your developer:

```text
APPLE_CLIENT_ID=YOUR_SERVICES_ID
```

Example only:

```text
APPLE_CLIENT_ID=com.example.website
```

Do not copy the example. Use your actual Services ID.

> **Screenshot:** To be added after manual verification of the current Apple Developer interface.

## What is the Apple Team ID?

The **Team ID** identifies your Apple Developer team.

Some server-side implementations require it.

Do not confuse Team ID with Services ID:

```text
Services ID → identifies the website/service
Team ID → identifies the Apple Developer team
```

Send the Team ID only if your developer requests it.

## What is the Key ID?

The **Key ID** identifies a private key created in the Apple Developer account.

It is commonly used together with the private key for server-side authentication.

It is not a password, but it identifies a sensitive credential. Send it only if your developer requests it.

## What is the Apple Private Key?

A **private key** is a sensitive credential used by the server to prove its identity to Apple.

Apple's documentation says private keys should never be shared outside your developer team.

Do not:

- Put it in GitHub
- Put it in a public README
- Paste it into a public issue
- Send it through an unsecured public channel

If the developer needs the private key, use the secure transfer method agreed with the development team.

Do not paste the actual private key into this documentation.

## What about the Apple Client Secret?

Some Apple server-side implementations use a client secret generated as a JWT.

A **JWT** is a signed token. In simple terms, it is a secure message the server creates to identify itself to Apple.

Do not manually generate a JWT unless your developer specifically asks you to.

In most projects, the developer should generate and configure the client secret using the required Apple Team ID, Key ID, Services ID, and private key.

This is an implementation detail and should not be forced on a non-technical client.

## What to Send to Your Developer

For the immediate requirement:

```text
APPLE_CLIENT_ID=YOUR_SERVICES_ID
```

Depending on the implementation, the developer may also request:

```text
APPLE_TEAM_ID=
APPLE_KEY_ID=
APPLE_PRIVATE_KEY=
```

Only provide additional credentials if your developer specifically requests them.

Private credentials must be transferred securely.

## Copy-Paste Handover Template

```text
Apple Sign in with Apple Setup Completed

APPLE_CLIENT_ID=________________________________
```

```text
Website:
________________________________

Services ID:
________________________________

Primary App ID:
________________________________

Website domain configured:
Yes / No

Website domain verified:
Yes / No

Return URL configured:
Yes / No

Sent to developer:
Yes / No
```

Do not paste a private key, client secret, Apple password, 2FA code, or recovery code into this template.

## Security

### Identifier values

These identify Apple resources:

```text
Services ID
Team ID
Key ID
```

Identifier values may be needed by your developer for legitimate setup.

### Sensitive credentials

These must remain protected:

```text
Private Key
Client Secret
Account password
2FA code
Recovery codes
```

Apple's documentation says private keys should not be shared outside your developer team. If a private key is needed, transfer it only through the secure method agreed with the development team.

## Common Problems

### Problem 1 — Services ID cannot be configured

Possible causes:

- No appropriate primary App ID exists.
- Sign in with Apple is not enabled for the App ID.
- The user does not have the required Apple Developer permissions.

Solution:

Ask the Account Holder/Admin or developer to check the App ID and account access.

### Problem 2 — Website domain cannot be configured

Possible causes:

- Incorrect domain
- Domain not verified
- Domain not configured as expected
- Wrong Services ID
- Wrong primary App ID association

Ask your developer to confirm the exact domain, whether the domain has been verified, and whether the correct Services ID and primary App ID are being used.

### Problem 3 — Invalid redirect / return URL

The Return URL must match the URL used by the website.

Check:

- `https` vs `http`
- Domain
- Subdomain
- Path
- Trailing slash
- Exact URL

Never guess this value. Ask your developer for the exact Return URL.

### Problem 4 — Apple login works but server authentication fails

This can involve:

- Team ID
- Key ID
- Private Key
- Client Secret
- Services ID
- JWT configuration

This part should normally be handled by the developer.

The client should not try to fix server-side authentication configuration unless the developer asks them to.

### Problem 5 — Private key is missing

Apple private keys need to be created and downloaded when configured.

If the original private key file was lost, the developer may need to create a new key.

Do not assume Apple will let you download the original private key again.

## Optional: Apple Private Email Relay

Sign in with Apple may allow users to hide their real email address and use an Apple private relay email address.

If the website needs to send email to users who choose Apple's private relay email address, additional Apple email relay configuration may be required.

Ask your developer if this applies to your website.

## Optional: Server-to-Server Notifications

Apple supports server-to-server notifications for advanced account changes.

This is an advanced developer feature and is not required simply to create the website's Apple Client ID.

Ask your developer if this applies to your project.

## FAQ

### What is the Apple Client ID?

For website Sign in with Apple, the Apple Client ID is usually the Services ID created in Apple Developer.

### What is an Apple Services ID?

It is the website identifier Apple uses for Sign in with Apple. It is the value your developer may use as APPLE_CLIENT_ID.

### Is the Services ID the same as the Apple App ID?

No. The App ID identifies the Apple app; the Services ID identifies the website or web service connecting to Apple.

### What is the Return URL?

It is the exact address where Apple sends the user after authentication. It must match the website configuration exactly.

### Do I need to send the Apple private key?

Only if your developer specifically requests it and gives you a secure transfer method. Private keys should never be shared publicly.

### What is the Team ID?

It identifies the Apple Developer team. It is required only for some server-side implementations.

### Why does Apple login fail on the return URL?

This usually means the Return URL does not match the exact value configured in Apple Developer.

### Why does the website domain fail to verify?

Usually because the domain is incorrect, not verified, or not associated with the correct Services ID and App ID.

### What should I send to my developer?

Usually:

```text
APPLE_CLIENT_ID=YOUR_SERVICES_ID
```

Only send additional Apple credentials if the developer specifically requests them through a secure transfer method.

## Final Checklist

```text
[ ] Apple Developer account available
[ ] Account Holder/Admin access confirmed
[ ] Existing App ID found
[ ] Sign in with Apple enabled
[ ] Primary App ID identified
[ ] Services ID created
[ ] Services ID registered
[ ] Sign in with Apple configured for Services ID
[ ] Primary App ID associated
[ ] Website domain configured
[ ] Website domain verified
[ ] Return URL configured
[ ] Services ID copied
[ ] APPLE_CLIENT_ID prepared
[ ] Additional credentials identified if required
[ ] Private key kept secure
[ ] Developer received required values securely
```

## Official Apple Documentation

- [Register a Services ID](https://developer.apple.com/help/account/identifiers/register-a-services-id/)
- [Configure Sign in with Apple for the web](https://developer.apple.com/help/account/capabilities/configure-sign-in-with-apple-for-the-web/)
- [Configuring your environment for Sign in with Apple](https://developer.apple.com/documentation/signinwithapple/configuring-your-environment-for-sign-in-with-apple)
- [Enable app capabilities](https://developer.apple.com/help/account/identifiers/enable-app-capabilities/)
- [About Sign in with Apple](https://developer.apple.com/help/account/capabilities/about-sign-in-with-apple/)
- [Create a Sign in with Apple private key](https://developer.apple.com/help/account/capabilities/create-a-sign-in-with-apple-private-key/)
- [Create a private key to access a service](https://developer.apple.com/help/account/keys/create-a-private-key)
- [Sign in with Apple documentation](https://developer.apple.com/sign-in-with-apple/)

## Related Guides

[Back to Social Login Setup Guide](../../README.md)

[Google Login Setup](../google/README.md)

[Facebook Login Setup](../facebook/README.md)
