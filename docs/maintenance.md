# Documentation Maintenance Guidelines

This repository is a practical guide for social login setup. Provider dashboards change over time, and those changes can affect app setup, redirect URIs, permissions, approval requirements, and terminology.

This document explains how to keep the documentation accurate and honest.

[Back to main README](../README.md)

## Why Updates Are Needed

Provider dashboards, policies, permissions, and requirements can change without notice.

Examples include:

- a new app type or login flow
- changed dashboard names or sections
- a changed redirect URI requirement
- a new review or verification step
- changed domain or URL rules
- different permissions or consent screens
- new security or development mode requirements

Because these changes happen often, this repository should be reviewed regularly and updated when the provider process changes.

## What Should Be Checked

For each provider guide, contributors should check the current setup process for the following areas:

### Account creation

- whether the correct account type is still required
- whether a business account or developer account is required
- whether the setup steps changed

### Application creation

- whether the app creation flow is still the same
- whether names, sections, or menu labels changed
- whether new app types are required

### Credential creation

- whether the provider still uses the same credential names
- whether the credential is created in a different screen or menu
- whether a new internal identifier or configuration step was added

### Redirect URI configuration

- whether redirect URLs or callback URLs are still configured in the same place
- whether matching rules changed
- whether the provider now expects exact host, path, or trailing slash rules

### Domain configuration

- whether the website domain or subdomain needs to be added differently
- whether custom domains or verified domains are still required
- whether localhost or staging setup is handled differently

### Production requirements

- whether live mode requires additional verification
- whether the website domain must be verified before login works
- whether a production app must be used instead of a development app

### Review requirements

- whether app review is still required for some access
- whether certain permissions require provider approval
- whether business verification is required before certain features are enabled

### Security requirements

- whether new secret handling or verification steps were introduced
- whether certain credentials are now required to stay in a private backend environment
- whether the provider now warns against exposing tokens or app secrets publicly

### Official documentation links

- whether the linked provider docs still exist
- whether the UI or process changed enough that the old guide needs revision
- whether the provider added new official help pages or removed older ones

## How to Report Outdated Instructions

When a contributor finds that documentation is no longer accurate, they should report the issue clearly and with enough detail to help someone fix it.

A good report should include:

- the provider name
- the guide file or section that appears outdated
- the current issue
- what changed, if known
- the official documentation source that shows the new process

Examples of issues to report:

- broken links
- changed UI or menu names
- changed terminology
- new requirements
- removed fields
- new errors or warnings
- different workflow in the provider dashboard

A contributor should not silently keep using outdated instructions when a provider experience clearly changed.

## Source Priority

When verifying setup information, use the following priority order:

1. Official provider documentation
2. Official provider dashboard
3. Official provider support or help center
4. Community sources only as supporting evidence

This order matters because provider dashboards and docs are the most reliable sources. Community guides can help explain a workflow, but they should not replace the provider’s official instructions.

## Verification

A guide should not be marked as verified unless the current process has actually been followed.

This means contributors should only label a guide as verified if they have:

- checked the official provider documentation
- checked the current provider dashboard or app flow
- followed the actual setup steps for the provider
- confirmed the described values, names, and requirements still match the current experience

If a contributor has only read general instructions or reused older documentation, the guide should not be treated as verified.

The repository should prefer honest wording such as:

- verified
- text reviewed
- text complete but not manually verified
- verification pending

This keeps the documentation accurate and avoids claiming certainty that has not been tested.

## Last Reviewed

In the future, provider guides may include a simple metadata section like this:

```text
Last reviewed:
Provider documentation checked:
Guide status:
```

This helps keep the project honest and easy to maintain.

Do not invent review dates for this task. The metadata section is only a recommendation for future updates.

## Recommended Contributor Habit

Before making changes to a provider guide, contributors should:

- open the current official provider docs
- check the live dashboard if access is available
- compare the current process with the existing instructions
- update or remove any section that no longer matches the current experience
- note the source of the change

This helps the repository stay useful for both developers and non-technical clients.

[Back to main README](../README.md)
