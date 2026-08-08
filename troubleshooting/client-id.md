# Client ID Problems

## Problem

The login flow fails because the website is using the wrong app identifier.

### What you see

- invalid client ID
- app not recognized
- login fails before the user completes sign in
- a different app appears to be connected than the one intended

### What it usually means

The website is likely using a Client ID, App ID, or Services ID that belongs to the wrong provider app, wrong environment, or wrong account.

### What the client can check

- confirm which provider account owns the app
- check whether the value comes from the correct project
- compare the identifier with the one shown in the provider dashboard
- confirm the app is not from a test project or a different website

### What the developer should check

- confirm the app identifier matches the correct provider dashboard project
- compare the value in the website config with the value in the provider dashboard
- check whether a test credential is being used in production
- confirm the correct environment is selected

### When to contact the provider

Contact the provider only after the developer confirms the correct app identifier and the app still appears invalid.

[Back to Social Login Troubleshooting Center](README.md)
