# Social Login Setup Guide

A practical homepage for social login setup, OAuth setup guide, and website authentication handoff.

## Why This Repository Exists

A developer often asks a non-technical client for a provider credential such as:

GOOGLE_CLIENT_ID=

That request can be confusing. The client may not know:

- where the credential is created
- which account should own it
- what website URL or redirect URI should be entered
- what is safe to send back to the developer
- what must stay private

This repository solves that problem. It explains the setup process in plain language so a client can understand what to create, what to copy, and what to keep private.

## Who Is This For?

This project is designed for:

- Non-technical clients
- Startup founders
- Freelancers
- Developers
- Technical project managers
- Web agencies
- Product teams

It helps both sides of the setup:

- the client, who owns the provider account and application
- the developer, who implements the website login flow

## Quick Start

If you are a client:

- choose the provider you need
- follow the setup guide for that provider
- give the developer the exact website and redirect information they need
- copy the required identifier from the provider dashboard
- send only the required credential back to the developer

If you are a developer:

- give the client the exact website URL and redirect information
- send them the correct provider guide
- ask for only the required identifier or secure credential if needed
- configure the website and test the login flow after receiving the value

## Supported Providers

| Provider | Status | Primary credential | Guide |
| --- | --- | --- | --- |
| Google | Verified | Client ID | [Google Login Setup](docs/google/README.md) |
| Apple | Verified | Services ID / Client ID | [Apple Sign in with Apple Setup](docs/apple/README.md) |
| Facebook | Text complete / verification pending | App ID / Client ID | [Facebook Login Setup](docs/facebook/README.md) |
| Microsoft | Planned | — | — |
| GitHub | Planned | — | — |
| LinkedIn | Planned | — | — |
| Discord | Planned | — | — |
| X | Planned | — | — |
| Reddit | Planned | — | — |

> Facebook is included as a text-based guide, but it is not treated as manually verified yet.

## Provider Comparison

| Provider | Website login | Primary identifier | Additional credentials may be required | Redirect configuration | Developer involvement |
| --- | --- | --- | --- | --- | --- |
| Google | Yes | Client ID | Client Secret in some server-side setups | Authorized JavaScript origin and redirect URI | Usually website setup and login integration |
| Apple | Yes | Services ID, used as Client ID | Team ID, Key ID, private key, client secret depending on implementation | Return URL and domain verification | Usually server-side configuration and JWT handling |
| Facebook | Yes | App ID, used as Client ID | App Secret in some implementations | Valid OAuth redirect URI and app configuration | Usually website integration and testing |

## How the Process Works

Developer provides website URL, redirect details, and setup requirements.

Client creates or updates the provider application.

Client copies the correct identifier from the provider dashboard.

Client sends the required credential or identifier securely to the developer.

Developer configures the website and tests the login flow.

In plain language: the client owns the provider account and app configuration, while the developer owns the website implementation.

## Security

Never share these publicly:

- passwords
- OTP codes
- 2FA codes
- recovery codes
- private keys
- access tokens
- refresh tokens
- client secrets

Identifiers are different from secrets.

- An identifier tells the app which provider app or website is being used.
- A secret proves identity and must stay protected.

Examples of identifiers:

- Google Client ID
- Apple Services ID
- Facebook App ID

Examples of secrets:

- Google Client Secret
- Apple private key
- Facebook App Secret

Only share secrets through the secure transfer method your developer provides.

## Provider Guides

- [Google Login Setup](docs/google/README.md)
- [Apple Sign in with Apple Setup](docs/apple/README.md)
- [Facebook Login Setup](docs/facebook/README.md)

## Templates

- [Client Credential Request](templates/client-credential-request.md)
- [Redirect URL Checklist](templates/redirect-url-checklist.md)
- [Client Handover](templates/client-handover.md)

These templates help structure the communication between the client and the developer.

## Troubleshooting

- [General troubleshooting](troubleshooting/README.md)
- [OAuth redirect URI troubleshooting](troubleshooting/redirect-uri.md)

## FAQ

### What is social login?

Social login allows a visitor to sign in with an existing social account instead of creating a separate username and password.

### What is OAuth?

OAuth is a standard way for websites and apps to ask a provider to confirm a user and share limited information safely.

### What is a Client ID?

It is the public identifier for the provider application. It tells the provider which website or app is asking for login.

### What is a Client Secret?

It is a sensitive value used by a backend service or app to authenticate securely. It should never be public.

### What is a Redirect URI?

It is the exact address where the provider sends the user after login. It must match the website configuration exactly.

### Why does my developer need my provider account?

The provider account owns the application configuration. The developer needs the correct application and credential setup to connect the website to that provider.

### Can I share my Client ID?

Usually yes, if the developer requests it as part of the setup. It is a public-style identifier, not the same as a password or secret.

### Should I share my password?

No. Never share your provider account password, 2FA codes, recovery codes, or account secrets with a developer or anyone else unless a provider specifically requires it through a trusted, secure process.

### Why does login work locally but not in production?

Usually because the domain, redirect URI, or app configuration differs between localhost and the live website.

### Why are provider dashboards different?

Each provider has its own developer dashboard and terminology. The same concept may be called something slightly different in Google, Apple, or Facebook.

### Do all providers require the same credentials?

No. Each provider uses different identities, setup flows, and credential types. The project explains each one separately.

### Why does the developer need the exact callback URL?

Because a small mismatch can block the login flow. The provider expects the exact URL that the website uses after authentication.

## Planned Providers

These providers are planned for future documentation:

- Microsoft
- GitHub
- LinkedIn
- Discord
- X
- Reddit

No new provider guides are included yet.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Security

See [SECURITY.md](SECURITY.md).

## License

This project is licensed under the [MIT License](LICENSE).

## Summary

This repository is a practical social login setup guide for website social login, OAuth setup guide, social authentication, Google Client ID, Apple Services ID, Facebook App ID, OAuth redirect URI, social login credentials, and website social login. It is designed to help non-technical clients and developers work together without exposing sensitive provider credentials.
