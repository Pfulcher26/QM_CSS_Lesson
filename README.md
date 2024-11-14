# CSS and CSS Selectors in Web Development & QM

## Table of Contents
- [Introduction: HTML, JavaScript, and CSS](#introduction-html-javascript-and-css)
- [What is CSS?](#what-is-css)
- [What is a CSS Selector?](#what-is-a-css-selector)
- [Targeting CSS in Style Sheets](#practice-css)
- [Targeting CSS with Javascript](#live-example)
- [How Quantum Metric Uses CSS Selectors](#how-quantum-metric-uses-css-selectors)
  - Events
  - PII Remediation
  - Zones
  - Segments/Metrics
- [Useful Links](#useful-links)
- [CSS Cheat Sheet](#css-cheat-sheet-for-queryselector)

---

## Introduction: HTML, JavaScript, and CSS 

When building a website, HTML, JavaScript, and CSS work together like the body’s structure. Here's a simple way to think about their roles:

- **HTML** is like the bones of the body. It provides the essential structure and framework of a web page—without HTML, there's nothing to build upon.
- **JavaScript** is like the muscles. It moves the body and makes things interactive. With JavaScript, we can manipulate the structure, add functionality, and make the website dynamic.
- **CSS** is like the skin. It covers the bones, adds color, texture, and visual appeal, making everything look good and presentable to the user.

By working together, these three languages bring a website to life!

<img src="https://github.com/user-attachments/assets/3a1e783e-e1d9-489f-a006-bfbe4868cb6f" width="600" height="600" />

---

## What is CSS?

CSS, or Cascading Style Sheets, is a language used in web development to define the look and feel of a web page. By styling HTML elements, CSS allows developers to create visually appealing layouts, control colors, fonts, spacing, and more.

### Key Elements of CSS:
- **Class** (`.classname`): Targets one or multiple elements with the same class name.
- **ID** (`#idname`): Targets a unique element with a specific ID.
- **Data Attributes** (`[data-*="value"]`): Custom attributes that store extra information on elements without affecting HTML structure.

---

## What is a CSS Selector?

A CSS selector is a pattern used to target HTML elements for styling or scripting. Selectors specify which elements in the document tree a CSS rule applies to. They are essential for any styling or element-targeting task in CSS or JavaScript.

### Types of CSS Selectors:
- **Simple Selectors**: Target elements by type, class, or ID (e.g., `p`, `.classname`, `#idname`).
- **Attribute Selectors**: Target elements with specific attributes (e.g., `[type="text"]`, `[data-role="button"]`).
- **Pseudo-Classes**: Target elements in a specific state (e.g., `:nth-child`, `:hover`, `:first-child`).
- **Combinator Selectors**: Target elements based on their relationship (e.g., `.parent .child`, `.sibling + .adjacent`). 

---

## Targeting CSS in Style Sheets

Let's use REPLIT to do a simple exercise demonstrating the types of CSS selectors in action. 

[Try out CSS on Replit here!](https://replit.com/)

---

## Why Data Attributes Are Important for Dynamically Generated CSS

Data attributes are essential for sites that use dynamically generated CSS because they provide a reliable way to target and interact with elements regardless of changing class names or IDs. When CSS is dynamically created or updated—such as during user interactions or content changes—data attributes remain static, ensuring elements can still be targeted by JavaScript and CSS selectors. This separation of concerns helps maintain clean code and improves performance. 

---

## Targeting CSS in Stylesheets vs. querySelector

While CSS stylesheets and the `querySelector` method both use CSS selectors to target elements on a web page, they serve different purposes and are used in different contexts.

### CSS Stylesheets:
- CSS selectors in stylesheets are used to define the visual appearance of elements across a webpage. Once a page is loaded, the CSS rules are applied to all matching elements automatically, without requiring JavaScript intervention.

### querySelector in JavaScript:
- The `querySelector` method, on the other hand, is used to select individual elements dynamically within JavaScript code, often to manipulate the selected elements (e.g., change styles, add event listeners, or retrieve values).
  
---

## Targeting CSS with Javascript

Let's use [Tofugu](https://www.tofugu.com/) to understand how we can use `querySelector` to target different web page elements using CSS. Open the Developer Tools (right-click > Inspect or press F12, or press `Command + Option + J` on Mac), and try selecting different elements on the page. Observe how CSS selectors are used to target elements for styling and structure.

---

## How Quantum Metric Uses CSS Selectors

### Events
Quantum Metric can trigger events based on CSS selectors.  These are often used for click events, selector present events and when writing custom Javascript events. 

### PII Remediation
CSS selectors help isolate and remediate PII (Personally Identifiable Information) by selecting specific input fields or data points on the page and anonymizing them.

### Zones
To be completed by Rutger

### Segments/Metrics
To be completed by Rutger

---

## CSS Cheat Sheet for querySelector

Below is a quick reference to some of the most commonly used CSS selectors, specifically for use with `querySelector` in JavaScript.

### Common CSS Selectors for querySelector
- **Universal Selector** (`*`): Targets all elements.
  ```javascript
  document.querySelector('*'); // Selects the first element on the page

- **Type Selector** (`element`): Targets all instances of a specific element.
  ```javascript
  document.querySelector('p'); // Selects the first <p> element

- **Class Selector** (`.classname`): Targets elements with a specific class.
  ```javascript
  document.querySelector('.header'); // Selects the first element with the class 'header'

- **ID Selector** (`#idname`): Targets a unique element with an ID.
```javascript
document.querySelector('#main-content'); // Selects the element with the ID 'main-content'
```

- **Attribute Selector** (`[attr="value"]`): Targets elements with a specific attribute value.
```javascript
document.querySelector('[type="text"]'); // Selects the first element with type="text"
```

- **Greedy Attribute Selector - Universal** (`[attr*="value"]`): Targets elements whose attribute value contains a specified substring.
```javascript
document.querySelector('[data-role*="admin"]'); // Selects the first element with data-role containing "admin"
```

- **Greedy Attribute Selector - Starts With** (`[attr^="value"]`): Targets elements whose attribute value starts with a specified string.
```javascript
document.querySelector('[data-category^="elec"]'); // Selects the first element with data-category starting with "elec"
```

---

## Combinator Selectors and the `>` Symbol

The `>` (child combinator) selector targets direct child elements of a specified parent element. This is useful when you want to select elements that are immediate children of a given element, excluding deeper nested elements.

### Direct Child Selector (`>`): Selects direct children of a parent element.

```javascript
document.querySelector('.parent > .child'); // Selects the first .child element that is a direct child of .parent
```

In this example, .child must be a direct child of .parent. If .child is nested deeper inside another element within .parent, it will not be selected.

***Example:***

```html
<div class="parent">
  <div class="child"></div> <!-- This will be selected -->
  <div>
    <div class="child"></div> <!-- This will NOT be selected -->
  </div>
</div>
```

### Combinations with Other Selectors

You can combine the `>` selector with other selectors for more specific targeting.

```javascript
document.querySelector('.parent > .child:nth-child(2)'); // Selects the second .child that is a direct child of .parent

```

---

## Useful Links

Here are some valuable resources for learning and referencing CSS and CSS Selectors:

- [MDN Web Docs on CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)  
  Comprehensive documentation on CSS syntax, selectors, properties, and more.
- [MDN Web Docs on CSS Selectors](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Selectors)  
  Detailed explanation of different CSS selectors, including advanced options.
- [CSS-Tricks](https://css-tricks.com/)  
  A web design and development blog with tips, tutorials, and guides on CSS.
- [W3Schools CSS Tutorial](https://www.w3schools.com/css/)  
  A beginner-friendly resource for learning CSS with examples and exercises.
- [Can I Use](https://caniuse.com/)  
  A site to check browser compatibility for various CSS properties.

---


  
