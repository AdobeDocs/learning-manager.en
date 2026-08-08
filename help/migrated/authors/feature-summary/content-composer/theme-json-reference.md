---
description: A complete reference for every property in the Content Composer theme JSON schema — including palette tokens, font stacks, radius and spacing tokens, text role values, component properties, and assessment styling.
jcr-language: en_us
title: Adobe Learning Manager Content Composer theme JSON property reference
---

# Adobe Learning Manager Content Composer theme JSON property reference

A complete reference for every property in a Content Composer theme JSON file, with descriptions and example values.

Top-level fields that identify and describe the theme.

## **Metadata**

| **Property** | **Type** | **Description**                                                                                                            | **Slate value**                                                                                                  |
|--------------|----------|----------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| id           | string   | Unique theme identifier. Lowercase, hyphens only, no spaces or special characters. Used internally to reference the theme. | "slate"                                                                                                          |
| name         | string   | Display name shown in the Course Themes panel.                                                                             | "Slate"                                                                                                          |
| version      | string   | Semantic version number. Use "1.0.0" for new themes.                                                                       | "1.0.0"                                                                                                          |
| description  | string   | Short description of the theme's visual character.                                                                         | "A warm, authoritative theme with cream background, Adobe red accents, and the Roboto Slab + Roboto type system" |
| author       | string   | Name of the theme creator or team.                                                                                         | "Content Composer"                                                                                               |
| source       | string   | Theme origin. "shipped" for built-in themes. "custom" for user-created themes.                                             | "custom"                                                                                                         |
| isDefault    | boolean  | Whether this theme is automatically applied to new courses. Set to false in most cases.                                    | false                                                                                                            |

## **foundation.palette**

The seven core colour tokens that form the colour foundation of the theme. All element values reference these tokens using var(--tokenName) rather than hardcoded hex values.

| **Property**     | **Type**   | **Description**                                                                                                           | **Slate value** |
|------------------|------------|---------------------------------------------------------------------------------------------------------------------------|-----------------|
| foreground       | hex colour | Primary foreground colour for text, icons, and UI elements placed on the background.                                      | #1A1A1A        |
| background       | hex colour | Main course canvas and slide background colour.                                                                           | #FAF7F2        |
| accent           | hex colour | Brand accent colour applied to buttons, selected states, progress indicators, lesson headers, and interactive highlights. | #E8001C        |
| backgroundSubtle | hex colour | Secondary background colour for cards, panels, navigation, and component fills.                                           | #F0EBE1        |
| secondary        | hex colour | Border, divider, and inactive UI element colour.                                                                          | #D9D3C9        |
| textPrimary      | hex colour | Primary text colour for all heading and body content.                                                                     | #1A1A1A        |
| textInverse      | hex colour | Text colour for content placed on dark or accent-coloured backgrounds, such as button labels on the accent colour.        | #FFFFFF        |

## **foundation.fonts**

Two font stacks applied across all text roles in the theme. Reference in element values using var(--font-heading) or var(--font-body).

| **Property** | **Type**          | **Description**                                                                                      | **Slate value**                                                     |
|--------------|-------------------|------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------|
| heading      | font stack string | Font family for lesson titles, topic titles, and display headings. Include web-safe fallbacks.       | "Roboto Slab, Georgia, 'Times New Roman', serif"                    |
| body         | font stack string | Font family for paragraph text, captions, quiz questions, and UI labels. Include web-safe fallbacks. | "Roboto, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif" |

## **foundation.spacing**

Horizontal and vertical spacing tokens used as a baseline. Components scale from these using horizontalSpacingScale and verticalSpacingScale multipliers.

| **Path**      | **Type** | **Description**                     | **Slate value** |
|---------------|----------|-------------------------------------|-----------------|
| horizontal.xs | px value | Smallest horizontal spacing unit    | 4px             |
| horizontal.s  | px value | Small horizontal spacing unit       | 8px             |
| horizontal.m  | px value | Medium horizontal spacing unit      | 12px            |
| horizontal.l  | px value | Large horizontal spacing unit       | 16px            |
| horizontal.xl | px value | Extra-large horizontal spacing unit | 24px            |
| vertical.xs   | px value | Smallest vertical spacing unit      | 4px             |
| vertical.s    | px value | Small vertical spacing unit         | 8px             |
| vertical.m    | px value | Medium vertical spacing unit        | 16px            |
| vertical.l    | px value | Large vertical spacing unit         | 24px            |
| vertical.xl   | px value | Extra-large vertical spacing unit   | 32px            |

## **foundation.radius**

