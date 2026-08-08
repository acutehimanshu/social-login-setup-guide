# Social Login Troubleshooting

This section covers common OAuth setup problems that can happen with Google, Apple, Facebook, and other social login providers.

Provider-specific errors will be documented later after each provider guide is verified against the current provider dashboard.

## Common Problems

| Problem | What it usually means |
| --- | --- |
| Redirect URL mismatch | The redirect URI or callback URL entered in the provider dashboard does not exactly match the URL used by the website. |
| Wrong Client ID | The website is using a Client ID, App ID, or Services ID from the wrong provider application. |
| Wrong Client Secret | The website is using the wrong secret, or the secret was copied incorrectly. Never place secrets in public repositories. |
| Incorrect domain | The website domain entered in the provider dashboard does not match the real website domain. |
| Application still in development/test mode | The provider application may not be available to real users yet. |
| Provider account not verified | The provider may require account, business, email, domain, or developer verification before login works fully. |
| Incorrect callback URL | The website may be sending users to a callback URL that was not configured in the provider dashboard. |
| Production domain not configured | Login may work on a test domain but fail on the live website because the production domain was not added. |
| App not approved/reviewed where applicable | Some providers may require review or approval before certain features are available to all users. |

## First Checks

1. Confirm the exact website domain.
2. Confirm the exact redirect URI or callback URL.
3. Confirm the correct Client ID, App ID, or Services ID is being used.
4. Confirm the provider application belongs to the correct account.
5. Confirm production domains are configured before testing the live website.
6. Confirm no secrets were shared publicly.

For a beginner-friendly explanation, see [OAuth Redirect URI Explained](redirect-uri.md).
