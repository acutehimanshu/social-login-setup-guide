# Social Login Troubleshooting Center

This guide is for clients who are stuck during social login setup and are asking:

> What is probably wrong, and when should I contact my developer?

This is not a coding manual. It is a beginner-friendly checklist for understanding common provider login issues.

## Start Here

Most social login problems are caused by one of these:

- redirect URI mismatch
- wrong provider app or credential
- production domain not configured
- app still in development or review mode
- missing permission or developer configuration
- a credential copied from the wrong environment

Use this guide to narrow down the issue before contacting your developer.

## Quick Links

- [Google guide](../docs/google/README.md)
- [Apple guide](../docs/apple/README.md)
- [Facebook guide](../docs/facebook/README.md)
- [Glossary](../docs/glossary.md)
- [Client credential request template](../templates/client-credential-request.md)
- [Redirect URL checklist](../templates/redirect-url-checklist.md)
- [Client handover](../templates/client-handover.md)

[Back to main README](../README.md)

---

## 1. Redirect URI mismatch

## Problem

The login page opens, but users are sent back to a page that fails, shows an error, or loops.

### What you see

- “redirect_uri_mismatch” or a similar error
- login works on one URL but not another
- users return to the website but the flow stops

### What it usually means

The provider is comparing the redirect URI or callback URL it was told to use with the one the website is actually sending. They do not match.

### What the client can check

- confirm the exact website URL the developer is using
- check whether the site is using `http` or `https`
- check whether the domain is the live site or a staging site
- confirm the path after the domain is exactly the same
- check whether the URL has a trailing slash difference
- make sure the site is not using `localhost` when the app expects the live site

### What the developer should check

- confirm the exact redirect URI configured in the provider dashboard
- verify the callback route used by the website code
- ensure the redirect URI exactly matches the provider configuration
- confirm staging and production values are not mixed up
- review whether the app expects a different callback path than the website is using

### When to contact the provider

Contact the provider only if the developer has already confirmed the exact correct redirect URL and the provider still rejects it. In most cases, the issue is a mismatch in the dashboard or app configuration.

---

## 2. Wrong Client ID / App ID / Services ID

## Problem

The login page is loading, but the provider says the app is not recognized or the site is using the wrong identity.

### What you see

- app not found
- invalid client ID
- provider says the application cannot be used
- login fails only for one website or one environment

### What it usually means

The website is likely using a credential from the wrong provider app, wrong account, or wrong environment.

### What the client can check

- confirm the app belongs to the correct provider account
- check whether the credential was created for the correct website
- compare the value the developer copied with the value shown in the provider dashboard
- confirm the app is not from a different project or test account

### What the developer should check

- confirm the correct Client ID, App ID, or Services ID is being used in the website config
- check whether a test app credential is being used in production
- confirm the provider app matches the website domain and environment
- compare the value in the code or config to the value in the provider dashboard

### When to contact the provider

Only contact the provider if the credential has been confirmed to be correct in the dashboard and still appears invalid. Usually this is a configuration mismatch rather than a provider-side outage.

See also: [Client ID guide](client-id.md)

---

## 3. Wrong Client Secret

## Problem

The site is failing during the token exchange or backend authorization step.

### What you see

- invalid client secret
- authentication fails after login is approved
- the flow stops after the provider returns the user
- logs show token exchange or callback errors

### What it usually means

The website is using an incorrect secret, an old secret, or a secret copied from the wrong app or environment.

### What the client can check

- do not paste or send secrets in public messages or browser consoles
- confirm the secret clearly belongs to the correct provider app
- check whether a production secret is being used in the wrong environment

### What the developer should check

- verify the secret is valid in the provider dashboard
- check whether the secret is expired, rotated, or mismatched
- confirm the secret is stored on the server and not exposed in frontend code
- confirm the value being used matches the exact provider app that owns the login flow

### When to contact the provider

Contact the provider only if the secret is valid and correctly copied but still fails. In most cases, the issue is a mismatch or an environment mix-up.

See also: [Client secret guide](client-secret.md)

---

## 4. Login works locally but not in production

## Problem

The developer can test login on localhost, but the live site fails.

### What you see

