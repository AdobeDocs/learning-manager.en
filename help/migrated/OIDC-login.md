# Sign in to Adobe Learning Manager with OpenID Connect (OIDC)

Learn how OpenID Connect sign-in works in Adobe Learning Manager for learners, authors, and administrators. This article covers the experience, not implementation.

## Understand OpenID Connect sign-in

OpenID Connect (OIDC) is a common sign-in method built on web standards. Many organizations use an identity provider (for example, Okta, Google Workspace, or Microsoft Entra ID) for employees and partners.

When your organization enables OIDC for Adobe Learning Manager:

* You sign in using your organization's usual login page, not a password that applies only to Adobe Learning Manager, unless your organization chooses otherwise.
* After you authenticate, Adobe Learning Manager receives the information your organization allows (such as your email and proﬁle attributes) and opens the right experience for you: Learner, Author, Administrator, or other roles your account supports.

OIDC is an alternative to other sign-in options your account may oﬀer, such as Adobe ID or SAML based single sign-on (SSO). Your administrator decides which methods are available.

## Why organizations choose OpenID Connect

Organizations often choose OIDC because:

* Users see the same corporate or cloud identity experience they use for other applications.
* Password policies, multi-factor authentication, and account lifecycle are managed in the identity provider, consistent with other enterprise apps.
* OIDC follows patterns similar to other modern sign-in ﬂows from a user and IT perspective, without the heavier document exchange associated with some SAML-only setups.

Your experience is still: go to Learning Manager, sign in where your organization tells you, and land in the app.

## What you see when you sign in 

### Open Adobe Learning Manager

You might use:

* The main Adobe Learning Manager URL for your environment
* A custom domain your organization conﬁgured, if applicable
* A link from an email, invitation, or self-registration page
* A bookmark or deep link to a speciﬁc course, catalog page, or resource

If your account uses OIDC, starting sign-in typically redirects your browser to your organization's identity provider.

### Sign in with your organization

On your identity provider's page, enter your credentials and complete any extra steps your organization requires, such as multi-factor authentication. This step happens outside Adobe Learning Manager's own login form when OIDC is the method in use. From your perspective, it feels like signing in to your company or school account. You might not see technical terms like *OIDC* or *OAuth* during this step.

### Return to Adobe Learning Manager

After a successful sign-in, your browser returns you to Adobe Learning Manager. The product then:

* Recognizes you using the email and proﬁle information your identity provider shares, according to your organization's settings
* Applies your permissions in Adobe Learning Manager (Learner, Author, Administrator, Integration Administrator, and so on)
* Opens the appropriate app or area (for example, the learner experience compared with admin or author experiences), consistent with how Adobe Learning Manager assigns roles for your account

If something goes wrong (for example, your account is not provisioned or your organization blocks access), you might see an error or be unable to proceed. Contact your internal IT team or Adobe Learning Manager administrator.

## Use other sign-in options with OpenID Connect

Adobe Learning Manager can support more than one sign-in method on an account (multiple SSO options). For example:

* Some users sign in with Adobe ID
* Others use SAML SSO
* Others use OIDC

Which options appear to you depends on how your account is conﬁgured. Enabling OIDC for your organization does not by itself remove other methods unless your administrators change that conﬁguration.

## Supported features and scenarios

The following behaviors are supported when your organization uses OIDC with Adobe Learning Manager, consistent with how other enterprise sign-in methods are expected to work.

### Table 1. OIDC support in common scenarios

| Area | What it means for you |
| --- | --- |
| Internal and external users | Employees and invited external users (for example, partners) can use OIDC where your administrator enables it, including ﬂows that start from self-registration links when your account is set up for that. |
| First-time access | If you are allowed by policy, your ﬁrst successful OIDC sign-in can create or link your user in Adobe Learning Manager according to your organization's rules, similar to other SSO options. |
| Proﬁle and attributes | Information such as email and other attributes can be updated from your identity provider over time, so your Adobe Learning Manager proﬁle stays aligned with your organization's directory, within what your administrator conﬁgures. |
| Deep links | Links that point to a speciﬁc page or resource in Learning Manager (not only the home page) are supported. You can land on the intended content after sign-in when your organization's setup allows it. |
| Return path | After authentication, you can return to the place you were trying to reach (for example, the same course or catalog URL you started from), rather than always landing on a generic home page. |
| Custom domain | If your company uses a custom hostname for Adobe Learning Manager, OIDC sign-in is supported in that context as well. |
| Mobile | Signing in on phones and tablets through supported browsers or experiences is supported. |
| Publish to Adobe Learning Manager (Prime) | Workﬂows that involve publishing content into Learning Manager from connected tools remain supported when your account uses OIDC, consistent with your integration setup. |
| Identiﬁer-based sign-in | Where your account relies on stable identiﬁers (beyond email alone) for matching accounts, those ﬂows are supported for OIDC according to your administrator's conﬁguration. |

If a speciﬁc workﬂow does not work, the cause might be identity provider settings, account provisioning, or Adobe Learning Manager role assignment. Your administrator can verify.

## How roles work after sign-in

Adobe Learning Manager determines what you can do from your account's roles and permissions, not from the OIDC protocol itself. OIDC only establishes who you are to the satisfaction of your identity provider and what your organization shares with Adobe Learning Manager.

* Learners typically see training, catalogs, and learning plans.
* Authors may create or curate content.
* Administrators manage users, conﬁguration, and reporting.

If you land in the wrong area or lack access you expect, ask your Adobe Learning Manager administrator to check your proﬁle and group membership.

## Troubleshooting for common issues

### Table 2. Troubleshooting OIDC sign-in

| Issue | What to try |
| --- | --- |
| Redirect loop or blank page | Clear cookies for your Learning Manager URL and identity provider, try another browser, or try a private window. If it persists, contact IT. Corporate proxies or identity provider session policies sometimes interfere. |
| "Access denied" or similar after identity provider login | Your identity provider accepted you, but Adobe Learning Manager might not have a matching user, or your account might lack a license or role. Contact your Adobe Learning Manager administrator. |
| Wrong language or proﬁle details | Attribute mapping is controlled by your organization. Ask your administrator whether directory attributes should drive locale or proﬁle ﬁelds. |
| Deep link opened the home page instead of the resource | Return-path and deep-link behavior can depend on how the link was shared and your session. Try the link again after a full sign-in, or ask your administrator whether the link format is supported for external users. |

## What administrators should know

If you conﬁgure Adobe Learning Manager for your organization, OIDC is set up with your identity provider's application registration: client identiﬁers, endpoints for authorization, tokens, user information, and the redirect URL that Adobe Learning Manager uses to complete sign-in. Those values come from your identity provider's documentation. The settings must match between your identity provider and Learning Manager so users see a smooth redirect and return. 

End users do not need to manage those values. They only need the correct Learning Manager URL (or custom domain) and, where applicable, invitation or self-registration links from your team.

## Summary

* OIDC lets users sign in to Adobe Learning Manager through their organization's standard identity provider, with a familiar redirect-and-return ﬂow.
* After sign-in, Adobe Learning Manager uses email and shared attributes to identify the user and apply roles (Learner, Author, Administrator, and so on).
* Self-registration, multiple SSO options, attribute updates, ﬁrst-time user provisioning, deep links, return path, custom domains, mobile, Publish to Adobe Learning Manager, and identiﬁer-based matching are supported according to your account conﬁguration.
* Other sign-in methods (such as Adobe ID or SAML) remain available when your administrators keep them enabled.
