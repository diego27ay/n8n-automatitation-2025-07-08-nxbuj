# n8n Landing Page Maintenance Guide

This guide will help you maintain and customize the n8n landing page. Whether you're new to web development or just getting started with HTML and CSS, we'll walk you through the essential modifications you might need to make.

## Table of Contents
- [Updating Text and Styling](#updating-text-and-styling)
- [Managing Links](#managing-links)
- [Adding Privacy and Terms Pages](#adding-privacy-and-terms-pages)
- [Troubleshooting](#troubleshooting)

## Updating Text and Styling

### Header Section
The header contains your main navigation and logo. To update the logo text:

```html
<!-- Find this line in the header section -->
<a href="/" class="text-2xl font-bold bg-gradient-to-r from-purple-500 to-pink-500 bg-clip-text text-transparent">n8n.auto</a>
```

To change the logo text, simply replace "n8n.auto" with your desired text. The gradient effect will automatically apply to your new text.

### Hero Section
The hero section is your main landing area. To update the main headline:

```html
<h1 class="text-4xl md:text-5xl lg:text-7xl font-extrabold mb-8 bg-gradient-to-r from-purple-400 to-pink-400 bg-clip-text text-transparent">
    Create n8n automations
</h1>
```

The text sizes are responsive:
- `text-4xl`: Mobile devices
- `md:text-5xl`: Medium screens
- `lg:text-7xl`: Large screens

### Features Section
To add or modify feature cards:

1. Locate the features grid:
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
```

2. Copy an existing feature card and customize:
```html
<div class="bg-gray-800 rounded-2xl p-8 hover:scale-105 transition-transform duration-300 border border-gray-700">
    <div class="w-12 h-12 bg-purple-500/20 rounded-lg flex items-center justify-center mb-6">
        <!-- Icon SVG here -->
    </div>
    <h3 class="text-xl font-semibold mb-4">Your New Feature</h3>
    <p class="text-gray-400">Your feature description</p>
</div>
```

## Managing Links

### Navigation Menu Links
The main navigation menu contains internal links to page sections:

```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="hover:text-purple-400 transition-colors duration-300">Features</a>
    <a href="#benefits" class="hover:text-purple-400 transition-colors duration-300">Benefits</a>
    <a href="#faq" class="hover:text-purple-400 transition-colors duration-300">FAQ</a>
    <a href="#contact" class="hover:text-purple-400 transition-colors duration-300">Contact</a>
</div>
```

To update these links:
1. The `href="#section-name"` corresponds to section IDs in the HTML
2. Ensure section IDs match exactly (case-sensitive)
3. To link to external pages, replace the `#section-name` with the full URL

### Call-to-Action Buttons
There are two main CTA buttons that currently point to "https://shazapp.com/":

```html
<a href="https://shazapp.com/" class="inline-block bg-gradient-to-r from-purple-500 to-pink-500 px-8 py-4 rounded-full text-lg font-semibold hover:scale-105 transform transition-all duration-300 shadow-lg hover:shadow-purple-500/25">
    Get Started Now
</a>
```

To update:
1. Replace the `href` value with your desired URL
2. Update the button text between the opening and closing tags
3. Maintain the existing classes for consistent styling

## Adding Privacy and Terms Pages

### Footer Legal Links
Locate the legal section in the footer:

```html
<div>
    <h4 class="text-lg font-semibold mb-6">Legal</h4>
    <ul class="space-y-4 text-gray-400">
        <li><a href="#" class="hover:text-purple-400 transition-colors duration-300">Privacy Policy</a></li>
        <li><a href="#" class="hover:text-purple-400 transition-colors duration-300">Terms of Service</a></li>
    </ul>
</div>
```

To link to privacy and terms pages:
1. Create `privacy.html` and `terms.html` in your project directory
2. Update the href attributes:
```html
<li><a href="privacy.html" class="hover:text-purple-400 transition-colors duration-300">Privacy Policy</a></li>
<li><a href="terms.html" class="hover:text-purple-400 transition-colors duration-300">Terms of Service</a></li>
```

## Troubleshooting

Common issues and solutions:

1. **Broken Internal Links**
   - Ensure section IDs match the href values exactly
   - Check for extra spaces in IDs
   - Verify that the section ID exists in the HTML

2. **Responsive Design Issues**
   - Don't remove `md:` or `lg:` prefixes from classes
   - Keep the existing grid structure (`grid-cols-1 md:grid-cols-2 lg:grid-cols-3`)
   - Maintain the container class on parent elements

3. **Gradient Text Not Showing**
   - Ensure these classes remain together:
     - `bg-gradient-to-r`
     - `from-purple-400`
     - `to-pink-400`
     - `bg-clip-text`
     - `text-transparent`

4. **Social Media Icons Not Displaying**
   - Verify SVG paths are complete
   - Keep the `currentColor` fill attribute
   - Maintain the `h-6 w-6` classes for proper sizing

Remember to test all changes across different screen sizes using your browser's developer tools (F12 or right-click → Inspect).