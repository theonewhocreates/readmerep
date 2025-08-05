# Static Portfolio - Netlify Deployment Guide

This guide explains how to deploy your static HTML/CSS/JavaScript portfolio to Netlify.

## Project Structure

```
static-portfolio/
├── index.html          # Homepage
├── projects.html       # Projects page
├── styles.css          # All CSS styles
├── script.js           # JavaScript functionality
├── netlify.toml        # Netlify configuration
├── _redirects          # URL redirects
└── DEPLOYMENT_GUIDE.md # This file
```

## Prerequisites

- A Netlify account (free at netlify.com)
- Your project files ready for deployment

## Deployment Options

### Option 1: Drag and Drop Deployment (Easiest)

1. **Prepare your files:**
   - Ensure all files are in the project directory
   - No build process required for static HTML/CSS/JS

2. **Deploy to Netlify:**
   - Go to [netlify.com](https://netlify.com) and log in
   - Click "Add new site" → "Deploy manually"
   - Drag and drop the entire `static-portfolio` folder to the deployment area
   - Your site will be deployed with a random URL

### Option 2: Git-based Deployment (Recommended)

1. **Initialize Git repository:**
   ```bash
   cd static-portfolio
   git init
   git add .
   git commit -m "Initial commit: Static portfolio"
   ```

2. **Push to GitHub:**
   ```bash
   git remote add origin YOUR_GITHUB_REPO_URL
   git push -u origin main
   ```

3. **Connect to Netlify:**
   - Go to [netlify.com](https://netlify.com) and log in
   - Click "Add new site" → "Import an existing project"
   - Choose "GitHub" and authorize Netlify
   - Select your repository

4. **Configure build settings:**
   - Build command: (leave empty)
   - Publish directory: (leave empty or set to ".")
   - No build process needed for static files

5. **Deploy:**
   - Click "Deploy site"
   - Your site will be live immediately
   - Future pushes to main branch will trigger automatic deployments

## Configuration Files

### netlify.toml
- Configures redirects for clean URLs
- Sets security headers
- Optimizes caching for static assets
- No build command needed

### _redirects
- Backup configuration for URL redirects
- Handles clean URLs (/projects instead of /projects.html)
- 404 fallback to homepage

## Features Included

### Responsive Design
- Mobile-first approach
- Breakpoints for tablet and desktop
- Touch-friendly navigation

### Interactive Elements
- Mobile menu toggle
- Project category filtering
- Smooth scrolling
- Hover effects and animations

### Performance Optimizations
- Optimized CSS with custom properties
- Efficient JavaScript with event delegation
- Lazy loading support
- Proper caching headers

### Accessibility
- Semantic HTML structure
- Keyboard navigation support
- Screen reader friendly
- High contrast ratios

## Custom Domain (Optional)

1. In your Netlify site dashboard, go to "Domain settings"
2. Click "Add custom domain"
3. Follow the instructions to configure your DNS
4. SSL certificate will be automatically provided

## Environment Variables

This static site doesn't require environment variables, but if you add dynamic features:
1. Go to Site settings → Environment variables
2. Add your variables
3. Redeploy your site

## Troubleshooting

### Common Issues:

1. **CSS not loading:** Check file paths are relative and correct
2. **JavaScript not working:** Check browser console for errors
3. **Images not displaying:** Ensure image paths are correct
4. **Mobile menu not working:** Verify JavaScript is loading properly

### Testing Locally:

You can test the site locally using any HTTP server:

```bash
# Using Python 3
python -m http.server 8000

# Using Node.js (if you have http-server installed)
npx http-server

# Using PHP
php -S localhost:8000
```

Then visit `http://localhost:8000` in your browser.

## Performance Tips

1. **Optimize images:** Use WebP format when possible
2. **Minify CSS/JS:** Use online tools or build processes
3. **Enable compression:** Netlify handles this automatically
4. **Monitor performance:** Use Lighthouse or PageSpeed Insights

## SEO Optimization

The site includes basic SEO elements:
- Semantic HTML structure
- Meta viewport tag
- Descriptive page titles
- Clean URL structure

For better SEO, consider adding:
- Meta descriptions
- Open Graph tags
- Structured data
- XML sitemap

## Browser Support

This portfolio supports:
- Chrome 60+
- Firefox 60+
- Safari 12+
- Edge 79+

Features used:
- CSS Grid and Flexbox
- CSS Custom Properties
- ES6 JavaScript
- Intersection Observer API

## Updates and Maintenance

To update your portfolio:
1. Edit the HTML, CSS, or JavaScript files
2. Test locally
3. Commit and push to GitHub (for Git-based deployment)
4. Or drag and drop updated files (for manual deployment)

## Support

For deployment issues:
- Check Netlify's build logs in your dashboard
- Review the [Netlify documentation](https://docs.netlify.com)
- Ensure your local files work correctly before deployment

