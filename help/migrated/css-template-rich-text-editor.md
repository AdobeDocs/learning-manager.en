---
jcr-language: en_us
title: CSS template for Rich Text Editor
contentowner: saghosh
preview: {Boolean}true
---


# CSS template for Rich Text Editor {#css-template-for-rich-text-editor}

# **Why is CSS required?**

Rich text is composed of HTML markup. Rendering the markup as-is would result in default styling applied by the browser. This often doesn't go well with the style guidelines of the company. A CSS is required to meet the guidelines.

# Default style

The attached CSS stylesheet contains the styling that is applied by Learning Manager. The styling is tweaked considering majority of the usecases. Download the attached CSS file and import it to your webapp according to your conventions and build system. The CSS classes defined are namespaced under&nbsp;ql-editor&nbsp;class and they don't interfere with your existing styles.

# **Customize styles**

The default styling may not meet everyone's needs. The customisations can be done by overiding CSS supplied. All the styling is wrapped under ql-editor as descendant selectors. The following classes are used:

* **Indenting**: li.ql-indent-$number. $number varies from 1-9
* **size**: ql-size-small, ql-size-large, ql-size-huge
* **alignment**: ql-align-center, ql-align-justify, ql-align-right
* **color**: ql-color-$color. $color = white, red, orange, yellow, green, blue, purple
* **background**: ql-bg-$color. $color = black, red, orange, yellow, green, blue, purple
* **html tags**: p, ol, ul, pre, blockquote, h1, h2, h3, h4, h5, h6

[CSS file to be used for customization.](assets/ql-headless.css)  