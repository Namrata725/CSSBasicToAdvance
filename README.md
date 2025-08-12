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

# f. text and font styling

## Overview

This is a simple webpage with two sections:

- The **first section** demonstrates text-related properties like color, alignment, spacing, and decoration.
- The **second section** focuses on font-related properties including Google Fonts, font variants, weight, and web-safe fonts.

## Why This?

Text and font styling are core parts of CSS that control how content looks and feels. This example helps you understand how each property works and improves the visual presentation of your web pages.

### Text Styling Used

- **Text color:** Changes the color of text (e.g., blue).
- **Text alignment:** Aligns text to the left, right, center, or justified.
- **Text decoration:** Adds underline with custom color, style, and thickness.
- **Text transform:** Converts text to uppercase.
- **Text indent:** Indents the first line of text.
- **Letter spacing:** Adjusts space between letters.
- **Line height:** Controls vertical space between lines.
- **Word spacing:** Increases space between words.
- **Text shadow:** Adds layered colored shadows behind text for a 3D effect.

### Font Styling Used

- **Font family:** Applies different fonts like Tahoma (web-safe) and Raleway (Google Font).
- **Font style:** Applies italic style.
- **Font weight:** Makes text bold (e.g., weight 900).
- **Font variant:** Uses small-caps (uppercase letters in smaller size).
- **Font size:** Sets font size (e.g., 20px).

### Google Fonts

This project imports the **Raleway** font using `@import`:

```css
@import url("https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,100..900;1,100..900&display=swap");
```

---

# f. Display Propertise

## Overview

In HTML, elements have default display behaviors:

- **Block elements** take up the full width available and start on a new line.
- **Inline elements** flow within a line and only take up as much width as their content.
- **Inline-block elements** behave like inline elements but allow setting width and height like block elements.
- **none** elements are invisible and do not take up any space.

### HTML Elements Used

- **Block-level elements:** `<div>`, `<h1>`, `<p>`, `<nav>`, `<ul>`, `<li>`
- **Inline elements:** `<span>`, `<a>`, `<img>`

### CSS Highlights

```css
/* Changes a paragraph to behave like inline */
.inline-P {
  display: inline;
}

/* Changes a paragraph to behave like inline */
.inline-P {
  display: inline;
}

/* This hides the second paragraph using display: none */
.inline-P2 {
  display: none;
}
```

## Display Types

**Block Elements**

- Start on a new line.
- Take up full width by default.
- Allow setting width, height, margin, and padding.

**examples : div, p, ul, li, h1, h2, h3, h4, h5, h6, nav, a, img**
**Inline Elements**

- Do not start on a new line.
- Only take up as much width as necessary.
- You cannot set width or height directly.
- You can set margin and padding.Padding and margin (top/bottom) have no visible effect.

**examples : span, a, img**

**Inline-Block Elements**

- Behave like inline elements (stay in line with text).
- Allow setting width, height, padding, and margin.

**Examples** any element styled with display: inline-block

**display: none**

- Completely removes the element from rendering.
- The element will not take any space.

### **Examples** any element styled with display: none

---

# h. css position properties

## Overview

The CSS `position` property specifies how an element is positioned in the document. It affects how the element is placed, whether it scrolls with the page, and what it’s relative to.

This demo visually compares all six types of positioning inside a container using color-coded boxes.

## Position Values Explained

### 1 `static` (default)

- All HTML elements are **static** by default.
- They appear in the normal document flow.
- Top, right, bottom, and left values have **no effect**.
  **Example:** `.darkcyan` box

### 2 `relative`

- The element remains in the document flow.
- You can shift it using `top`, `left`, `right`, or `bottom`.
- **Positioning is relative to its original position**, not its parent.
  **Example:** `.red` box

Only `top` and `left` are applied when all four (top, bottom, right, left) are set. This is because in case of conflicts, browsers prioritize the ones that move the element **away** from its normal flow.

### 3 `absolute`

- Removed from the normal document flow.
- Positioned **relative to the nearest positioned (non-static) ancestor**.
- If no such ancestor exists, it is positioned relative to the `<html>` element.
  **Example:** `.green` box If a box "disappears", it's usually because it moved out of view or got covered due to stacking context.

