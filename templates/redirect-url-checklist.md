# Redirect URL Checklist

Use this checklist to confirm the correct website and redirect values before the login flow is tested.

> Never guess a redirect URI. The developer must provide the exact value.

## Provider-neutral checklist

### Website details

```text
Website URL:
____________________

Environment:
Production / Staging / Local development

Domain:
____________________

Subdomain (if any):
____________________
```

### Provider settings

```text
Provider:
Google / Apple / Facebook / Other
```

```text
Website URL:
____________________

Domain:
____________________

JavaScript origin (where applicable):
____________________

Redirect URI / Callback URL / Return URL (where applicable):
____________________

Production value:
Yes / No

Local or development value (if needed):
____________________
```

## Check each provider

### Google

- [ ] Website URL is correct
- [ ] Domain is correct
- [ ] JavaScript origin is correct if required
- [ ] Redirect URI is exact and matches the developer’s value
- [ ] Production value is configured
- [ ] Local or development value is listed if needed

### Apple

- [ ] Website URL is correct
- [ ] Domain is correct
- [ ] Return URL or callback URL is exact
- [ ] Production value is configured
- [ ] Local or development value is listed if needed
- [ ] Domain or app setup matches the developer’s instructions

### Facebook

- [ ] Website URL is correct
- [ ] Domain is correct
- [ ] Redirect URI or callback URL is exact
- [ ] Production value is configured
- [ ] Local or development value is listed if needed
- [ ] App configuration matches the developer’s instructions

## Common exact-match checks

Before sending the values, confirm:

- `http` vs `https`
- `www` vs non-`www`
- subdomain differences
- path differences
- trailing slash differences
- localhost vs live website
- staging vs production

## Final confirmation

```text
Exact redirect URI provided by developer:
____________________

Does it match the website and environment exactly?
Yes / No

Approved by developer:
Yes / No
```

If anything is unclear, ask the developer for the final approved value before testing the sign-in flow.
