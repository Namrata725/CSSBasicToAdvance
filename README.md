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

## b. CSS Selectors

# CSS Selectors & Styling Guide

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

# Specificity Order (Priority)

- Universal Selector (\*)
- Element Selector (section, p, etc.)
- Class Selector (.class)
- Attribute Selector ([type="text"])
- Pseudo-classes (:hover, :first-child)
- ID Selector (#id)
- Inline styles (style="...") – Highest
- !important — Overrides all

---