Border radius tokens controlling corner rounding for components and cards.

| **Property** | **Type** | **Description**                                         | **Slate value** |
|--------------|----------|---------------------------------------------------------|-----------------|
| none         | px value | No rounding - sharp corners. Always "0px".              | 0px             |
| s            | px value | Small radius for subtle corner rounding.                | 4px             |
| m            | px value | Medium radius for standard card and component rounding. | 8px             |
| l            | px value | Large radius for prominent rounding.                    | 16px            |
| full         | px value | Full pill or circle shape. Always "9999px".             | 9999px          |

## **foundation.logo**

| **Property** | **Type**       | **Description**                                                                              | **Slate value** |
|--------------|----------------|----------------------------------------------------------------------------------------------|-----------------|
| logo         | string or null | URL or file path for the logo image displayed in the course header. Set to null for no logo. | null            |

## **elements.text**

Typography properties for each named text role in the course. All roles share the same set of properties.

### **Text roles**

| **Role**     | **Applied to**                                                               |
|--------------|------------------------------------------------------------------------------|
| lessonTitle  | Main title on a lesson opening slide                                         |
| topicTitle   | Heading at the top of each topic slide                                       |
| blockHeading | Headings inside content components such as accordion headers and card titles |
| subheading   | Secondary headings within a topic slide                                      |
| question     | Quiz and knowledge check question text                                       |
| caption      | Captions below images and media blocks                                       |
| paragraph    | Body text in content slides                                                  |
| buttonLabel  | Text on buttons and call-to-action elements                                  |

### **Shared text properties**

The following properties apply to every text role listed above.

| **Property**       | **Type**              | **Accepted values**                                                | **Description**                                         |
|--------------------|-----------------------|--------------------------------------------------------------------|---------------------------------------------------------|
| fontFamily         | CSS var or font stack | var(--font-heading), var(--font-body), or a full font stack string | Font family for this text role.                         |
| fontSize           | px value              | Any pixel value                                                    | Font size.                                              |
| fontWeight         | string                | "bold" or "normal" only - numeric values are not supported         | Font weight.                                            |
| fontStyle          | string                | "normal" or "italic"                                               | Font style.                                             |
| color              | CSS var or hex        | Any palette token via var(--tokenName) or a direct hex value       | Text colour.                                            |
| textAlign          | string                | "left", "center", or "right"                                       | Horizontal text alignment.                              |
| letterSpacing      | string                | "normal", a px value, or an em value                               | Space between characters.                               |
| lineHeight         | string                | A percentage or unitless value                                     | Line height.                                            |
| textDecoration     | string                | "none", "underline", or "line-through"                             | Text decoration.                                        |
| textTransform      | string                | "none", "uppercase", "lowercase", or "capitalize"                  | Text case transformation.                               |
| paddingInlineStart | px value              | Any pixel value                                                    | Left padding applied to the text block.                 |
| paragraphSpacing   | px value              | Any pixel value                                                    | Space added below each paragraph within the text block. |

### **Text role values - Slate theme**

| **Role**     | **fontFamily**      | **fontSize** | **fontWeight** | **fontStyle** | **color**          | **textAlign** | **letterSpacing** | **lineHeight** | **textTransform** |
|--------------|---------------------|--------------|----------------|---------------|--------------------|---------------|-------------------|----------------|-------------------|
| lessonTitle  | var(--font-heading) | 48px         | bold           | normal        | var(--textPrimary) | center        | -0.01em           | 130%           | none              |
| topicTitle   | var(--font-heading) | 40px         | normal         | normal        | var(--textPrimary) | left          | 0                 | 135%           | none              |
| blockHeading | var(--font-heading) | 24px         | bold           | normal        | var(--textPrimary) | left          | 0                 | 140%           | none              |
| subheading   | var(--font-body)    | 20px         | bold           | normal        | var(--textPrimary) | left          | 0.01em            | 150%           | none              |
| question     | var(--font-heading) | 24px         | normal         | normal        | var(--textPrimary) | left          | 0                 | 150%           | none              |
| caption      | var(--font-body)    | 13px         | normal         | normal        | var(--textPrimary) | left          | 0.02em            | 170%           | none              |
| paragraph    | var(--font-body)    | 16px         | normal         | normal        | var(--textPrimary) | left          | 0.01em            | 190%           | none              |
| buttonLabel  | var(--font-body)    | 14px         | bold           | normal        | var(--textInverse) | center        | 0.06em            | 125%           | uppercase         |

## **elements - structural surfaces**

Properties that control the background and border of the course's fixed layout surfaces.

