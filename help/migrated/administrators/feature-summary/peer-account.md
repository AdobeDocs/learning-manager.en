---
description: Read this article to know how to create and manage peer accounts in Learning Manager.
jcr-language: en_us
title: Peer accounts
contentowner: shhivkum
exl-id: 251d0eeb-f5e8-4f70-a36c-dcecb4834042
---
# Peer accounts

Read this article to know how to create and manage peer accounts in Learning Manager.

Learning Manager offers the ability to share purchased seats using the Peer account feature. With peer accounts in Learning Manager, an administrator can share the purchased seats with the peer accounts that the administrator is associated with. In addition, the administrator who has initiated the sharing of seats can view the reports of the peer accounts.

## Add a peer account {#addapeeraccount}

1. From the Administrator dashboard, click **[!UICONTROL Settings]** > **[!UICONTROL Peer Accounts]**.
1. From the upper-right corner click **[!UICONTROL Add]**.

   ![](assets/peeraccount.png)

   *Add peer account*

1. In the **[!UICONTROL Account Subdomain]** field, specify the sub-domain with whom you want to establish a peer account.

   ![](assets/addpeer.png)

   *Add a sub-domain*

>[!NOTE]
>
>To find the subdomain of another account, check the account's URL. The subdomain appears before the main domain and helps identify the specific account.
>
>For example:
>
>In the URL [https://www.learningmanager.com/accountname](https://www.learningmanager.com/accountname), the subdomain is **accountname**.
>
>In the URL [https://www.accountname.learningmanager.com](https://www.accountname.learningmanager.com), the subdomain is also **accountname**.
>
>The subdomain is unique to each account and is used to access the respective Learning Manager instance.

1. Enter the email ID of the administrator who either accepts or rejects the peer account request.
1. Specify the number of seats you want to share with your peer. When you share seats with the peer account, the peer account goes into Active state with the received seats, or with the peer's own purchased seats.

   If you enter a number that is more than the available seats, the system displays a warning.

1. Select the check box if you want to view the enrollment reports and shared catalog reports of your peers.
1. Click Add to add the peer account.

   If an administrator shares seats with a peer, the peer cannot share them with anyone else. However, the peer can separately purchase some seats and share them.

## View the seats shared by peer accounts

Administrators can view the number of seats shared by the peer accounts on the administrator interface. 

To view the seats shared by peer account:

1. Log in to Adobe Learning Manager as an administrator.
2. Select **[!UICONTROL Users]** and then select **[!UICONTROL Internal]**.

![](assets/peer-account-seats.png)
_Users section showing the number of seats shared by the peer account_

## View reports associated with peer accounts {#viewreportsassociatedwithpeeraccounts}

After you establish a peer account, you can plot reports for the peer accounts as well. As an administrator, if you initiate the peer account request, you can view the reports for the peer account.

If the peer also wants to view the administrator reports, then the peer has to send a separate peer account request to the administrator.  

To know how to generate and view the shared catalogs for the peer account, see [Viewing peer reports](reports.md#main-pars_header_894271250).

## Deleting peer accounts {#deletingpeeraccounts}

If you no longer wish to share seats or purchases with an account, you can delete the peer account.

1. From the Learning Manager administrator app, click Settings > Peer Accounts.
1. Select the peer account or accounts that you want to delete.   
1. Do one of the following:

   * Click Delete from the upper-right corner of the page.
   * Click the Delete icon next to the Peer account that you want to delete.

   After a peer account is deleted, the received seats are no longer available. If the peer account had only received seats and no purchased seats, the account goes to an Inactive state.

## User report for Peer accounts {#download-peer-account}

The Administrator can view the user report of the peer account. The parent account admin can request to access the report and once the peer account admin accepts this, the parent admin will be able to view the number of registered users in the peer account and will be able to download the user report for peer account.

1. On the Peer Accounts page, click **[!UICONTROL Add]**.
1. Enable the option, **[!UICONTROL Request permission to download user reports for entire account]**.

![](assets/image034.png)

*View user report of a peer account*

To download the reports for peer accounts, click **[!UICONTROL Download]**. 

## Frequently Asked Questions {#frequentlyaskedquestions}

+++How to share seats from one account to another?

When adding a peer account, specify the number of seats that you can share with another peer account.

![](assets/share-seats.png)

*Share seats from one account to another*
+++
