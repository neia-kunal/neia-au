# Neia Website

Official website for Neia - Using AI to make life better, not just faster.

## Security

This repository follows security best practices for GitHub Pages websites. See [SECURITY.md](SECURITY.md) for our security policy and vulnerability disclosure process.

### Security Configuration

To ensure the website is served securely:

1. **Enable HTTPS Enforcement**
   - Go to Repository Settings → Pages
   - Check "Enforce HTTPS"
   - This ensures all traffic is served over HTTPS

2. **Custom Domain Configuration**
   - DNS A records point to GitHub Pages IPs
   - CNAME record configured for www subdomain
   - Custom domain verified in repository settings

3. **Security Headers**
   - Note: GitHub Pages doesn't support custom HTTP headers
   - For advanced security headers, consider using a CDN like Cloudflare

4. **Vulnerability Disclosure**
   - security.txt file available at `/.well-known/security.txt`
   - Contact: contact@m.neia.au

## Repository Structure

```
.
├── .well-known/
│   └── security.txt      # RFC 9116 security contact info
├── CNAME                 # Custom domain configuration
├── SECURITY.md           # Security policy and practices
├── .gitignore           # Git ignore patterns
└── README.md            # This file
```

## Deployment

This site is automatically deployed via GitHub Pages when changes are pushed to the main branch.

### Prerequisites

- GitHub Pages enabled in repository settings
- Custom domain configured (neia.au)
- HTTPS enforcement enabled

## Contributing

Please review [SECURITY.md](SECURITY.md) before contributing. Report security issues via email to contact@m.neia.au.

## License

© 2025 Neia. All rights reserved.