| **Element**  | **Property** | **Type**          | **Description**                                   | **Slate value**            |
|--------------|--------------|-------------------|---------------------------------------------------|----------------------------|
| canvas       | background   | CSS var           | Main course canvas background colour              | var(--background)          |
| header       | background   | CSS var           | Course header bar background colour               | var(--background)          |
| header       | border       | CSS border string | Bottom border of the course header bar            | 1px solid var(--secondary) |
| footer       | background   | CSS var           | Course footer bar background colour               | var(--background)          |
| footer       | border       | CSS border string | Top border of the course footer bar               | 1px solid var(--secondary) |
| lessonHeader | background   | CSS var           | Background colour of the lesson title header area | var(--accent)              |
| topic        | background   | CSS var           | Background colour of each topic slide             | var(--background)          |
| topic        | border       | CSS border string | Border around the topic slide container           | 1px solid var(--secondary) |
| navigation   | background   | CSS var           | Background colour of the lesson navigation panel  | var(--backgroundSubtle)    |
| navigation   | border       | CSS border string | Border on the lesson navigation panel             | 1px solid var(--secondary) |
| button       | background   | CSS var           | Background colour of primary action buttons       | var(--accent)              |
| pagination   | background   | CSS var           | Background colour of the pagination control       | var(--backgroundSubtle)    |

## **elements - shared component properties**

These properties appear on all content block components: paragraphBlock, videoBlock, imageGrid, accordion, carousel, flipCard, and timeline.

| **Property**           | **Type**          | **Description**                                                                                   |
|------------------------|-------------------|---------------------------------------------------------------------------------------------------|
| background             | CSS var or colour | Outer background of the component block. Typically "transparent".                                 |
| cardBackgroundColor    | CSS var or colour | Background fill of individual cards within the component.                                         |
| cardBorder             | CSS border string | Border applied to each card. Full CSS shorthand, for example "1px solid var(--secondary)".        |
| cardShadowOffset       | string            | X and Y offset of the card drop shadow, for example "0px 2px 6px".                                |
| cardShadowColor        | CSS var or colour | Colour of the card drop shadow.                                                                   |
| cardShadowOpacity      | percentage string | Opacity of the card drop shadow. Set to "0%" to remove the shadow.                                |
| horizontalSpacingScale | numeric string    | Multiplier applied to horizontal spacing tokens for this component. "1" uses the default spacing. |
| verticalSpacingScale   | numeric string    | Multiplier applied to vertical spacing tokens for this component. "1" uses the default spacing.   |
| radiusScale            | numeric string    | Multiplier applied to radius tokens for this component. "1" uses the default radius.              |
| nestedAccentColor      | CSS var or colour | Accent colour for nested elements within the component. Applies to paragraphBlock only.           |

### **Shared component values - Slate theme**

| **Component**  | **cardBackgroundColor** | **cardBorder**         | **cardShadowOpacity** |
|----------------|-----------------------------|----------------------------|---------------------------|
| paragraphBlock | var(--backgroundSubtle)     | 1px solid var(--secondary) | 8%                        |
| videoBlock     | var(--backgroundSubtle)     | 1px solid var(--secondary) | 8%                        |
| imageGrid      | var(--backgroundSubtle)     | 1px solid var(--accent)    | 8%                        |
| accordion      | var(--backgroundSubtle)     | 1px solid var(--secondary) | 8%                        |
| carousel       | var(--backgroundSubtle)     | 1px solid var(--secondary) | 8%                        |
| flipCard       | var(--backgroundSubtle)     | 1px solid var(--secondary) | 8%                        |
| timeline       | var(--backgroundSubtle)     | 1px solid var(--secondary) | 8%                        |

## **elements - component-specific properties**

Properties unique to individual component types.

| **Component**  | **Property**             | **Type** | **Description**                                                  | **Slate value**         |
|----------------|--------------------------|----------|------------------------------------------------------------------|-------------------------|
| paragraphBlock | nestedAccentColor        | CSS var  | Accent colour for nested elements within the paragraph block     | var(--accent)           |
| flipCard       | cardFrontBackgroundColor | CSS var  | Background colour of the flip card front face                    | var(--backgroundSubtle) |
| flipCard       | cardBackBackgroundColor  | CSS var  | Background colour of the flip card back face - the reveal colour | var(--accent)           |
| flipCard       | arrowColor               | CSS var  | Colour of the flip indicator arrow icon                          | var(--textInverse)      |
| tabs           | activeBg                 | CSS var  | Background colour of the currently selected tab                  | var(--accent)           |
| tabs           | inactiveBg               | CSS var  | Background colour of unselected tabs                             | var(--backgroundSubtle) |
| tabs           | containerBg              | CSS var  | Background colour of the tab bar container                       | var(--backgroundSubtle) |
| timeline       | trackColor               | CSS var  | Colour of the connecting line between timeline nodes             | var(--secondary)        |
| timeline       | progressCompletedBg      | CSS var  | Fill colour of completed timeline progress markers               | var(--accent)           |
| timeline       | progressCurrentBorder    | CSS var  | Border colour of the current timeline progress marker            | var(--accent)           |
| timeline       | progressUnreachedBg      | CSS var  | Fill colour of timeline markers not yet reached                  | var(--secondary)        |
| timeline       | progressUnreachedBorder  | CSS var  | Border colour of timeline markers not yet reached                | var(--backgroundSubtle) |

