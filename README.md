# Introduction to CSS

## What is CSS?

**CSS** stands for **Cascading Style Sheets**. It is a **stylesheet language** used to describe how HTML elements should be **styled and presented** on a web page.

While **HTML** is used to create the **structure** of a web page (like headings, paragraphs, buttons), **CSS** is used to define the **look and feel** — such as colors, fonts, layout, spacing, animations, and responsiveness.

---

## Why Use CSS?

Here’s why CSS is essential in web development:

- **Separation of Content and Style**  
  Keeps HTML clean by separating structure from design.

- **Better Visual Design**  
  Enables beautiful, consistent, and customizable styling of web pages.

- **Reusability**  
  One CSS file can be applied to multiple pages.

- **Improved Maintainability**
  Changes to styling can be made in one place rather than editing every HTML element.

- **Responsive Design**  
  CSS enables you to build layouts that adapt to different screen sizes and devices.

---

## a. introduction to CSS

## Types of CSS

There are **three main types of CSS**:

### 1. Inline CSS

CSS is written directly in the `style` attribute of an HTML element.

```html
<p style="color: red;">This is red text.</p>
```

- Quick and easy for small changes.
- Not ideal for large projects — hard to maintain.

### 2. Internal CSS

CSS is written inside a `<style>` tag within the `<head>` of an `HTML` document.

```html
<head>
  <style>
    h1 {
      color: blue;
    }
  </style>
</head>
```

- Ideal for small projects.
- Easy to maintain.
- Can be used with external CSS.
- Styles are not reusable across multiple pages.

#### 3. External CSS

CSS is written inside a `<style>` tag within the `<head>` of an `HTML` document.

```html
<link rel="stylesheet" href="style.css" />
```

- Ideal for large projects.
- Promotes clean, modular code.
- Reusable and easy to maintain.

---

---

# b. CSS Selectors

## CSS Selectors & Styling Guide

## What is a Selector?

A **CSS selector** is a pattern used to target and select specific HTML elements on a webpage so you can apply styles to them.

## It tells the browser **which elements** the CSS rules should apply to.

## 1. Element Selectors

### What is an Element Selector?

An **element selector** targets HTML elements directly by their **tag name**.

```css
section {
  color: red;
}
```

This will apply the style to all <section> elements in the document.

## 2. ID Selector

### What is an ID Selector?

An **ID** selector targets an element with a specific **id** attribute using the **#** symbol.

```css
#elem-1 {
  color: blue;
}
```

This will apply the style to the element with an id of "elem-1".

### Rules for IDs:

- Must be unique on a page.
- Can’t start with a number.
- Allowed characters: letters, digits, hyphens (-), and underscores (\_).
- Example of valid IDs: #header, #main-content

## 3. Class Selector

## What is a Class Selector?

A class selector targets elements with a given **class** using the **.** symbol.

```css
.elem-2 {
  color: purple;
}
```

### Rules for Class Names:

- Can be reused across multiple elements.
- Cannot start with a number.
- Allowed characters: letters, digits, hyphens (-), underscores (\_).

## Adding Multiple Classes:

You can assign multiple class names to an element, separated by spaces:

```html
<section class="elem-2 highlight"></section>
```

Both **.elem-2**and **.highlight** styles will be applied.

## 4. Universal Selector

### what is Universal Selector?

- Selects all elements on the page.
- Useful for applying base styles like font or margin reset.

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## grouping selectors

Applies the same styles to multiple selectors at once.

```css
.elem-2,
#elem-1 {
  border: 1px solid black;
}
```

## nested / child selectors

Target specific structure:

```css
.elem-2 > p {
  color: rgb(4, 112, 112);
  font-size: 20px;
}
```

This applies only to <p> elements directly inside .elem-2.

## Pseudo-classes

```css
.elem-2 > p:hover {
  color: black;
}
```

## Specificity Order (Priority)

