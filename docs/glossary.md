# OAuth and Social Login Glossary

This glossary explains common login and OAuth terms in plain English for beginners.

[Back to main README](../README.md)

## Social Login

**Simple meaning:** Logging in with an existing account from a provider such as Google, Apple, or Facebook instead of creating a new password on a website.

**Example:** A customer clicks “Continue with Google” on a website and signs in with their Google account.

**Why it matters:** It makes signup easier for users and helps websites offer a faster, familiar login experience.

## OAuth

**Simple meaning:** A standard way for one website or app to ask another service to confirm a user and allow limited access without sharing the user’s password.

**Example:** A website asks Google to confirm that the person is signed in and to share the user’s basic profile information.

**Why it matters:** OAuth is the foundation for many social login flows and helps separate login from password sharing.

## OAuth 2.0

**Simple meaning:** The most common version of OAuth used today for website login and app authorization.

**Example:** A site uses OAuth 2.0 to redirect a user to Google, then Google sends the user back after login.

**Why it matters:** It is the standard many providers use for social login and app authorization.

## OpenID Connect

**Simple meaning:** A layer built on top of OAuth 2.0 that adds identity information, so the app can know who the user is.

**Example:** After login, a website can receive a user identity and basic profile information from the provider.

**Why it matters:** OAuth handles access; OpenID Connect helps confirm the user’s identity.

## Authentication

**Simple meaning:** Proving that a person is who they say they are.

**Example:** Entering a username and password, or signing in using a Google account.

**Why it matters:** Authentication decides whether the user is allowed to log in.

## Authorization

**Simple meaning:** Giving an app or website permission to access something on the user’s behalf.

**Example:** A website asks for permission to read the user’s email address or profile information.

**Why it matters:** Authorization decides what a site may do after the user is signed in.

## Identity Provider

**Simple meaning:** The service that confirms a user’s identity, such as Google, Apple, or Facebook.

**Example:** Google is an identity provider when a website allows “Continue with Google.”

**Why it matters:** The identity provider is the trusted service that handles the sign-in process.

## Client

**Simple meaning:** The website or app that is asking the identity provider to log a user in.

**Example:** A storefront’s website is the client when it requests login through Google.

**Why it matters:** The client is the application that uses the login service.

## Client ID

**Simple meaning:** A public identifier that tells the identity provider which application or website is requesting login.

**Example:** Google provides a Client ID for a specific website app; Apple uses a Services ID or app-specific identifier depending on the setup.

**Why it matters:** It identifies the app to the provider, but it is not the same as a secret.

## Client Secret

**Simple meaning:** A sensitive secret used by the app or server to prove it is allowed to communicate securely with the provider.

**Example:** A backend service may use a Client Secret when exchanging authorization codes for tokens.

**Why it matters:** Secret values must stay private and should not be shared publicly.

## App ID

**Simple meaning:** A provider-specific identifier for an app or application created inside a provider dashboard.

**Example:** Meta may use an App ID for a Facebook app, and it is different from the app’s secret.

**Why it matters:** It tells the provider which app is being used, but it is not the same as a private credential.

## Services ID

**Simple meaning:** An Apple-specific app identifier used in the Sign in with Apple flow.

**Example:** Apple may require a Services ID for the website or app that is using Sign in with Apple.

**Why it matters:** Apple uses this identifier in a way that differs from Google’s Client ID or Meta’s App ID.

## App Secret

**Simple meaning:** A sensitive secret value that belongs to a provider app configuration and should be protected.

**Example:** A Meta app may include an App Secret that must be kept secure and not exposed in frontend code.

**Why it matters:** App secrets are private credentials and should never be published publicly.

## Redirect URI

**Simple meaning:** The exact URL where the provider sends the user after login or authorization completes.

**Example:** A site might use https://www.example.com/auth/callback as its redirect URI.

**Why it matters:** If the redirect URI is wrong or does not match exactly, login may fail.

## Callback URL

**Simple meaning:** Another name for the URL the provider sends the user back to after login.

