---
jcr-language: en_us
title: Captivate Prime compliance to GDPR
description: Adobe Learning Manager compliance to GDPR
contentowner: dvenkate
---


# Captivate Prime compliance to GDPR

>[!IMPORTANT]
>
>The contents of this document are not legal advice and are not meant to substitute for legal advice. Please consult your company's legal department for advice concerning GDPR.

+++What is GDPR?

GDPR is a new regulation by the European Union that comes into effect on 25 May 2018. It provides strong control for data privacy and enables end users to take charge of their own personal data.

+++

+++How or Why does it apply to you as an Adobe Learning Manager customer?

While GDPR is a EU regulation, it is applicable to business entities worldwide, that collects personal information for any user who may be EU resident.  As a Captivate Prime customer, evaluate if GDPR is applicable to your organization.

+++

+++What role does Adobe play in this as a vendor of Captivate Prime?

As per GDPR, If your business provides a product or service to EU residents, and determines how and why to collect, track, and monitor their data, you're considered a [data controller](https://gdpr-info.eu/art-24-gdpr/). As an Adobe Learning Manager customer, if you perform one of these activities you are considered as a data controller.

Businesses that process data on behalf of controllers are considered  [data processors](https://gdpr-info.eu/art-28-gdpr/). As a vendor of cloud-hosted LMS Adobe Learning Manager, Adobe plays the role of a data processor. Here are some more details about  [GDPR and Your Business](https://www.adobe.com/privacy/general-data-protection-regulation.html).

+++

+++How does Captivate Prime enable you to be compliant with GDPR?

Captivate Prime has built in the following tools and processes that will help you in GDPR compliance. To support any processes that go beyond the product to be fully compliant with the regulation, you may still need to evaluate with your compliance team.

**Right to Forget- Reaching the Data Controller:** GDPR requires data controllers to support a Right To Forget functionality for their users. This means that any user has the right to request the data controller to permanently delete any Personal data stored for that user. If you get such a request and further evaluate that it is a valid request, this functionality is now provided in Captivate Prime through its [Purge Users](../administrators/feature-summary/purge-users.md) functionality. This feature allows the admin to initiate a permanent delete of any data related to a specific individual, upon the individuals request at which point Captivate Prime will instantly hard delete the data from its database and a purge of the backup logs (meant for recovery of the system) will also follow automatically.

**Right to Forget- Reaching the Data Processor:** The end user can also reach out to Adobe independently for deleting their PII. In this case, Captivate Prime will automatically detect which accounts own the PII for that user and Adobe will notify the admin immediately of such a request. Admin can then evaluate the validity of the request and take a call on the request through the Purge Users feature.

**Right to Access:** GDPR allows the end user the right to request data that a controller may have stored for that end user. To support this request, Captivate Prime allows the admin to self-generate Learner Transcript which can be shared with the user.

**Privacy by Design, Data Encryption:** We process data both in transit and at rest using best-in-class encryption standards to ensure data security. Encryption algorithms used are SHA-256. This ensures that any data that you store is adequately protected so that it does not fall into the wrong hands.

+++