- works on localhost or staging
- fails on the production domain
- provider says domain or redirect is not allowed

### What it usually means

The app was configured for local testing, but the live domain was not added to the provider configuration.

### What the client can check

- confirm the live website domain is correct
- confirm the domain matches the one the developer is using in the app
- check whether the live site uses `www` or a different subdomain
- confirm the site uses `https` on production

### What the developer should check

- compare the localhost settings to the live settings
- confirm the production domain is listed in the provider dashboard
- verify the redirect URI uses the production URL, not the local URL
- check whether the app has separate values for local and live environments

### When to contact the provider

Contact the provider only after the developer confirms the correct live domain and redirect URL are already configured but still not accepted.

See also: [Development vs production guide](development-vs-production.md)

---

## 5. Login works for the developer but not normal users

## Problem

Only the developer or test account can log in, but end users cannot.

### What you see

- the developer can complete login
- real users hit an error or permission screen
- users are blocked in a way the developer is not blocked

### What it usually means

The app may still be restricted to a small set of users, a different account, or a provider feature that is not yet available to the public.

### What the client can check

- confirm the app is meant for public use
- check whether only a specific account or email is allowed
- confirm the app is not still limited to internal testing

### What the developer should check

- confirm the app is in the correct mode for public use
- check whether the provider requires additional review
- verify whether the app’s allowed users or access settings are restricted
- review whether a different provider account is being used than the live one

### When to contact the provider

Contact the provider if the app is intended to be public and the developer has already confirmed that the configuration and permissions are correct.

---

## 6. Provider application still in development mode

## Problem

The login flow is blocked or limited because the provider app is still in testing or development mode.

### What you see

- limited testing only
- app not available to everyone
- screens showing testing mode or restricted use

### What it usually means

The provider app may not yet be approved for public use or may still be configured for internal testing.

### What the client can check

- ask whether the app is meant to be public or still under internal testing
- check whether the project is in the provider dashboard and whether it says “development” or “live”

### What the developer should check

- confirm the app mode matches the project status
- verify whether the site should be using a live or production app
- review whether a test app is being used for the live website

### When to contact the provider

The provider is usually not needed unless the dashboard says the app is in a valid live state and the issue still remains. In most cases, this is a configuration issue, not a support issue.

---

## 7. Account permission problem

## Problem

The provider account is configured, but the app cannot be used properly because the account or user lacks permission.

### What you see

- access denied
- app is there but cannot be used
- user cannot complete login or the provider asks for permission changes

### What it usually means

There may be permission settings, restricted roles, or incomplete business/account setup on the provider side.

### What the client can check

- confirm the correct account owns the provider app
- check whether the account is verified and active
- confirm the person managing the app has access to the right settings

### What the developer should check

- confirm the app owner account is the correct one for the live website
- review whether the app or dashboard settings restrict certain users or roles
- check whether the app requires additional account verification or admin access

### When to contact the provider

Contact the provider if the correct account and permissions are already in place but the app still appears blocked or restricted.

See also: [Account permissions guide](account-permissions.md)

---

## 8. Domain configuration problem

## Problem

The site is configured for one domain, but the provider expects another.

### What you see

- domain mismatch errors
- login fails only on the live domain
- local or staging works but the production site fails

### What it usually means

The provider dashboard has a different domain, subdomain, or host than the one the live website is using.

### What the client can check

- confirm the exact main domain and any subdomains
- check whether the site uses `www` or a custom subdomain
- review whether a development URL is still set instead of the production domain

### What the developer should check

- confirm the exact domain name configured in the provider dashboard
- verify the site is using the same host value in the app config
- check whether the domain was entered with a missing or extra `www`, or a different path

### When to contact the provider

Contact the provider if the domain values have already been checked and still fail to match correctly.

---

## 9. App Review / verification issue

## Problem

The app seems configured correctly, but certain permissions or login flows are still blocked.

### What you see

- access to some user information is blocked
- provider says the app is not approved
- the app works in a limited way but not for full public use

### What it usually means

The provider may require app review, business verification, or additional confirmation before full access is allowed.

### What the client can check

- confirm whether the app is expected to be public or only internal testing
- check whether the provider dashboard says the app requires review or verification

