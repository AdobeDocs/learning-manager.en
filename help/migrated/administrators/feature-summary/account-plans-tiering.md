---
description: Learn how Prime and Ultimate plans differ in Adobe Learning Manager and how your account is affected when it renews on a new contract
jcr-language: en_us
title: Account plans tiering
exl-id: 8897372e-d9b5-4519-a59a-a9b9a95b86aa
---

# Account plans and tiering

Adobe Learning Manager is available on two account plans — **Prime** and **Ultimate** — each with access to a different set of capabilities. Your account's current plan is shown on the **Billing** page.

## Prime and Ultimate plans

Every new Adobe Learning Manager account is provisioned on one of two plans:

* **Prime** — the standard plan, with access to the core Adobe Learning Manager feature set
* **Ultimate** — includes everything in Prime, plus additional capabilities described below

To check which plan your account is on, go to **Billing** in the admin navigation.

>[!NOTE]
>
>Some accounts have a different connector allotment based on the specific type of contract they hold, independent of whether they are on Prime or Ultimate. This has always been part of how connector access works and is not a change introduced by the plan structure. Contact your Adobe account team if you have questions about your specific connector allotment.

## What's different between Prime and Ultimate

| Capability | Prime | Ultimate |
|---|---|---|
| Headless APIs | Not available | Available |
| Connector count | Limited to 6 | Higher limit |
| Jobs API rate limit | Lower | Higher |
| Seat sharing between accounts | Not available | Available |

For details on seat sharing eligibility and how it's affected by your plan, see [seat sharing in Adobe Learning Manager](#).

## How existing accounts are affected

If your account was created before this plan structure was introduced, you retain full access to all the capabilities you previously had — including everything now associated with the Ultimate plan — until your next renewal.

At renewal, your account moves to either the Prime or Ultimate plan, based on the plan associated with your new contract:

* If your renewed contract is on the **Prime** plan, your account loses access to the capabilities not included in Prime — such as Headless APIs, the higher connector count, and the higher Jobs API rate limit.
* If your renewed contract is on the **Ultimate** plan, your account retains full access to these capabilities with no interruption.

The following table shows how this plays out across different scenarios.

| Scenario | Resulting plan | Ultimate-only capabilities |
|---|---|---|
| Existing account renews on a Prime contract | Prime | Not available |
| Existing account renews on an Ultimate contract | Ultimate | Available |
| New account provisioned on a Prime contract | Prime | Not available |
| New account provisioned on an Ultimate contract | Ultimate | Available |
| Existing Prime account renews again on a Prime contract | Prime | Not available |

>[!NOTE]
>
>"Existing account" refers to any account created before this plan structure was introduced. Until your first renewal after that point, your account continues to behave as if it were on the Ultimate plan, regardless of which plan you will eventually move to.

## Request access to a specific feature

If your account is on the Prime plan and you need access to a specific capability that is only included in Ultimate — without moving your entire account to a different plan — contact your Adobe account team or Adobe Support. In some cases, Adobe can enable an individual capability for your account outside of a full plan change.

>[!NOTE]
>
>This is not a self-service option available from your account's Settings. It requires a request to Adobe, and availability depends on the specific capability requested.

## Frequently asked questions

**When does a plan change take effect?**
Plan changes take effect at your account's next renewal. If your contract changes from Ultimate to Prime, or from Prime to Ultimate, the new plan's capabilities apply starting from that renewal — not immediately when the contract is signed.

**Will moving to the Prime plan affect an existing seat-sharing relationship?**
Yes. Seat sharing between accounts is available on the Ultimate plan only. If your account moves to Prime at renewal, any existing seat-sharing relationships end at that point. See [seat sharing in Adobe Learning Manager](#) for details.

**Can I move from Prime back to Ultimate later?**
Yes. Your plan is tied to your contract, so moving from Prime to Ultimate (or the reverse) happens whenever your contract is updated to reflect the new plan, taking effect at the next renewal.

**Does the connector limit on Prime apply immediately to an existing account?**
No. If your account was created before this plan structure was introduced, your existing connector access continues unchanged until your next renewal. The Prime plan's connector limit only applies once your account has renewed onto a Prime contract.

**Who do I contact to confirm which plan my account will move to at renewal?**
Contact your Adobe account team. They can confirm which plan is associated with your upcoming renewal and help you request a specific plan if needed.
