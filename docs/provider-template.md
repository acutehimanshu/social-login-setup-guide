# How to Get [Provider] Client ID for Website Login

This is an internal template for contributors who want to add a new provider guide.

Use this structure to keep new provider documentation consistent with the rest of the repository.

## Overview

Explain the goal in plain English.

This guide helps a non-technical client understand how to create or configure the provider app and return the correct value the developer needs for website login.

Keep this section short and practical.

## What are we trying to get?

Explain the main goal in one or two short paragraphs.

For example:

- create or access the correct provider application
- configure the website domain and redirect URL
- get the correct public identifier for the website login flow
- understand what must stay private

Do not assume all providers use the same credential names. Use provider-specific language.

## What is [Provider]?

Explain what the provider is in plain English.

This section should answer:

- what the provider does
- why a site might use it for login
- how the provider relates to the website

Keep the explanation simple and beginner-friendly.

## Before You Start

Before writing the provider guide, check the current official documentation first.

Contributors should confirm:

- the current dashboard flow
- the current menu names and screens
- the current app setup process
- the current redirect or callback configuration process
- whether the provider requires a live app, review, or verification step

Important reminder:

- verify official documentation first
- do not guess
- do not assume the process is the same as another provider
- do not rely on older notes or community screenshots as the main source

## Ask Your Developer for These Details

Include a short list of exact values the developer should provide to the client before setup begins.

Examples:

- website URL
- production domain
- local or staging domain if needed
- redirect URI or callback URL
- allowed domain or origin details if the provider requires them
- any provider-specific app naming or environment details

The developer should provide the exact values. The client should not guess them.

## Client vs Developer Responsibilities

Use a simple two-column style summary.

### Client responsibilities

- owns the provider account
- creates or updates the app
- provides the correct app identifier or value requested by the developer
- confirms the correct website domain and environment

### Developer responsibilities

- gives the exact website and callback details
- explains what the client needs to create or configure
- checks the app integration on the website
- verifies the login flow works correctly after the client returns the value

This separation should remain clear and simple.

## Step 1 — Provider Account

Explain how the client creates or accesses the relevant provider account.

Include:

- what account is needed
- whether a business or personal account is acceptable
- whether there are special account requirements
- whether login or setup access is shared with the developer

Do not say a personal account is required unless the provider actually requires it.

## Step 2 — Create Application

Explain how the client creates the app or project in the provider dashboard.

Include:

- where the app is created
- what the app is named
- what website or project the app belongs to
- whether a development or live app is being created

Do not overstate review requirements. State only what is actually required by the provider.

## Step 3 — Configure Website

Explain what website details must be added to the provider app.

Examples:

- website URL
- domain
- subdomain
- local or staging domain if required
- JavaScript origin where applicable

Use provider-specific terminology correctly. Do not imply that a Google Client ID and an Apple Services ID are the same type of value.

## Step 4 — Configure Redirect URI

Explain the redirect or callback setup in plain language.

Include:

- what a redirect URI is
- why the value must match exactly
- examples of common mismatch reasons
- the rule that the exact value must come from the developer

Important:

- do not guess redirect URI values
- explain `http` vs `https`
- explain domain differences
- explain subdomain differences
- explain path and trailing slash differences
- explain localhost vs production differences

## Step 5 — Configure Required Permissions

Explain any permissions, scopes, or access the provider requires.

Keep this section provider-specific and precise.

Do not claim broad access is required unless the provider genuinely requires it.

## Step 6 — Create/Get Client ID

Explain where the client finds the required value and how it is named in that provider.

This section should clearly explain:

- what the value is
- whether it is a public identifier or a secure credential
- where the client should copy it from
- which value should be returned to the developer

Use the provider’s actual terminology. Do not flatten all providers into one generic label.

## Step 7 — Additional Credentials

Explain whether the provider requires extra credentials, keys, or sensitive values.

Important:

- do not create fields asking clients to paste private keys into a public Markdown file
- do not tell clients to share secrets in a public document
- only mention additional credentials when they are actually required by the provider and developer
- say that sensitive items must be shared using a secure transfer method if needed

## What to Send to Your Developer

Explain exactly what the client should return after setup.

This may include:

- the provider app identifier
- website URL
- domain details
- redirect URI or callback URL
- any required provider-specific value that the developer asked for

Do not include security-sensitive values unless the developer specifically requests them through a secure method.

## Security

Explain the difference between identifiers and secrets.

A good security section should say:

- never publish passwords
- never publish OTP or recovery codes
- never publish client secrets, private keys, tokens, or refresh tokens
- only send sensitive values through a secure method when specifically requested

Never publish credentials.

## Development vs Production

Explain the difference between a testing app and a live app.

Include:

- local development setup
- staging setup if used
- production or live setup
- when a provider may require different values by environment

## Common Problems

List the issues that are commonly confusing to non-technical clients.

Examples:

- redirect URI mismatch
- wrong app selected
- domain mismatch
- app still in development mode
- login works locally but not in production
- wrong environment used
- provider review or verification requirements

Keep these in plain English and explain when the client should contact the developer.

## FAQ

Add a short FAQ with the questions a beginner is likely to ask.

Examples:

- What is this value?
- Is this a password?
- Why does the developer need this?
- Why does the provider behave differently?
- Why does login work on one domain but not another?
- What should I keep private?

## Final Checklist

Add a final checklist the client can review before sending anything back to the developer.

Example checklist items:

- provider account created
- app created
- correct website entered
- redirect URI or callback URL checked
- correct domain used
- correct environment selected
- required identifier copied
- no secrets shared publicly
- developer has reviewed the value

## Official Documentation

Include a list of the official provider documentation links used for the guide.

This section should be clean and factual.

## Related Guides

Link to any relevant repository resources, such as:

- [README](../README.md)
- [Glossary](glossary.md)
- [Client FAQ](client-faq.md)
- [Troubleshooting center](../troubleshooting/README.md)
- [Templates](../templates/client-credential-request.md)

## Contributor Notes

When writing a provider guide, contributors should remember:

- verify official documentation first
- do not guess
- explain technical terminology simply
- never publish credentials
- do not overstate App Review requirements
- do not mark a guide verified without manual verification
- use provider-specific terminology correctly

This template is meant to keep the repository consistent without making the documentation sound identical across providers.

[Back to main README](../README.md)
