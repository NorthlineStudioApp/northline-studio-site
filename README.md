# Northline Studio Website

Simple static website for Northline Studio LLC.

## Local Development

Open `index.html` in a browser, or use a local server:

```bash
# Python 3
python -m http.server 8000

# Then visit http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a GitHub account (if needed)
2. Create a new repository named `northlinestudio.github.io` (or any name)
3. Push this code to the repository
4. Go to Settings > Pages > Source: Deploy from branch (main)
5. Site will be live at `https://yourusername.github.io/reponame/`

## Add Custom Domain (when ready)

1. Buy domain (e.g., northlinestudio.app)
2. In GitHub repo Settings > Pages > Custom domain: enter your domain
3. Add DNS records at your domain registrar:
   - Type: CNAME
   - Name: www (or @)
   - Value: yourusername.github.io
4. Wait for DNS propagation (up to 24 hours)
5. Enable "Enforce HTTPS" in GitHub Pages settings

## Files

- `index.html` - Home page
- `privacy-policy.html` - Privacy policy (required for App Store)
- `terms.html` - Terms of service
- `support.html` - Support/contact page
- `styles.css` - All styles
- `favicon.svg` - Site icon

## Update Checklist

When domain is ready:
- [ ] Update email from `support@northlinestudio.app` to actual email
- [ ] Set up email forwarding or mailbox
- [ ] Update App Store connect with real URLs
