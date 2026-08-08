# Redirect URL Checklist

After a user logs in with Google, Apple, or Facebook, the provider needs to know where to send the user back to your website. This address is usually called a redirect URL or callback URL.

Different providers may use slightly different names, but the idea is the same: the provider sends the user back to a specific page on your website so the login can be completed.

## Important

Never guess a redirect URL.

The developer should provide the exact URL. Even a small difference can cause login to fail.

## Checklist

Provider:

```text
Google / Apple / Facebook
```

Website:

```text
____________________
```

Redirect / Callback URL:

```text
____________________
```

Configured:

- [ ] Yes
- [ ] No

Verified by developer:

- [ ] Yes
- [ ] No
