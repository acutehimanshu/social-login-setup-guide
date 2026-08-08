# Account Permission Problems

## Problem

The app is configured, but certain users or accounts cannot complete login.

### What you see

- access denied
- only one user can log in
- some users cannot complete the flow
- the app appears to work, but access is still blocked

### What it usually means

There may be permission restrictions, account roles, app restrictions, or provider settings that limit who can use the app.

### What the client can check

- confirm the correct provider account owns the app
- check whether the account is verified and active
- confirm the user has access to the right account or permissions

### What the developer should check

- review app user restrictions and allowed accounts
- confirm the app is not still set to internal or restricted testing use
- verify whether additional account verification is required

### When to contact the provider

Contact the provider if the account and permissions appear correct on the project side but access is still restricted.

[Back to Social Login Troubleshooting Center](README.md)
