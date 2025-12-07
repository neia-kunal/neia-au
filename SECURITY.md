# Security Policy

## Reporting a Vulnerability

We take the security of our website seriously. If you discover a security vulnerability, please report it responsibly.

### How to Report

- **Email**: contact@m.neia.au
- **Response Time**: We aim to acknowledge reports within 48 hours
- **Disclosure**: Please allow us time to address the issue before public disclosure

### What to Include

When reporting a vulnerability, please include:
- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact
- Any suggested remediation

## Supported Versions

This website is continuously updated. Security fixes are applied to the latest version.

## Security Best Practices

This GitHub Pages website implements the following security measures:

### Current Protections

1. **HTTPS Enforcement**: All traffic is served over HTTPS
2. **Custom Domain Configuration**: Proper DNS configuration with CNAME
3. **Vulnerability Disclosure**: security.txt file for responsible disclosure
4. **Regular Updates**: Dependencies and content are regularly reviewed

### GitHub Pages Limitations

GitHub Pages has some inherent limitations:

1. **Custom HTTP Headers**: Cannot set custom security headers like CSP, HSTS, X-Frame-Options, etc.
2. **Server-Side Processing**: No server-side code execution or processing

### Recommended Security Practices

For visitors to this website:

1. **Verify HTTPS**: Always ensure you're visiting https://neia.au
2. **Keep Browsers Updated**: Use the latest version of your web browser
3. **Report Issues**: If you notice suspicious content or behavior, please report it

### Content Security

- External resources (fonts, images) are loaded from trusted sources only
- All external links use `rel="noopener noreferrer"` for security
- No user-generated content is hosted on this site
- No sensitive data collection or processing occurs

## Known Limitations

Due to GitHub Pages infrastructure:

1. **No Custom Headers**: We cannot set Content-Security-Policy, X-Frame-Options, or other security headers via HTTP responses
2. **Limited CSP**: Content Security Policy can only be partially implemented via meta tags
3. **No HSTS Preload**: Cannot set custom HSTS headers for preload lists

## Security Updates

This document will be updated as our security posture evolves. Last updated: December 2025

## Acknowledgments

We appreciate the security research community's efforts to keep the web safe. Responsible disclosure helps protect all users.

## Additional Resources

- [GitHub Pages Security Best Practices](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
- [OWASP Security Guidelines](https://owasp.org/)
- [RFC 9116: security.txt](https://www.rfc-editor.org/rfc/rfc9116.html)