**Example:** After a user approves login, the provider may bring them back to https://www.example.com/login/callback.

**Why it matters:** It is the return point for the login flow and must match the provider’s configuration.

## Authorized JavaScript Origin

**Simple meaning:** The allowed website domain that is allowed to start the login flow from browser code.

**Example:** A site may list https://www.example.com as an authorized JavaScript origin in Google’s dashboard.

**Why it matters:** This helps the provider trust the website that initiates the login request from the browser.

## Domain

**Simple meaning:** The main website name, such as example.com.

**Example:** https://example.com is a domain.

**Why it matters:** Providers often require the correct domain to be registered for login and redirect settings.

## Subdomain

**Simple meaning:** A separate section of a main domain, such as app.example.com or shop.example.com.

**Example:** shop.example.com is a subdomain of example.com.

**Why it matters:** A subdomain may need to be allowed separately because providers often check exact hostnames.

## Access Token

**Simple meaning:** A temporary credential that allows a website or app to access certain information on behalf of the user.

**Example:** A website may use an access token to read a user’s email address after login.

**Why it matters:** Tokens are commonly used after authentication to allow limited access.

## Refresh Token

**Simple meaning:** A long-lived token used to get a new access token when the old one expires.

**Example:** A backend service may store a refresh token so the user does not need to sign in again repeatedly.

**Why it matters:** Refresh tokens help keep sessions working without asking the user to re-authenticate too often.

## Scope

**Simple meaning:** A defined set of permissions that the app is asking for from the provider.

**Example:** A website may request email and profile access as part of the login flow.

**Why it matters:** Scopes control what the app is allowed to read or use.

## Permission

**Simple meaning:** A specific right the user grants to the app or website.

**Example:** The user may allow the website to read their email address or basic profile information.

**Why it matters:** Permissions explain exactly what the user is approving when they log in.

## Development Mode

**Simple meaning:** A temporary state for testing login while an app is still being built or reviewed.

**Example:** A developer may use a provider’s development mode while testing the login flow on a local or staging site.

**Why it matters:** It allows testing before the app is fully public or approved for production use.

## Production / Live Mode

**Simple meaning:** The ready-to-use state where the website is configured for real visitors and live traffic.

**Example:** A production app is the version that connects to the live domain and serves real users.

**Why it matters:** Live mode is where the real login experience is expected to work without testing restrictions.

## App Review

**Simple meaning:** A provider’s review process that checks whether an app is allowed to request certain permissions or be used by the public.

**Example:** A social login app may need review before it can request broader user data access.

**Why it matters:** Some apps must pass review before they can fully operate in production.

## Business Verification

**Simple meaning:** A provider check that confirms the business or organization behind the app is legitimate.

**Example:** A company may need to verify ownership or business details before an app can use some advanced features.

**Why it matters:** Verification helps providers reduce abuse and confirm that the app is being managed by a real organization.

## Private Key

**Simple meaning:** A secret cryptographic key used to sign or authenticate requests and secure communication.

**Example:** Apple may use a private key as part of its Sign in with Apple setup for secure server-side authentication.

**Why it matters:** Private keys are highly sensitive and must never be exposed publicly.

## Team ID

**Simple meaning:** A provider-issued identifier for the organization or team that owns the app or project.

**Example:** Apple may ask for a Team ID in some sign-in configurations.

**Why it matters:** It helps the provider associate the app with the correct company or team account.

## Key ID

**Simple meaning:** A short identifier that matches a specific cryptographic key used by a provider integration.

**Example:** Apple may use a Key ID together with a private key in certain authentication flows.

**Why it matters:** It helps identify the exact key being used without exposing the key itself.

## JWT

**Simple meaning:** JSON Web Token, a compact, signed token that carries identity or authorization information.

**Example:** A provider may send a JWT that includes user identity information after login.

**Why it matters:** JWTs are commonly used to carry trusted information between systems in a compact format.

---

[Back to main README](../README.md)
