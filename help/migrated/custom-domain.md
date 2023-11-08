---
jcr-language: en_us
title: Support for custom domain
contentowner: saghosh
---


# Support for custom domain {#support-for-custom-domain}

Custom Domains are not supported in an Azure instance of Captivate Prime.

## Overview {#overview}

Custom Domain support allows the customers to gain complete control over the domain name that they can use for their account in Captivate Prime. A customer needs to purchase the custom domain separately and work with Adobe team to set it up as their login URL for their learning platform.&nbsp;

This allows the customer to white label the login and access experience, such that the users do not see any presence of Adobe or Adobe Captivate Prime.&nbsp;

For&nbsp;instance,&nbsp;you’d like to customize your domain such that your users get the same&nbsp;experience as if they are on the Adobe domain. If ABC Inc wants to train their customers, it would like them to land&nbsp;on a domain called&nbsp;**abc.com/mylearning**, instead of&nbsp;**captivateprime.adobe.com/abc-inc/mylearning**.&nbsp;

As a pre-requisite, you must register the domain and then Adobe will guide you through customizing the&nbsp;url.

Custom&nbsp;domain&nbsp;feature&nbsp;is available at an additional cost. Please contact&nbsp;your Customer Success Manager&nbsp;to know more details.&nbsp;

* For learner role, the domain will start with&nbsp;https://cdn.<customer_custom_domain>/&nbsp;For example,&nbsp;https://cdn.elearningstage1.cpdomaintest.in/  
* For all other roles, the domain will start with https://<customer_custom_domain>/. For example, [https://elearningstage1.cpdomaintest.in/](https://elearningstage1.cpdomaintest.in/)

<customer_custom_domain> is the customizable part.

## How to setup a custom domain on an account {#howtosetupacustomdomainonanaccount}

As a pre-requisite,&nbsp;a customer must own a domain name and purchase the domain from a provider.

As an example, let us consider that a customer owns a fictitious domain, **acme.com**. The customer wishes Captivate Prime content to be served from **learning.acme.com**.

Follow the steps below to set up a custom domain.

1. The customer has to **add three CNAME** records in the domain:

   * **learning.acme.com:**&nbsp;ALB public endpoint of Captivate Prime shared by Adobe  
   
   * **lrs.learning.acme.com: **ALB public endpoint pointed by learning.acme.com  
   
   * **cdn.learning.acme.com: **CDN endpoint shared by Adobe

1. The customer must provide SSL certificates for these domains:

   * learning.acme.com  
   * lrs.learning.acme.com  
   * cdn.learning.acme.com

1. Adobe will upload these SSL certificates to AWS ALB for serving requests to the domains.
1. Adobe will add learning.acme.com in their SAN cert.
1. Adobe will generate the SP metadata for the customer as the metadata will contain the custom domian URLs.
1.

   * If the customer wishes to have social login, then Adobe must include the redirect url patterns of the social sites in the list of allowed urls.
   * If the customer has enabled SSO, then the customer must work with their IDP to include their domains in the redirect urls. The customer must share the IDP metadata XML with Adobe. Adobe then must update the SSO settings of the customer's account.

1. Adobe will then modify the S3 CORS rules to include the customer's domain.

