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

##

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
