# Redirect URI Troubleshooting

A redirect URI is the exact URL a provider sends the user back to after login.

Some providers call it a redirect URI. Some call it a callback URL or return URL. The idea is the same: it is the page where the login flow should continue after the user is authenticated.

## The basic flow

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

The user begins on the website, goes to the provider, signs in, and then the provider sends the user back to a configured page on the website.

## Why exact matching matters

Providers usually compare the redirect URI to the one they were configured to accept. If even one piece is different, the login may fail.

The most common exact-match problems are:

- `http` vs `https`
- `example.com` vs `www.example.com`
- a different subdomain
- a different path
- a missing or extra trailing slash
- local development URL vs production URL
- a different environment such as staging vs live

## Examples

These are examples only and should not be copied without confirmation from the developer.

```text
https://example.com/auth/callback
https://www.example.com/auth/callback
https://app.example.com/auth/callback
http://localhost:3000/auth/callback
```

If the site uses one of these values, the provider dashboard must match it exactly.

## What usually causes the problem?

Most redirect URI issues happen because one of these is true:

- the website is using a different URL than the one configured in the provider dashboard
- a staging URL was configured instead of the live URL
- a local development URL is still being used in production
- the developer changed the callback route but did not update the provider configuration
- the domain or subdomain differs from the approved value

## What the client can check

- confirm the exact live website URL
- confirm whether the site uses `www` or not
- check whether it is `http` or `https`
- review whether the value is a local or production domain
- confirm the path after the domain matches the developer’s instructions

## What the developer should check

- confirm the exact redirect URI for each environment
- verify the callback route used by the website
- compare the code route to the provider dashboard entry
- make sure the correct domain is approved for production use
- confirm there are no duplicate or old redirect values left over in the provider app

## Client reminder

Do not guess the redirect URI. The developer should provide the exact value that must be entered in the provider dashboard.

## Security reminder

If an error message includes a token, code, secret, or other sensitive value, remove it before sharing the error publicly.

### Related guides

- [Social Login Troubleshooting Center](README.md)
- [Google guide](../docs/google/README.md)
- [Apple guide](../docs/apple/README.md)
- [Facebook guide](../docs/facebook/README.md)
- [Glossary](../docs/glossary.md)

[Back to main README](../README.md)