## **elements.assessment**

Properties for quiz and knowledge check components.

| **Property**               | **Type**       | **Description**                                                              | **Slate value**         |
|----------------------------|----------------|------------------------------------------------------------------------------|-------------------------|
| background                 | CSS var        | Outer background of the assessment block                                     | transparent             |
| optionTextColor            | CSS var        | Text colour of answer option labels                                          | var(--textPrimary)      |
| optionIndicatorColor       | CSS var        | Colour of the radio button or checkbox indicator                             | var(--accent)           |
| optionSelectedColor        | CSS var        | Colour applied to the selected option indicator                              | var(--accent)           |
| optionCheckmarkColor       | CSS var        | Colour of the checkmark icon shown on a selected option                      | var(--textInverse)      |
| optionBackgroundColor      | CSS var        | Background colour of each answer option                                      | var(--background)       |
| optionHoverBackgroundColor | CSS var        | Background colour of an answer option on hover                               | var(--backgroundSubtle) |
| buttonBackgroundColor      | CSS var        | Background colour of the Submit or Check answer button                       | var(--accent)           |
| buttonTextColor            | CSS var        | Text colour of the Submit or Check answer button label                       | var(--textInverse)      |
| buttonHoverBackgroundColor | CSS var        | Background colour of the button on hover                                     | var(--accent)           |
| feedbackCorrectColor       | hex colour     | Background colour of the correct answer feedback panel                       | #D7F7E1               |
| feedbackIncorrectColor     | hex colour     | Background colour of the incorrect answer feedback panel                     | #FFEBE8               |
| feedbackTextColor          | hex colour     | Text colour inside the feedback panel                                        | #111111               |
| optionBorderCorrectColor   | hex colour     | Border colour on the correct answer option after the answer is revealed      | #079355               |
| optionBorderIncorrectColor | hex colour     | Border colour on an incorrectly selected option after the answer is revealed | #D73220               |
| horizontalSpacingScale     | numeric string | Multiplier for horizontal spacing within the assessment component            | "1"                     |
| verticalSpacingScale       | numeric string | Multiplier for vertical spacing within the assessment component              | "1"                     |
| radiusScale                | numeric string | Multiplier for border radius within the assessment component                 | "1"                     |

## **Palette token var() reference**

Use these var() expressions in element values to reference palette tokens. Updating a palette token automatically updates every element that uses it.

| **Expression**          | **References**                      |
|-------------------------|-------------------------------------|
| var(--foreground)       | foundation.palette.foreground       |
| var(--background)       | foundation.palette.background       |
| var(--accent)           | foundation.palette.accent           |
| var(--backgroundSubtle) | foundation.palette.backgroundSubtle |
| var(--secondary)        | foundation.palette.secondary        |
| var(--textPrimary)      | foundation.palette.textPrimary      |
| var(--textInverse)      | foundation.palette.textInverse      |
| var(--font-heading)     | foundation.fonts.heading            |
| var(--font-body)        | foundation.fonts.body               |

## Example of a theme json

