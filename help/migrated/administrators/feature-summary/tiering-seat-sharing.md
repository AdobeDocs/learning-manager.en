---
description: How billing plans determine whether accounts can share licensed seats, and what happens to sharing relationships when a plan changes
jcr-language: en_us
title: Tiering - Seat sharing
exl-id: 42b4cba4-1e44-40d8-aa57-ce2a855be258
---

# Seat sharing and account plans in Adobe Learning Manager

Seat sharing lets one account share a portion of its licensed seats with another account, so learners in the receiving account can access Adobe Learning Manager using seats from the sharing account. Which accounts can share seats, and with whom, depends on the billing plan each account is on.

## Which plans support seat sharing

Seat sharing is available to accounts on the **Ultimate** plan. Accounts on the **Prime** plan cannot share seats with another account, and cannot receive shared seats from another account.

Accounts billed by credit card are on the Prime plan by default and are therefore not eligible to participate in seat sharing.

Trial accounts are the one exception: a Trial account can receive shared seats from an Ultimate account. While an active sharing relationship is in place, the Trial account has Ultimate-level feature access.

## Peer accounts setting visibility

Peer account setting will be visible in the Admin app of the account that shares this feature.

>[!NOTE]
>
>If your account shares seats with additional accounts beyond the one you receive seats from, for example, if your account passes shared access along to a third account, every account in that chain must be on the Ultimate plan for sharing to continue working end to end.

## Account combinations that support seat sharing

The following table shows whether seat sharing is possible between different combinations of account plans.

| Sharing account (parent) | Receiving account (child) | Sharing supported? |
|---|---|---|
| Prime (any) | Any | No, seat sharing is restricted to Ultimate plan accounts |
| Ultimate | Ultimate | Yes |
| Ultimate | Prime | No, plan mismatch |
| Ultimate | A credit-card-billed account | No, plan mismatch, since credit-card-billed accounts are on the Prime plan |
| Ultimate | Trial | Yes, the Trial account gets Ultimate-level access while the relationship is active |

>[!NOTE]
>
>Some additional restrictions on seat sharing between specific account configurations may apply independently of plan type, for example, based on how an account's subscription was originally set up. If you're unable to establish a sharing relationship between two Ultimate accounts, contact Adobe support to confirm your account configuration.

## What happens to seat sharing when a plan changes

Seat sharing eligibility is evaluated at renewal. If an account's plan changes in a way that affects an existing sharing relationship, the following happens:

* If a sharing (parent) account's plan changes from Ultimate to Prime at renewal, its existing seat-sharing relationships end.
* If the receiving account has its own independent subscription, that subscription is unaffected; only the sharing relationship itself ends.
* If the receiving account was a Trial account relying on the parent account's Ultimate access, it reverts to Prime-level access once the sharing relationship ends.

These changes take effect at the account's next renewal for existing ALM accounts, not immediately during an active contract term. However, these do not apply for new accounts that are created after tiering feature has gone live.

>[!NOTE]
>
>Accounts billed by credit card that currently have Ultimate-level access will move to the Prime plan starting from their next renewal. If such an account has any active seat-sharing relationships at that point, those relationships end as part of the same transition.