### 4 `fixed`

- Positioned relative to the **viewport** (the browser window).
- Stays fixed when the page scrolls.
- Useful for sticky headers, floating buttons, etc.

  **Examples:**

- `.blue` box (bottom-right corner)
- `.orange` box (next to it, using `right: 50px`)

### 5 `sticky`

- Behaves like `relative` until it crosses a scroll threshold.
- Then it becomes `fixed` and sticks to the defined offset (e.g., `top: 50px`).
- Requires a scrollable container or enough vertical space to work.
  **Example:** `.purple` box Related to its **scrollable parent**.

## Z-Index

The `z-index` property defines the **stacking order** of elements (which elements appear on top of others).

- Higher `z-index` values appear above lower ones.
- Only works on elements with `position` set to `relative`, `absolute`, `fixed`, or `sticky`.

  **Example in Code:**

- `.blue` box has `z-index: 1`
- `.purple` box has `z-index: 5` (appears above `.blue`)
- `.container` itself has a `z-index: 12` (for context)

---

# i. css float, clear and overflow

## Overview

The CSS `float`, `clear`, and `overflow` properties are used to control how elements behave when positioned side-by-side, wrap text around images, or when content exceeds its container.

## Overflow

The `overflow` property manages how content behaves when it exceeds the container’s boundaries.

### Values of `overflow`:

- `visible`  
  Default. Content spills out of the container visibly.

- `hidden`  
  Content is clipped and overflow is not visible.

- `scroll`  
  Adds scrollbars regardless of whether content overflows.

- `auto`  
  Adds scrollbars only when content overflows.

**Example in code:**

- `.float-container` in `index.html` uses `overflow: auto` to expand and contain floated children.
- Other values like `hidden`, `scroll`, and `visible` can be tested by uncommenting the lines in `style.css`.

## Float

The `float` property is used to position elements to the left or right, allowing surrounding inline content (like text) to wrap around the floated element.

### Values of `float`:

- `left`  
  Floats the element to the left side of its container.

- `right`  
  Floats the element to the right side of its container.

- `none`  
  Default. Element is not floated and appears in the normal document flow.

- `inherit`  
  Inherits the float value from its parent element.

  **Examples in code:**

- `.float-left` image floats to the left, allowing text to wrap on the right.
- `.float-right` image floats to the right, allowing text to wrap on the left.
- `.box` class in `index2.html` demonstrates floating colored boxes.

## Clear

The `clear` property is used to control the behavior of elements after floated elements. It prevents the element from wrapping around floated siblings.

### Values of `clear`:

- `left`  
  Prevents the element from sitting next to any left-floated elements.

- `right`  
  Prevents the element from sitting next to any right-floated elements.

- `both`  
  Prevents the element from sitting next to both left and right floats.

- `none`  
  Default. Allows floating elements beside it.

---

# j. Sign-Up mini project

## Overview

This project demonstrates a modern, stylish sign-up form using **glassmorphism** design. It uses layout positioning (`absolute`, `relative`, `transform`), input styling, hover effects, and layered circular backgrounds with blur filters for a soft, frosted look.

The layout is responsive to viewport dimensions using `100vw` and `100vh`, and visually enhanced with gradient backgrounds and box shadows.

## Layout

### outer-box

- Covers the entire viewport using `width: 100vw; height: 100vh;`.
- Has a diagonal background gradient:  
  `background: linear-gradient(to top left, #3ed8ff, #a8f5ff);`

  ### inner-box

- The main container for the form.
- Positioned in the vertical center using:
  ```css
  position: relative;
  top: 40%;
  transform: translateY(-50%);
  ```
- Applies `backdrop-filter: blur(8px);` for the frosted glass effect.
- Has padding, rounded corners, and box-shadow for depth.

### Form Sections

- **Header (`.signup-header`)**: Contains a large heading and subtext.
- **Body (`.signup-body`)**: Contains the form elements and spacing.
- **Footer (`.signup-footer`)**: Contains a login link for existing users.

