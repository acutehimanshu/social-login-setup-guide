# OAuth Redirect URI Explained

An OAuth redirect URI is the address where Google, Apple, Facebook, or another provider sends the user after login.

Some providers call this a redirect URI. Others may call it a callback URL, return URL, or redirect URL. Do not assume every provider uses exactly the same wording.

## Simple Flow

```text
User
 ↓
Website
 ↓
Google / Apple / Facebook
 ↓
User logs in
 ↓
Provider sends user back
 ↓
Redirect / Callback URL
 ↓
Website completes login
```

## Why the URL must match exactly

The provider checks the redirect URI for safety. It wants to make sure users are sent back only to an address that was approved in the provider dashboard.

The URL usually must match exactly. A small difference can cause login to fail.

Common differences include:

- `http` instead of `https`
- A missing or extra trailing slash
- A different subdomain
- A different path
- A local testing URL used on the production website

## Examples

These are examples only. Do not copy them unless your developer confirms they are correct for your website.

Example website:

```text
https://example.com
```

Example redirect URI:

```text
https://example.com/auth/callback/google
```

Example local testing redirect URI:

```text
http://localhost:3000/auth/callback/google
```

## Important Rule

Never guess the redirect URI or callback URL.

The developer should provide the exact URL that must be entered in the provider dashboard.
