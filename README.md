# Neia Australia Website

A GitHub Pages website for Neia Australia.

## Local Development

To view the site locally, you can use any simple HTTP server:

```bash
# Using Python
python -m http.server 8000

# Or using Node.js
npx serve
```

Then open `http://localhost:8000` in your browser.

## GitHub Pages Deployment

This site is configured to deploy automatically via GitHub Pages. To enable:

1. Go to your repository Settings
2. Navigate to "Pages" in the sidebar
3. Under "Source", select your branch (e.g., `main`)
4. Click Save

The site will be available at: `https://neia-kunal.github.io/neia-au/`

## Adding Content

Add your content to the `index.html` file in the appropriate sections. The site supports:
- HTML content with proper semantic structure
- Responsive design for mobile and desktop
- Smooth scrolling navigation

## File Structure

```
neia-au/
├── index.html      # Main HTML page
├── css/
│   └── style.css   # Stylesheet
├── _config.yml     # Jekyll configuration
└── README.md       # This file
```
