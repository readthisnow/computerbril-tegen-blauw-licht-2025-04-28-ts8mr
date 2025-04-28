# Landing Page Maintenance Guide
## ComputerBril.org

This guide provides detailed instructions for maintaining and customizing the ComputerBril.org landing page.

## Table of Contents
1. [Updating Text and Tailwind CSS Classes](#updating-text-and-tailwind-css-classes)
2. [Fixing Broken Links](#fixing-broken-links)
3. [Linking Privacy and Terms Pages](#linking-privacy-and-terms-pages)
4. [Troubleshooting](#troubleshooting)

## Updating Text and Tailwind CSS Classes

### Header Section
The header contains the logo and navigation menu. To update:

1. **Logo Text:**
```html
<!-- Find this line in the header -->
<a href="/" class="text-2xl font-bold bg-gradient-to-r from-blue-600 to-indigo-600 bg-clip-text text-transparent">ComputerBril.org</a>
```
- Replace `ComputerBril.org` with your desired text
- The gradient effect is created by `bg-gradient-to-r from-blue-600 to-indigo-600`

2. **Navigation Links:**
```html
<div class="hidden md:flex space-x-8">
    <a href="#features" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Voordelen</a>
    <a href="#benefits" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">Waarom Kiezen</a>
    <a href="#faq" class="text-gray-600 hover:text-blue-600 transition-colors duration-300">FAQ</a>
</div>
```
- Update link text between `<a>` tags
- `hidden md:flex` means the menu is hidden on mobile and visible on medium screens
- `space-x-8` adds horizontal spacing between items

### Hero Section
The main banner section contains:

```html
<h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight mb-8">
    Computerbril Tegen Blauw Licht
    <span class="block text-blue-600 mt-4">Nu 20% Korting!</span>
</h1>
```
- Text sizes increase with screen size (`text-4xl` → `text-5xl` → `text-6xl`)
- `leading-tight` controls line height
- `mb-8` adds bottom margin

## Fixing Broken Links

### Current Link Inventory
1. Navigation Links:
```html
<a href="#features">Voordelen</a>
<a href="#benefits">Waarom Kiezen</a>
<a href="#faq">FAQ</a>
```
- These are internal anchor links (scroll to sections)
- Keep the `#` symbol for internal navigation

2. Call-to-Action Links:
```html
<a href="https://computerbril.org/winkel" class="inline-flex items-center...">
```
- Replace `computerbril.org/winkel` with your actual shop URL
- Maintain the `https://` prefix for external links

### Updating Links Step-by-Step
1. Identify the link to update
2. Replace the `href` value:
   - Internal links: Use `#section-id`
   - External links: Use full URL with `https://`
3. Test the link by clicking it

## Linking Privacy and Terms Pages

### Adding Footer Links
Add these links to the footer section:

```html
<div class="border-t border-gray-800 mt-12 pt-8 text-sm text-gray-400">
    <p>&copy; 2024 ComputerBril.org. Alle rechten voorbehouden.</p>
    <!-- Add these lines below the copyright notice -->
    <div class="mt-4 space-x-4">
        <a href="/privacy.html" class="hover:text-blue-400 transition-colors duration-300">Privacy Policy</a>
        <a href="/terms.html" class="hover:text-blue-400 transition-colors duration-300">Terms of Service</a>
    </div>
</div>
```

### Style Consistency
- Use `text-gray-400` for default state
- Add `hover:text-blue-400` for hover effect
- Include `transition-colors duration-300` for smooth color changes

## Troubleshooting

### Common Issues and Solutions

1. **Broken Responsive Design**
   - Check for missing screen size prefixes (`sm:`, `md:`, `lg:`)
   - Verify Tailwind CSS is properly loaded
   - Example fix:
     ```html
     <!-- Incorrect -->
     <div class="text-xl">
     <!-- Correct -->
     <div class="text-lg md:text-xl lg:text-2xl">
     ```

2. **Links Not Working**
   - Verify href attributes start with `/`, `#`, or `https://`
   - Check for typos in section IDs
   - Example:
     ```html
     <!-- Incorrect -->
     <a href="features">
     <!-- Correct -->
     <a href="#features">
     ```

3. **Styling Issues**
   - Maintain the class order: layout → spacing → colors → effects
   - Example:
     ```html
     <div class="flex items-center px-4 text-blue-600 hover:bg-blue-50">
     ```

### Need Help?
If you encounter issues:
1. Check the browser console for errors
2. Verify all files are in the correct directory
3. Ensure Tailwind CSS and Alpine.js are properly loaded
4. Contact support at the email provided in the footer

Remember to always test changes across different screen sizes and browsers before deploying to production.