# Jekyll Components Library Guide

## Introduction

The components library in your Jekyll site is designed to make it easier to maintain and extend your website by providing reusable pieces of code that can be included in multiple pages. This guide outlines the structure and usage of each component.

## Components Structure

The components are stored in the `_components` directory. Each component is a self-contained HTML file that can be included in other layouts, includes, or pages using the Jekyll `{% include %}` or `{% include_relative %}` tags.

### Directory Structure

```plaintext
.
├── _components
│   ├── button.html
│   ├── footer.html
│   └── navigation.html
├── _includes
│   └── header.html
├── _layouts
│   └── default.html
└── ...
```

### Components Overview

1. **Navigation Component**: `_components/navigation.html`
2. **Footer Component**: `_components/footer.html`
3. **Button Component**: `_components/button.html`

---

## 1. Navigation Component

**File**: `_components/navigation.html`

### Description
The navigation component provides a simple, reusable navigation bar that can be included in the header of your site or anywhere else where navigation is required.

### Usage
To include the navigation component in a page or layout:

```liquid
{% include_relative ../_components/navigation.html %}
```

### Example
The navigation component is used in the `_includes/header.html` file:

```liquid
<header>
  <h1>{{ site.title }}</h1>
  <p>{{ site.description }}</p>
  {% include_relative ../_components/navigation.html %}
</header>
```

### Customization
To customize the navigation links, simply edit the `_components/navigation.html` file:

```html
<nav>
  <ul>
    <li><a href="{{ '/' | relative_url }}">Home</a></li>
    <li><a href="{{ '/about/' | relative_url }}">About</a></li>
    <li><a href="{{ '/contact/' | relative_url }}">Contact</a></li>
  </ul>
</nav>
```

---

## 2. Footer Component

**File**: `_components/footer.html`

### Description
The footer component is a reusable footer that can be included at the bottom of every page.

### Usage
To include the footer component in a page or layout:

```liquid
{% include_relative ../_components/footer.html %}
```

### Example
The footer component is used in the `_layouts/default.html` file:

```liquid
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{ page.title }}</title>
  <link rel="stylesheet" href="{{ '/assets/css/style.css' | relative_url }}">
</head>
<body>
  {% include header.html %}
  <main>
    {{ content }}
  </main>
  {% include_relative ../_components/footer.html %}
</body>
</html>
```

### Customization
To customize the footer text or styling, edit the `_components/footer.html` file:

```html
<footer>
  <p>&copy; 2024 {{ site.title }}. All rights reserved.</p>
</footer>
```

---

## 3. Button Component

**File**: `_components/button.html`

### Description
The button component provides a simple, styled button that can be reused across your site.

### Usage
To include the button component in a page or layout:

```liquid
{% include_relative ../_components/button.html text="Your Button Text" %}
```

### Example
The button component is used in the `about.md` page:

```markdown
---
layout: default
title: About
permalink: /about/
---

# About This Site

This site is a template for creating modular Jekyll websites that integrate with GitHub Pages and GitHub Actions for automated deployment and code quality checks.

{% include_relative ../_components/button.html text="Learn More" %}
```

### Customization
To customize the button's appearance or behavior, edit the `_components/button.html` file:

```html
<button style="background-color: #008CBA; color: white; padding: 10px 20px; border: none; border-radius: 4px; cursor: pointer;">
  {{ include.text }}
</button>
```

You can modify the `style` attribute to change the button's color, padding, borders, etc.

### Dynamic Text
The button text is dynamic and passed as a parameter when including the button. For example:

```liquid
{% include_relative ../_components/button.html text="Click Me!" %}
```

---

## Best Practices

- **Reuse Components**: Instead of writing the same code multiple times, create a component and reuse it throughout your site. This makes it easier to maintain consistency and apply site-wide updates.
- **Keep Components Modular**: Each component should have a single responsibility (e.g., navigation, footer, button). This makes them easier to reuse and customize.
- **Document Your Components**: As your library grows, document your components, so you and others understand how to use and customize them.

## Extending the Components Library

To add a new component:

1. Create a new `.html` file in the `_components` directory.
2. Write your HTML, CSS, and Liquid code for the component.
3. Include the component in your layouts or pages using `{% include_relative %}` or `{% include %}`.
4. Document the component in this guide for future reference.

---