### What the developer should check

- confirm which permissions the app requests
- verify whether a review or verification step is required for the requested user data
- review whether the app is using a restricted mode instead of full public access

### When to contact the provider

Contact the provider after confirming the app is intended for public use and the review requirements have been reviewed.

---

## 10. Wrong provider application

## Problem

The credentials belong to a different site or a different provider app entirely.

### What you see

- login works for one project but not another
- the developer and client are looking at different provider dashboards
- credentials do not match the intended website

### What it usually means

The app being used is not the same one created for the project.

### What the client can check

- compare the app name, project name, and website URL on the provider dashboard
- confirm whether the credential belongs to the correct project or provider account
- check whether one app was created for testing and another for production

### What the developer should check

- confirm the correct provider dashboard project is connected to the live site
- verify the website config points to the intended app
- compare the app IDs and secrets with the project’s records

### When to contact the provider

Provider support is usually not needed unless the client and developer are both certain the correct app is selected and the provider still rejects it.

---

## 11. Credential belongs to another environment

## Problem

A value from a testing environment is being used in production, or vice versa.

### What you see

- works only on localhost
- works only on staging
- login breaks after deployment

### What it usually means

The project has multiple environments, and the wrong app or credential is being used for the live system.

### What the client can check

- ask which environment the app is meant for
- confirm whether the site is live, staging, or local
- review whether the developer copied the credential from a test project instead of the final one

### What the developer should check

- confirm the environment mapping for each app
- ensure production settings do not reuse test credentials
- verify that the app dashboard for production matches the live domain

### When to contact the provider

Contact the provider only after confirming the developer is using the correct environment-specific app and the provider still rejects the configuration.

---

## 12. Provider dashboard configuration changed

## Problem

The provider app was configured correctly before, but now login fails unexpectedly.

### What you see

- a previously working app suddenly stops accepting logins
- the redirect URL or app settings appear different than before
- a small update or dashboard change caused the problem

### What it usually means

Something in the provider dashboard changed, such as a redirect URI, app status, permission, or domain configuration.

### What the client can check

- confirm no account or app changes were made recently
- ask whether anyone updated the project or dashboard settings
- review if the website or provider account changed ownership

### What the developer should check

- compare the provider dashboard to the documented setup values
- verify the website still matches the approved provider configuration
- look for any change in redirect route, app state, or allowed domain

### When to contact the provider

Contact the provider if the dashboard configuration was reviewed and still appears correct but the login flow fails unexpectedly.

---

## Redirect URI flow

A helpful mental model for redirect URIs is this:

```text
Website
↓
Provider
↓
Login
↓
Redirect URI
↓
Website
```

This means the user starts on the website, moves to the provider, logs in, and then is returned to a specific URL on the website.

The provider checks the return address carefully. If that address is different from the approved one, login may fail.

### Exact matching matters

Redirect URIs usually need to match exactly, including:

- `http` vs `https`
- domain name
- subdomain
- path
- trailing slash
- localhost vs production

### Examples

Examples only; these are not universal values.

- `https://example.com/auth/callback`
- `https://www.example.com/auth/callback`
- `https://app.example.com/auth/callback`
- `http://localhost:3000/auth/callback`

A redirect URI should be copied only from the developer’s exact confirmed configuration. Do not guess.

For a deeper walkthrough, see [redirect-uri.md](redirect-uri.md).

---

## Security reminder

Never paste a client secret, access token, refresh token, private key, or other sensitive value into a troubleshooting issue, ticket, screenshot, or public message.

If an error contains a token or secret, remove the sensitive value before sharing the error publicly.

---

## When to contact the developer

Contact the developer when:

- the exact website URL is unclear
- the provider app or credentials were copied incorrectly
- a redirect URI or callback URL needs to be confirmed
- the app is using the wrong environment
- the site is not configured for the live domain
- the provider dashboard values do not match the website settings

## When to contact the provider

Contact the provider only when:

- the app and dashboard values have already been checked
- the developer has confirmed the exact required settings
- the provider still rejects the login flow for a valid-looking configuration
- there is a provider-side verification, access, or review issue

---

[Back to main README](../README.md)