## Form Inputs

Each input field includes:

- Full-width styling with padding and border.
- Rounded corners and spacing.
- `input[type="submit"]` has a dark background and white text by default.
- On hover, it changes to light blue (`#3ed8ff`) with dark text.

## Decorative Circles

- Two `div.circle` elements are absolutely positioned for design enhancement.
- They have:
  ```css
  width: 150px;
  height: 150px;
  border-radius: 50%;
  background: linear-gradient(to top right, #ffffff33, #ffffffff);
  ```

### Positions:

- `.c1` — top-left of the screen (`top: 100px; left: 40px;`)
- `.c2` — bottom-right of the screen (`bottom: 200px; right: 50px;`)

## Fonts

- Uses `Lato` and `Raleway` via Google Fonts.

  ```css
  @import url("https://fonts.googleapis.com/css2?family=Lato:wght@400;700&family=Raleway:ital,wght@0,100..900;1,100..900&display=swap");
  ```

---

# k. CSS Flexbox: Container and Item Properties

## Overview

Flexbox is a **one-dimensional layout system** in CSS that allows you to align and distribute space among items inside a container. It simplifies creating flexible and responsive layouts without relying on floats or positioning.

This demo illustrates the **flex container** and **flex item** properties using a set of boxes that adjust their position and size based on different Flexbox rules.

## What is Flexbox?

- **Flexbox** (Flexible Box Layout) is designed to provide **space distribution** and **alignment capabilities** for elements within a container.
- It operates along two axes:
  - **Main axis** (horizontal by default)
  - **Cross axis** (vertical by default)
- Elements inside a flex container become **flex items**, which can be arranged in various ways.

## Properties of Flex Container

A container becomes a **flex container** by setting:

```css
display: flex;
```

### 1. `flex-direction`

Determines the **main axis** (the direction of flex items):

- `row` (default) – items placed left to right
- `row-reverse` – items placed right to left
- `column` – items placed top to bottom
- `column-reverse` – items placed bottom to top

### 2. `flex-wrap`

Controls whether flex items wrap to the next line:

- `nowrap` (default) – all items stay on one line
- `wrap` – items wrap to the next line
- `wrap-reverse` – items wrap in reverse order

### 3. `flex-flow`

Shorthand for `flex-direction` and `flex-wrap`.

```css
flex-flow: row wrap;
```

### 4. `justify-content`

Aligns items **along the main axis**:

- `flex-start` (default) – items align at the start
- `flex-end` – items align at the end
- `center` – items align at the center
- `space-between` – equal space between items
- `space-around` – equal space around items
- `space-evenly` – equal space distributed across

### 5. `align-items`

Aligns items **along the cross axis**:

- `stretch` (default) – items stretch to fill container
- `flex-start` – items align at the start of the cross axis
- `flex-end` – items align at the end of the cross axis
- `center` – items align at the center of the cross axis
- `baseline` – items align by their text baseline

### 6. `align-content`

Aligns **multiple lines** (when wrapping is enabled):

- `stretch` (default)
- `flex-start`
- `flex-end`
- `center`
- `space-between`
- `space-around`
- `space-evenly`

## Properties of Flex Items (Children)

### 1. `order`

Controls the order of items. Default is `0`. Lower values appear first.

### 2. `flex-grow`

Specifies how much an item should **grow** relative to others.

### 3. `flex-shrink`

Specifies how much an item should **shrink** relative to others.

### 4. `flex-basis`

Defines the **initial size** of a flex item before remaining space is distributed.

### 5. `flex`

Shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`.

```css
flex: 0 0 200px;
```

### 6. `align-self`

Overrides `align-items` for a single flex item:

- `auto` (default)
- `flex-start`
- `flex-end`
- `center`
- `baseline`
- `stretch`

---

# i. grid layout

## Overview

CSS Grid is a **two-dimensional layout system** that allows control over both rows and columns. Unlike Flexbox (which is one-dimensional), Grid is ideal for creating complex layouts like galleries, dashboards, and full-page designs.

## Why Use Grid?

1. Simplifies complex layouts without using floats or positioning hacks.
2. Allows **precise placement** of elements in rows and columns.
3. Supports **fractional units (fr)**, **auto-sizing**, and **spanning multiple cells**.
4. Enables **responsive layouts** with `auto-fit` and `auto-fill`.

## Grid Container Properties

A container becomes a grid when you set:

```css
display: grid;
```

### 1. `gap`

- Defines space **between rows and columns** (not inside items).
- Previously achieved using `grid-row-gap` and `grid-column-gap`.
- Examples:
  ```css
  gap: 10px; /* equal spacing for rows and columns */
  gap: 10px 20px; /* 10px between rows, 20px between columns */
  ```
- Useful for separating items visually without adding margins.

### 2. `grid-template-columns`

- Defines the **number and size of columns**.
- Supported units:

  - **Fixed units** (`px`): Exact sizes.
    ```css
    grid-template-columns: 100px 200px 300px;
    ```
  - **Percentages**: Relative to container width.
    ```css
    grid-template-columns: 20% 30% 50%;
    ```
  - **Fractional units (`fr`)**: Distributes available space.
    ```css
    grid-template-columns: 1fr 2fr; /* second column is twice as wide */
    ```
  - **Repeat function**: Avoids repetition.
    ```css
    grid-template-columns: repeat(3, 1fr);
    ```
  - **Auto-fit / Auto-fill**: Creates dynamic grids.

    ```css
    grid-template-columns: repeat(auto-fill, 300px);
    ```

    3.  `grid-template-rows`

- Works like `grid-template-columns` but controls **row sizes**.
- Example:

  ```css
  grid-template-rows: 200px 80px; /* first row 200px, second row 80px */
  grid-template-rows: 1fr 2fr; /* second row takes double space */
  ```

  ### 4. `grid-auto-rows`

- Sets height for **rows automatically generated** (when more items exist than defined rows).
- Example:

  ```css
  grid-auto-rows: 150px;
  ```

  ### 5. `justify-content` (Horizontal alignment of the entire grid)

- Moves the **entire grid horizontally** inside the container.
- Options:

  - `start` – aligns grid to left.
  - `end` – aligns grid to right.
  - `center` – centers grid.
  - `space-between` – equal space between columns.
  - `space-around` – equal space around columns.
  - `space-evenly` – equal space distributed across.
  - `stretch` (default) – columns stretch to fill container.

  ### 6. `align-content` (Vertical alignment of the entire grid)

- Moves the **entire grid vertically** inside the container.
- Options mirror `justify-content`.

### 7. `align-items` (Vertical alignment of items within cells)

- Aligns items **within their cells vertically**.
- Options:
  - `start` – aligns items to top of cell.
  - `end` – aligns items to bottom of cell.
  - `center` – centers items vertically.
  - `stretch` (default) – stretches items to fill cell height.

## Grid Item (Children) Properties

### 1. `justify-self`

- Controls **horizontal alignment** of a single item within its cell.
- Options:
  - `start` – aligns to left.
  - `end` – aligns to right.
  - `center` – centers horizontally.
  - `stretch` (default) – fills entire width.

### 2. `align-self`

- Controls **vertical alignment** of a single item within its cell.
- Options:
  - `start` – aligns to top.
  - `end` – aligns to bottom.
  - `center` – centers vertically.
  - `stretch` (default) – fills entire height.

### 3. `grid-column`

- Makes items **span multiple columns**.
- Examples:

  ```css
  grid-column: 1 / 3; /* spans from column 1 to 3 */
  grid-column: 1 / span 2; /* spans 2 columns starting at 1 */
  grid-column: 1 / -1; /* spans all columns */
  ```

  ### 4. `grid-row`

- Makes items **span multiple rows**.
- Examples:
  ```css
  grid-row: 1 / 4; /* spans from row 1 to 4 */
  grid-row: 2 / span 3; /* spans 3 rows starting from row 2 */
  ```

### 5. `grid-area`

- Shorthand for:
  ```
  grid-row-start / grid-column-start / grid-row-end / grid-column-end
  ```
- Example:
  ```css
  grid-area: 1 / 1 / 3 / 3;
  ```
  This places the item starting at **row 1, column 1**, and ending at **row 3, column 3**.

## Notes

- Use `justify-*` for **horizontal control**.
- Use `align-*` for **vertical control**.
- Combine both for precise placement of items.

## Related Files

- **index.html** – Demonstrates grid layout with multiple boxes.
- **style.css** – Defines container and item properties with examples.
- **index2.html** – Additional grid structure.
- **style2.css** – Styles for the second example.

---

# m.Media Queries

## Overview

**CSS Media Queries** allow you to apply styles conditionally based on device characteristics like **screen size**, **orientation**, and **resolution**.  
They are the foundation of **responsive web design**, enabling a website to adapt to different devices such as phones, tablets, and desktops without creating separate versions.

## Why Use Media Queries?

1. **Responsive Design** – Ensures your site looks good on all devices.
2. **Better User Experience** – Content is readable and accessible without zooming or scrolling horizontally.
3. **Device Adaptation** – Adjusts styles for mobile, tablet, and desktop easily.
4. **Improved SEO** – Search engines favor mobile-friendly websites.
5. **Future-Proofing** – Automatically adapts to new devices and screen sizes.

## Syntax

A media query starts with `@media` followed by a condition and a CSS block:

```css
@media (condition) {
  /* Styles here */
}
```

Multiple conditions can be combined using and, or, and not operators.

### `1. Exact Width`

```css
@media (width <= 400px) {
  body {
    background-color: green;
  }
}
```

Applies styles if the viewport width is 400px or less.

### `2. Orientation`

```css
@media (orientation: portrait) {
  body {
    background-color: orangered;
  }
}
```

Applies styles when the device is in portrait mode.

### `3. Maximum Width`

```css
@media (max-width: 200px) {
  body {
    background-color: goldenrod;
  }
}
```

Applies styles if the viewport is 200px or narrower.

### `4. Minimum Width`

```css
@media (min-width: 600px) {
  body {
    background-color: teal;
  }
}
```

Applies styles if the viewport is 600px or wider.

### `5. Range (Min & Max Width)`

```css
@media (min-width: 400px) and (max-width: 500px) {
  body {
    background-color: brown;
  }
}
```

Applies styles only if the width is between 400px and 500px.

## Notes

- `Default Styles First:` Always define your base styles first, then override them with media queries.
- `Mobile-First Approach:` Start with small-screen styles and add larger breakpoints using min-width.
- `Avoid Too Many Breakpoints:` Use only the necessary ones to keep code clean.
- `Test Across Devices:` Use browser DevTools to simulate different devices.

---

# n. css variables

## overview

**CSS variables** are entities defined by CSS authors that contain specific values to be reused throughout a stylesheet. They follow a syntax like `--variable-name` and are accessed using the `var()` function. Variables make it easier to maintain and update styles consistently.

## Why Use CSS Custom Properties?

1. **Reusability** — Define a value once and reuse it throughout your styles.
2. **Maintainability** — Change the value in one place to update the entire site’s theme.
3. **Theming** — Easily create dark/light modes or different color schemes by overriding variables.
4. **Dynamic Updates** — Variables can be manipulated by JavaScript or media queries for responsive designs.

---

in our code

- `.container`wraps all content.
- `.box` elements represent content boxes.
- `.dark` class on `.box `overrides default colors for dark theme.

---

### CSS Explanation

**Global Variables (:root)**

```css
:root {
  --primary-text-color: teal;
  --secondary-text-color: black;
  --primary-background-color: #fff;
  --container-background-color: #eee;
  --default-margin-padding: 30px;
}
```

- Variables defined globally are accessible throughout the document.

**Dark Theme Override (.dark)**

```css
.dark {
  --primary-text-color: white;
  --secondary-text-color: white;
  --primary-background-color: black;
  --container-background-color: rgba(0, 0, 0, 0.288);
}
```

- Overrides global variables locally for elements with .dark class.
- Changes text color to white and background to black, creating a dark mode effect.

**Container Styling**

```css
.container {
  padding: 40px;
  background-color: var(--container-background-color);
  height: 100vh;
}
```

- Uses the container background color variable.
- Adds padding and full viewport height.

**Box Styling**

```css
.box {
  padding: var(--default-margin-padding);
  background-color: var(--primary-background-color);
  color: var(--secondary-text-color);
  margin-block: var(--default-margin-padding);
  border-radius: var(--default-margin-padding);
}
```

- Boxes use variables for padding, background, text color, margin, and border-radius.

**Headings Styling**

```css
h1 {
  text-align: center;
  color: var(--primary-text-color);
}

