---
description: Learn more about Experience Builder, a no-code/low-code tool in Adobe Learning Manager that enables administrators to design and publish branded, user-friendly pages without technical expertise.
jcr-language: en_us
title: Experience Builder in Adobe Learning Manager
---

# Overview

Experience Builder is a no-code/low-code tool in Adobe Learning Manager that helps you create customized learning portals. It allows you to design branded, user-friendly learning portals without needing technical skills or extensive coding knowledge.

With Experience Builder, administrators can easily create pages, menus, and widgets to deliver personalized learning experiences tailored to their audience

Many organizations struggle to customize their learning portals without technical help or expensive system integrators. They want portals that match their brand, deliver targeted content, and adapt to different learner groups while still being quick and easy to build.

Experience Builder is a no-code/low-code tool in Adobe Learning Manager that helps you create customized learning portals. It allows you to design branded, user-friendly learning portals without needing technical skills or extensive coding knowledge.
With Experience Builder, you can create new pages, menus, and widgets to deliver personalized learning experiences for your audience quickly and easily. With Experience Builder, you can quickly create new pages, menus, and widgets to deliver personalized learning experiences for your audience.

## The problem that Experience Builder solves

Experience Builder addresses the common challenge organizations face in customizing their learning portals without significant technical help or expensive system integrators. It bridges the gap between two primary options:

* The standard out-of-the-box experience, which offers limited customization and can make every learning portal look similar.
* A headless implementation, which allows for completely custom, gamified portals but comes with significant challenges, including a long time-to-market (typically 3-6 months), dependency on a development team, and high costs.

Experience Builder provides a middle ground, allowing for the creation of on-brand portals and unique learning journeys without the high cost and development overhead of a headless approach.

## Key benefits of using Experience Builder

The functionality of using pages, widgets, or menus delivers several key benefits:

* **Easy customization**: You can design portals that precisely match your brand with custom headers, footers, logos, and layouts. The ability to inject custom HTML, CSS, and JavaScript provides advanced control for a fully branded experience.
* **Personalized learning**: A key advantage is the ability to provide different experiences to different learners. You can configure pages and menus for specific user groups (for example, sales teams, designers, or engineers), ensuring they only see content relevant to them. This is ideal for creating targeted micro-learning campaigns for specific teams or time periods.
* **No code/low code interface**: Administrators can create learning experiences through a guided, visual interface rather than by writing code. This approach allows administrators to build and manage sophisticated, branded portals without needing technical skills or extensive coding knowledge.
* **Global and mobile-ready**: Experience Builder supports the creation of multilingual pages to cater to diverse global audiences and is designed to be mobile-friendly, ensuring a smooth experience for learners on desktops, phones, and tablets.

## Common use cases

Experience Builder can be used for various learning scenarios involving internal employees and external users.

* **Role-based training portals**: Organizations with specific departmental training needs, such as a financial firm with separate Sales and Customer Success teams, can create dedicated learning pages for each group to ensure the content is highly relevant.
* **Event-specific learning pages**: You can create temporary, specialized pages for corporate events like a Tech Summit or a Sales Kick Off. These pages can feature session information, speaker lists, and an Events Calendar Widget, and can be targeted only to the relevant team for a specific duration before reverting to the standard portal experience.
* **Customer academies**: Experience Builder allows agencies to build customer-facing academies that reflect their brand identity, achieving a custom experience without the time and cost associated with a headless build.

## Authenticated external-facing portal workflows

Customer-facing academies built with Experience Builder are managed entirely within Adobe Learning Manager. These portals use Adobe Learning Manager's built-in authentication, permissions, and security framework.

Every external learner must log in to Adobe Learning Manager and be a member of at least one User Group. Currently, Experience Builder does not support unauthenticated or public-facing portals. All personalized experiences require learners to log in to Adobe Learning Manager.

Administrators can use the Experience Builder **[!UICONTROL Menu]** option to assign custom-built pages as landing pages for specific User Groups. When learners from that group log in, Adobe Learning Manager automatically directs them to their assigned landing page, creating a personalized and branded experience for that audience, such as customer training, partner enablement, or onboarding.

### Requirements and limitations

* Authentication Required: Personalized content, custom pages, and menus are available only to authenticated users in Adobe Learning Manager.
* User Group assignment: Learners must be added to the correct User Groups to access their designated landing pages and menus.
* Group-Based Landing Pages: The landing page setting applies to all members of a User Group, ensuring consistent experiences for similar audiences.
* Customization Scope: Experience Builder supports extensive UI and layout customization using widgets, HTML, and iFrames. However, advanced integrations such as e-commerce, federated SSO, or external data connections may require a hybrid or headless implementation.

### External-facing portal setup workflow

* Define User Groups: Create or identify groups in ALM that represent your external audiences (For example, customers, partners, or distributors). View [User groups in Adobe Learning Manager](/help/migrated/administrators/feature-summary/user-group.md) for more information on User Groups. 
* Assign Learners to groups: Add each external learner to the appropriate User Group so they are directed to the correct portal experience after login.
* Design Portal Pages: Use Experience Builder to create branded pages with Adobe Learning Manager widgets, HTML, and iFrame components. View [Create a custom page in Experience Builder](/help/migrated/administrators/feature-summary/experience-builder/create-a-page.md) for more information.
* Configure Menus and Landing Pages: In the Menu Creator, assign each user group a unique menu and designate its custom portal page as the landing page. View [Create a menu](/help/migrated/administrators/feature-summary/experience-builder/create-a-menu.md) for more information. 
* Test and Publish: Verify navigation, content visibility, and page routing for each user group before publishing the portal.
