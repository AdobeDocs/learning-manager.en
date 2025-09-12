---
title: Experience Builder Recommendations in Adobe Learning Manager
description: Experience Builder Recommendations provide personalized course and content suggestions to learners using AI-driven algorithms. 
jcr-language: en-us
---

# Experience Builder recommendations in Adobe Learning Manager

Experience Builder is a powerful tool designed to help users create dynamic and engaging web pages with ease. To ensure optimal performance, usability, and security, it is essential to follow certain guidelines and recommendations when configuring pages, using widgets, and customizing layouts. This document provides a detailed overview of important notes and points that users should consider while working with Experience Builder. 

The information outlined here covers key aspects such as page and widget configurations, customization options, handling custom code, and security considerations. By adhering to these recommendations, users can maximize the efficiency of their Experience Builder projects, avoid common pitfalls, and adapt seamlessly to updates and changes. 

## Page and widget configuration 

### Maximum pages 

You can create up to 1000 pages in Experience Builder. This is the upper limit, but it is recommended to plan pages strategically to avoid unnecessary complexity. 

### Widgets per page 

* **Hard limit**: A maximum of 25 widgets can be added to a single page. 
* **Recommended limit**: For better performance, it is advised to use no more than 10 widgets per page. 
* **API-based widgets**: Widgets dependent on ALM APIs (e.g., Courses and paths, Category, My learning, Social learning, Calendar, Compliance, Leaderboard) should be limited to 10 per page. 
* **Independent widgets**: Widgets like HTML and Content box, which do not rely on ALM APIs, can be used up to the hard limit of 25 widgets. 

### Single use widgets 

Certain widgets, such as Calendar, Social learning, Compliance and Leaderboard, should only be used once per page. Using them multiple times can lead to performance issues, especially for widgets like the calendar, which require significant resources to load sessions. 

### Widget sizing guidelines 

Widgets such as Calendar, Leaderboard, Social, and Compliance should be placed in layouts with a minimum width of one-third of the page. Single card widgets are best suited for this width to ensure optimal display. Widgets like the Calendar and Compliances (expanded view) are designed for half-width layouts to offer a better user experience. For other layout sizes, widgets will adjust responsively to fit the available space and maintain usability. 

Using widgets within these recommended size guidelines enhances overall user interaction. 

## Customization guidelines 

### Default pixel distances 

**Vertical distance**: The default vertical distance between widgets is 80 pixels. 
**Horizontal distance**: The default horizontal distance between widgets is 20 pixels. 

### Custom CSS 

Users can override default distances and other visual properties using custom CSS. 

Steps for customization: 

* Inspect the page elements to identify CSS classes. 
* Apply changes at the global level, widget level, or page level. 

For example, to reduce the vertical distance between widgets, modify the CSS property for the relevant class. 

## Menu positioning 

Menus can be positioned at the top or left of the page. Further adjustments can be made using custom CSS. 

## Feature-specific recommendations 

### Social learning and Gamification widgets 

* If these features are disabled, administrators must manually remove the corresponding widgets from pages. 
* Pages should be redesigned to ensure they remain functional and visually intact after disabling these features. 

## Handling custom code 

### Impact of updates 

* Existing custom code (HTML, CSS, JS) injected into the backend may not work as expected after updates to Experience Builder. 
* Users must rewrite their code to align with new UI changes, such as updated class names. 

### Front-end support 

* Add custom code directly in the admin portal using HTML widgets or account-level CSS/JS blocks. 

### Disclaimer 

* Custom code may not function as expected with future releases, requiring adjustments. Be prepared to update their code after each release. 

## General recommendations 

### Performance considerations 

* Avoid exceeding the recommended widget limits to prevent performance degradation. 
* Using resource-intensive widgets (for example, a calendar) multiple times on a page can significantly impact page load times. 

### Security considerations 

* **HTML widgets**: You must ensure the code handles security issues like cross-site scripting (XSS) attacks, as these are outside the scope of Experience Builder's control. 

### Breaking changes 

Updates to Experience Builder may introduce breaking changes for customizations. You must: 

* Adjust the code to match new UI elements. 
* Test the customizations after each update. 

## Additional notes 

### Custom CSS implementation 

* You can inspect page elements, copy CSS classes, and apply their desired properties to customize layouts globally, at the widget level, or at the page level. 

### Widget IDs and Page IDs 

Each widget and page have unique IDs that can be used for targeted CSS changes. This allows for customization at different levels: 

* Global level: Apply CSS changes across all pages. 
* Widget level: Apply CSS changes to specific widgets. 
* Page level: Apply CSS changes to all widgets within a specific page. 

 

 

 

 

 