h2 {
  margin-bottom: var(--default-margin-padding);
}
```

- Heading colors and spacing use the custom properties.

**Responsive Design with Media Query**

```css
@media (max-width: 800px) {
  .box {
    --my-var: green;
  }
}
```

- Demonstrates how custom properties can be overridden inside a media query for responsive behavior.
- Although --my-var is declared but not used in this example, it shows the concept of dynamically changing variables at different viewport widths.

## Notes

- Custom properties cascade and can be overridden locally.
- Variables can be used anywhere a CSS property accepts values (colors, sizes, spacing).
- Use media queries to adjust variables for responsive and adaptive designs.
- This approach simplifies theming and style consistency across the site.

---

# o.CSS Pseudo-Classes & Pseudo-Elements Demo

## Overview

A **pseudo-class** is a keyword added to selectors that specifies a special state of the selected element.

- **Pseudo-classes** target elements in a special state (e.g., `:hover`, `:first-child`).
- **Pseudo-elements** style specific parts of an element (e.g., `::first-letter`, `::before`).

### Examples in This Project:

- `:link` — Styles an unvisited link.
- `:visited` — Styles a visited link.
- `:hover` — Styles when the mouse is over the element.
- `:active` — Styles when the element is clicked.
- `:first-child` — Selects the first child of its parent.
- `:last-child` — Selects the last child of its parent.
- `:nth-child(n)` — Selects the nth child (can use formulas like `2n+3`).

## What are CSS Pseudo-Elements?

A **pseudo-element** allows you to style specific parts of an element's content.

### Examples in This Project:

- `::first-letter` — Styles the first letter of an element.
- `::first-line` — Styles the first line of text.
- `::selection` — Styles the portion of text the user has highlighted.
- `::before` — Inserts generated content before an element.
- `::after` — Inserts generated content after an element.

### CSS Features Used

**1. Link States**

```css
.primary-button:link {
  color: green;
}
.primary-button:visited {
  color: red;
}
.primary-button:hover {
  color: orange;
  background-color: #eee;
}
.primary-button:active {
  color: purple;
}
```

- Demonstrates styling links in different states.

**2. Child Selectors**

```css
ul li:first-child {
  color: blue;
}
.second-li li:last-child {
  color: purple;
}
.second-li li:nth-child(3) {
  background-color: violet;
}
.second-li li:nth-child(2n + 3) {
  background-color: gray;
}
```

- Targets elements based on position within the parent.

**3. Pseudo-Elements for Text Styling**

```css
main p::first-letter {
  font-size: 50px;
}
main h2::first-letter {
  font-size: 50px;
}
main p::first-line {
  background-color: violet;
}
main p::selection {
  color: greenyellow;
  background-color: black;
}
```

- Styles specific portions of text like first letters, first lines, and selected text.

**4. Content Insertion**

```css
h3::before {
  content: "any, ";
}
h3::after {
  content: " *";
}
```

- Adds generated text before and after an element without changing HTML.

---

# p. # CSS `transform` Property

## Overview

The **`transform`** property in CSS allows you to visually manipulate an element by scaling, skewing, rotating, or translating it in 2D or 3D space without affecting the document flow.

## Common Transform Functions

- **scale()** → Changes the size of the element. Default value is `1` (original size).
- **rotate()** → Rotates the element by a given angle. Default value is `0deg` (no rotation).
- **skew()** → Skews (distorts) the element along the X and/or Y axis. Default value is `0deg`.
- **translate()** → Moves the element from its original position along X and/or Y axis.

### Supported Values:

- Keywords: `left`, `center`, `right`, `top`, `bottom`
- Length values (px, %, etc.)
- Default: `50% 50%` (center of the element)
- Syntax: `transform-origin: x-axis y-axis;`

## Example Code

### HTML

```html
<div class="container">
  <div class="box">box</div>
