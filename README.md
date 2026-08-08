# Social Login Setup Guide

> Simple, step-by-step guides for configuring social login and OAuth providers for websites and applications.

This repository helps people set up social login without needing to understand every technical detail of OAuth.

A developer may ask a client for something like:

```text
GOOGLE_CLIENT_ID=
```

For a non-technical client, that can be confusing. Where do you create it? Which account should own it? What is safe to send back to the developer? What should never be shared?

This project answers those practical questions with beginner-friendly social login setup guides for Google, Apple, Facebook, and future providers.

## Who is this for?

This guide is for:

- Non-technical clients
- Startup founders
- Freelancers
- Developers
- Technical project managers
- Web agencies
- Product teams

The documentation separates three important parts:

| Part | Meaning |
| --- | --- |
| What the developer provides | The website domain, redirect URI, callback URL, and any required setup details. |
| What the client does | Creates or configures the provider application in their own account. |
| What the client sends back to the developer | The Client ID, App ID, Services ID, or other requested non-secret values. |

This keeps account ownership with the client while giving the developer the information needed to configure the website.

## Supported Providers

| Provider | Status | Guide |
| --- | --- | --- |
| Google | Available | [Google Login Setup](docs/google/README.md) |
| Apple | Available | [Apple Sign in with Apple Setup](docs/apple/README.md) |
| Facebook | Available | [Facebook Login Setup](docs/facebook/README.md) |
| Microsoft | Planned | - |
| GitHub | Planned | - |
| LinkedIn | Planned | - |
| Discord | Planned | - |
| X | Planned | - |
| Reddit | Planned | - |

## What will I get from these guides?

Each provider guide is focused on practical setup, not a deep OAuth tutorial. The guides will explain:

- What the provider credential is
- Why the credential is required
- What account is needed
- Where to create the application
- What information the developer must provide
- What the client must enter
- Where to find the Client ID, App ID, or Services ID
- Which values are secrets
- Which values are safe to share with the developer
- How redirect URLs work
- How to configure production domains
- How to test login
- Common errors
- Final handover checklist

Useful terms you may see include social login setup, OAuth setup guide, Google Client ID, Google OAuth Client ID, Apple Client ID, Apple Services ID, Sign in with Apple, Facebook App ID, Facebook Login, OAuth redirect URI, OAuth callback URL, and social login credentials.

## Developer -> Client -> Developer Flow

```text
Developer gives required information
                ↓
Client creates/configures provider application
                ↓
Client receives Client ID / App ID
                ↓
Client sends required credential to Developer
                ↓
Developer configures the website
                ↓
Social Login is tested
```

In plain English: the developer gives the client the exact website information that must be entered into Google, Apple, or Facebook. The client creates the provider application in their own account, copies the requested ID value, and sends it back to the developer. The developer then adds that value to the website and tests the login flow.

## Important Security Rules

Never share:

- Account passwords
- OTP / 2FA codes
- Recovery codes
- Private keys
- Access tokens
- Refresh tokens
- Client secrets in public repositories

Client IDs, App IDs, and Services IDs are usually identifiers. They tell the website which provider application to use.

Secrets, private keys, access tokens, refresh tokens, passwords, OTP codes, and recovery codes must be protected. Do not paste them into public issues, public repositories, screenshots, chat messages, or templates unless your developer has clearly explained why they are needed and how they will be handled securely.

## Provider Guides

- [Google Login Setup](docs/google/README.md)
- [Apple Sign in with Apple Setup](docs/apple/README.md)
- [Facebook Login Setup](docs/facebook/README.md)

## Templates

- [Client Credential Request](templates/client-credential-request.md)
- [Redirect URL Checklist](templates/redirect-url-checklist.md)
- [Client Handover](templates/client-handover.md)

## Troubleshooting

- [General Troubleshooting](troubleshooting/README.md)
- [OAuth Redirect URI Explained](troubleshooting/redirect-uri.md)

## Planned Providers

The following providers are planned for future documentation:

- Microsoft
- GitHub
- LinkedIn
- Discord
- X
- Reddit
- GitLab
- Bitbucket

Guides for these providers have not been created yet.
