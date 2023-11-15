---
jcr-language: en_us
title: Support for custom domain
description: Custom Domains are not supported in an Azure instance of Learning Manager.
contentowner: saghosh
---


# Support for custom domain

Custom Domains are not supported in an Azure instance of Learning Manager.

## Overview {#overview}

Custom Domain support allows the customers to gain complete control over the domain name that they can use for their account in Learning Manager. A customer needs to purchase the custom domain separately and work with Adobe team to set it up as their login URL for their learning platform. 

This allows the customer to white label the login and access experience, such that the users do not see any presence of Adobe or Adobe Learning Manager. 

For instance, you'd like to customize your domain such that your users get the same experience as if they are on the Adobe domain. If ABC Inc wants to train their customers, it would like them to land on a domain called `abc.com/mylearning`, instead of `captivateprime.adobe.com/abc-inc/mylearning`. 

As a pre-requisite, you must register the domain and then Adobe will guide you through customizing the url.

Custom domain feature is available at an additional cost. Please contact your Customer Success Manager to know more details. 

* For learner role, the domain will start with `https://cdn.<customer_custom_domain>/` For example, `https://cdn.elearningstage1.cpdomaintest.in/`  
* For all other roles, the domain will start with `https://<customer_custom_domain>/`. For example, `https://elearningstage1.cpdomaintest.in/`

`<customer_custom_domain>` is the customizable part.

## How to setup a custom domain on an account {#howtosetupacustomdomainonanaccount}

As a pre-requisite, a customer must own a domain name and purchase the domain from a provider.

As an example, let us consider that a customer owns a fictitious domain, **acme.com**. The customer wishes Learning Manager content to be served from **learning.acme.com**.

Follow the steps below to set up a custom domain.

1. The customer has to **add three CNAME** records in the domain:

   * **learning.acme.com:** ALB public endpoint of Learning Manager shared by Adobe  
   * **lrs.learning.acme.com:** ALB public endpoint pointed by learning.acme.com  
   * **cdn.learning.acme.com:** CDN endpoint shared by Adobe

1. The customer must provide SSL certificates for these domains:

   * learning.acme.com  
   * lrs.learning.acme.com  
   * cdn.learning.acme.com

1. Adobe will upload these SSL certificates to AWS ALB for serving requests to the domains.
1. Adobe will add learning.acme.com in their SAN cert.
1. Adobe will generate the SP metadata for the customer as the metadata will contain the custom domian URLs.

   * If the customer wishes to have social login, then Adobe must include the redirect url patterns of the social sites in the list of allowed urls.
   * If the customer has enabled SSO, then the customer must work with their IDP to include their domains in the redirect urls. The customer must share the IDP metadata XML with Adobe. Adobe then must update the SSO settings of the customer's account.

1. Adobe will then modify the S3 CORS rules to include the customer's domain.