</div>
```

### CSS

```css
.container {
  height: 400px;
  width: 400px;
  background: teal;
  margin: 80px auto;
}

.box {
  width: 200px;
  height: 200px;
  background-color: orangered;
  font-size: 4rem;
  display: flex;
  justify-content: center;
  align-items: center;
}

.box:hover {
  transition: 0.5s ease;
  transform: rotate(45deg);
  transform-origin: bottom right;
}
```

---

# q. css animation

## Overview

CSS transitions allow you to change property values smoothly over a given duration. Instead of properties changing abruptly, transitions provide gradual animations, improving user experience and visual appeal.

A transition in CSS occurs when a CSS property changes from one value to another over time. This can be triggered by events like hover, focus, active states, or dynamically via JavaScript.

## Transition Properties

1. **transition-delay**

   - Time to wait before the transition starts.
   - Example: `transition-delay: 0.5s;`
   - Default: `0s`

2. **transition-duration**

   - How long the transition takes to complete.
   - Example: `transition-duration: 2s;`
   - Default: `0s`

3. **transition-property**

   - Specifies which CSS property to apply the transition to.
   - Example: `transition-property: transform;`
   - Default: `all`

4. **transition-timing-function**
   - Defines how the intermediate values are calculated.
   - Example: `transition-timing-function: ease;`
   - Default: `ease`

## Common Timing Functions

- **ease** – Slow start, fast middle, slow end
- **ease-in** – Slow start
- **ease-out** – Slow end
- **ease-in-out** – Slow start and end
- **linear** – Constant speed
- **cubic-bezier(n,n,n,n)** – Custom easing curve

---

# r.CSS Keyframes Animation

## Overview: What are Keyframes in CSS?

In CSS, **keyframes** define stages of an animation sequence by specifying styles at specific points in time.
They allow elements to transition smoothly between styles, making web pages more dynamic and interactive.

The `@keyframes` rule specifies the animation code, defining what should happen at various stages of the animation.
You can use percentages (`0%` to `100%`) or keywords (`from` and `to`) to indicate when style changes occur.

## Why Keyframes Animations are Important?

- **Better Visual Experience**: Animations grab user attention and make the website feel alive.
- **Highlight Interactions**: Can be used to guide the user’s eye to important content.
- **Creative Freedom**: Enables complex movements beyond simple transitions.

## CSS Animation Properties

| Property                    | Description                                                                                          | Example                                |
| --------------------------- | ---------------------------------------------------------------------------------------------------- | -------------------------------------- |
| `animation-name`            | The name of the animation to apply (matches the `@keyframes` name).                                  | `animation-name: orbit;`               |
| `animation-duration`        | How long one cycle of the animation takes.                                                           | `animation-duration: 2s;`              |
| `animation-delay`           | Time before the animation starts.                                                                    | `animation-delay: 1s;`                 |
| `animation-iteration-count` | Number of times the animation repeats (`infinite` for endless).                                      | `animation-iteration-count: infinite;` |
| `animation-direction`       | Direction in which the animation plays (`normal`, `reverse`, `alternate`, `alternate-reverse`).      | `animation-direction: alternate;`      |
| `animation-timing-function` | How the animation progresses over time (`linear`, `ease`, `ease-in`, etc.).                          | `animation-timing-function: linear;`   |
| `animation-fill-mode`       | Defines how styles are applied before/after the animation (`none`, `forwards`, `backwards`, `both`). | `animation-fill-mode: forwards;`       |

## Summary

CSS keyframes animations allow you to define complex sequences of visual changes.
By combining multiple animation properties with `@keyframes`, you can create engaging and visually appealing user interfaces.

---