- Universal Selector (\*)
- Element Selector (section, p, etc.)
- Class Selector (.class)
- Attribute Selector ([type="text"])
- Pseudo-classes (:hover, :first-child)
- ID Selector (#id)
- Inline styles (style="...") – Highest
- !important — Overrides all

---

# c. colors

## overview

In web development, colors play a vital role in enhancing the visual appeal and user experience of a website. Using HTML and CSS, we can easily apply and customize colors for various elements like text, backgrounds, borders, and more.

## Why Use Colors?

- To create visual hierarchy
- To improve readability
- To reflect branding and design consistency
- To highlight important information

## Where Is It Used?

- Backgrounds (background, background-color)
- Text content (color)
- Buttons, borders, headers, footers, and more

## Common Color Formats in CSS

1. **Named Colors**
   These are predefined color names supported by CSS. You just write the name of the color.

```css
article {
  background-color: lightcyan;
  color: darkcyan;
}
```

- Easy to remember
- Limited to around 140 standard names
- Common named colors: red, blue, green, black, white, yellow, purple, orange, gray, etc.

2. **Hex Codes (Hexadecimal Color Values)**

Hex codes are 6-digit codes that represent colors in the format:
`#RRGGBB (R = Red, G = Green, B = Blue)`
Each pair is a number from 00 to FF (which equals 0–255 in decimal).

```css
article {
  background-color: #219ebc;
  color: #023047;
  padding: 60px;
  margin: 20px;
}
```

- Precise and widely used
- Harder to understand at a glance

3. **RGB / RGBA**

RGB stands for Red, Green, Blue – each value ranges from 0 to 255.

```css
article {
  background-color: rgb(33, 150, 243);
  color: rgb(46, 139, 87);
}
```

- More flexible than hex codes
- RGBA adds the Alpha (transparency) value (from 0 = fully transparent to 1 = fully opaque).

```css
background-color: rgba(255, 0, 0, 0.5); /* Semi-transparent red */
```

4. **HSL / HSLA**

HSL stands for:

- Hue – the color angle on the color wheel (0–360)
- Saturation – intensity (0% = gray, 100% = full color)
- Lightness – brightness (0% = black, 100% = white)

```css
article {
  background-color: hsl(240, 100%, 50%);
  color: hsla(240, 100%, 50%, 0.5);
}
```

---

# d. unitInCss

## Overview

In CSS, units determine how big or small things appear on a webpage — including fonts, spacing, width, height, etc. Different units serve different purposes. This guide explains six commonly used units with examples and why you'd use each one.

## Why Are There Different Units?

Different design needs require different kinds of control:

- Some elements need fixed sizes.
- Others should scale based on screen size or user settings.
- Some should be relative to other elements.

## Units Explained

### px (Pixels)

- A fixed unit that does not scale.
- Great when you want exact control (e.g., borders, small spacing).
- Not responsive — the size stays the same on all screens.

**Example from code:**

```css
main {
  border: 5px solid black;
  margin: 20px;
}
```

### em (Relative to Parent)

- Depends on the font-size of the parent.
- Useful for scaling font sizes or spacing within components.
- Can multiply if nested (e.g., 2em inside a 2em = 4x base size).

**Example from code:**

```CSS
header {
  font-size: 2em;
  padding: 1em;
}
```

### rem (Relative to Root)

- Based on the root (html) font-size, usually 16px.
- More predictable than em because it's not affected by nesting.
- Perfect for headings or base sizes that should be consistent.

**Example from code:**

```css
h1 {
  font-size: 3rem;
}
```

### % (Percentage)

- Relative to the size of the parent element.
- Often used for width, height, or padding/margin.
- Helps create flexible layouts that adapt to parent sizes.

**Example from code:**

```css
section {
  width: 80%;
}
```

### vw (Viewport Width)

- 1vw = 1% of the browser window's width.
- Great for full-width sections, responsive containers.
- Scales with screen size.

**Example from code:**

```css
main {
  width: 60vw;
}
```

### vh (Viewport Height)

- 1vh = 1% of the browser window's height.
- Useful for creating full-screen sections or hero banners.

**Example from code:**

```css
main {
  height: 90vh;
}
```

## summary

- Use rem for consistent font sizes.
- Use em when you want scaling based on parent.
- Use px when you need exact control.
- Use % to size things relative to the container.
- Use vw/vh for full-screen responsiveness.

---

# e. CSS Box Model

## Overview

The **CSS Box Model** is the fundamental layout principle in CSS. Every HTML element is considered a rectangular box made up of four parts: **content, padding, border, and margin**.

## What is the Box Model?

The box model consists of:

1. **Content** – The actual text or image inside the element.
2. **Padding** – Space between the content and the border.
3. **Border** – The edge around the padding.
4. **Margin** – The outermost space between the element and other elements.

The total size of an element includes:

**Total Width = margin + border + padding + content width**
**Total Height = margin + border + padding + content height**

## What is the `div` Tag?

The `<div>` tag is a **block-level container** used to group HTML elements for styling and layout purposes. It doesn't add any visual effect by default but is very useful with CSS.

In this example:

```html
<div class="box">BOX</div>
```

The **div** has a class **box** applied to it, which is styled in **style.css.**

**box-sizing: border-box** ensures that **padding** and **border** are included inside the defined width and height of an element.

---