```
{
  "id": "slate",
  "name": "Slate",
  "version": "1.0.0",
  "description": "A warm, authoritative theme with cream background, Adobe red accents, and the Roboto Slab + Roboto type system",
  "author": "Content Composer",
  "source": "custom",
  "isDefault": false,
  "foundation": {
    "palette": {
      "foreground": "#1A1A1A",
      "background": "#FAF7F2",
      "accent": "#E8001C",
      "backgroundSubtle": "#F0EBE1",
      "secondary": "#D9D3C9",
      "textPrimary": "#1A1A1A",
      "textInverse": "#FFFFFF"
    },
    "fonts": {
      "heading": "Roboto Slab, Georgia, 'Times New Roman', serif",
      "body": "Roboto, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif"
    },
    "spacing": {
      "horizontal": {
        "xs": "4px",
        "s": "8px",
        "m": "12px",
        "l": "16px",
        "xl": "24px"
      },
      "vertical": {
        "xs": "4px",
        "s": "8px",
        "m": "16px",
        "l": "24px",
        "xl": "32px"
      }
    },
    "radius": {
      "none": "0px",
      "s": "4px",
      "m": "8px",
      "l": "16px",
      "full": "9999px"
    },
    "logo": null
  },
  "elements": {
    "text": {
      "lessonTitle": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "48px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "center",
        "letterSpacing": "-0.01em",
        "lineHeight": "130%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "topicTitle": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "40px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "135%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "blockHeading": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "24px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "140%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "subheading": {
        "fontFamily": "var(--font-body)",
        "fontSize": "20px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.01em",
        "lineHeight": "150%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "question": {
        "fontFamily": "var(--font-heading)",
        "fontSize": "24px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0",
        "lineHeight": "150%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "caption": {
        "fontFamily": "var(--font-body)",
        "fontSize": "13px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.02em",
        "lineHeight": "170%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "paragraph": {
        "fontFamily": "var(--font-body)",
        "fontSize": "16px",
        "fontWeight": "normal",
        "fontStyle": "normal",
        "color": "var(--textPrimary)",
        "textAlign": "left",
        "letterSpacing": "0.01em",
        "lineHeight": "190%",
        "textDecoration": "none",
        "textTransform": "none",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      },
      "buttonLabel": {
        "fontFamily": "var(--font-body)",
        "fontSize": "14px",
        "fontWeight": "bold",
        "fontStyle": "normal",
        "color": "var(--textInverse)",
        "textAlign": "center",
        "letterSpacing": "0.06em",
        "lineHeight": "125%",
        "textDecoration": "none",
        "textTransform": "uppercase",
        "paddingInlineStart": "0px",
        "paragraphSpacing": "0px"
      }
    },
    "canvas": {
      "background": "var(--background)"
    },
    "header": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "footer": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "lessonHeader": {
      "background": "var(--accent)"
    },
    "topic": {
      "background": "var(--background)",
      "border": "1px solid var(--secondary)"
    },
    "navigation": {
      "background": "var(--backgroundSubtle)",
      "border": "1px solid var(--secondary)"
    },
    "button": {
      "background": "var(--accent)"
    },
    "pagination": {
      "background": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "paragraphBlock": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "nestedAccentColor": "var(--accent)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "imageBlock": {
      "background": "transparent",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "videoBlock": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "imageGrid": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--accent)",
      "cardShadowOffset": "0px 2px 8px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "accordion": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "carousel": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "flipCard": {
      "background": "transparent",
      "cardFrontBackgroundColor": "var(--backgroundSubtle)",
      "cardBackBackgroundColor": "var(--accent)",
      "arrowColor": "var(--textInverse)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "tabs": {
      "background": "transparent",
      "activeBg": "var(--accent)",
      "inactiveBg": "var(--backgroundSubtle)",
      "containerBg": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "timeline": {
      "background": "transparent",
      "cardBackgroundColor": "var(--backgroundSubtle)",
      "cardBorder": "1px solid var(--secondary)",
      "cardShadowOffset": "0px 2px 6px",
      "cardShadowColor": "var(--foreground)",
      "cardShadowOpacity": "8%",
      "trackColor": "var(--secondary)",
      "progressCompletedBg": "var(--accent)",
      "progressCurrentBorder": "var(--accent)",
      "progressUnreachedBg": "var(--secondary)",
      "progressUnreachedBorder": "var(--backgroundSubtle)",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    },
    "assessment": {
      "background": "transparent",
      "optionTextColor": "var(--textPrimary)",
      "optionIndicatorColor": "var(--accent)",
      "optionSelectedColor": "var(--accent)",
      "optionCheckmarkColor": "var(--textInverse)",
      "optionBackgroundColor": "var(--background)",
      "optionHoverBackgroundColor": "var(--backgroundSubtle)",
      "buttonBackgroundColor": "var(--accent)",
      "buttonTextColor": "var(--textInverse)",
      "buttonHoverBackgroundColor": "var(--accent)",
      "feedbackCorrectColor": "#D7F7E1",
      "feedbackIncorrectColor": "#FFEBE8",
      "feedbackTextColor": "#111111",
      "optionBorderCorrectColor": "#079355",
      "optionBorderIncorrectColor": "#D73220",
      "horizontalSpacingScale": "1",
      "verticalSpacingScale": "1",
      "radiusScale": "1"
    }
  }
}
```
