# Client Secret Problems

## Problem

The login flow fails during the server-side exchange or token process.

### What you see

- invalid client secret
- token exchange error
- login appears to work partly but fails later
- error messages mention authorization or token exchange

### What it usually means

The secret is wrong, outdated, copied incorrectly, or being used in the wrong app or environment.

### What the client can check

- do not paste secrets into email, tickets, or public messages
- confirm the secret belongs to the right provider app
- check whether it was created for the correct environment

### What the developer should check

- verify the secret value matches the provider dashboard
- confirm the secret is stored securely and not exposed in frontend code
- check whether the app has rotated or changed the secret
- confirm the correct secret is used for the active environment

### When to contact the provider

Contact the provider only if the secret has already been checked and confirmed to be correct but still fails.

[Back to Social Login Troubleshooting Center](README.md)
