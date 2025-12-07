# Security Recommendations for GitHub Pages Website

This document provides additional security recommendations for implementing website content on this GitHub Pages repository.

## Implemented Security Measures

### Current Branch Security ✅

1. **CNAME Configuration**
   - Fixed: Proper newline terminator added
   - Custom domain: neia.au

2. **Vulnerability Disclosure**
   - RFC 9116 compliant security.txt file
   - Clear contact information
   - Annual expiration for review

3. **Security Documentation**
   - Comprehensive SECURITY.md policy
   - Documented limitations and best practices
   - Clear reporting procedures

4. **Repository Security**
   - .gitignore prevents sensitive file commits
   - No secrets or credentials in repository

## Recommended Enhancements for Website Content

When adding HTML/CSS/JS content to this repository, implement the following security measures:

### 1. Content Security Policy (CSP)

Since GitHub Pages doesn't support custom HTTP headers, implement CSP via meta tag in HTML:

```html
<head>
    <meta http-equiv="Content-Security-Policy" 
          content="default-src 'self'; 
                   script-src 'self' https://trusted-cdn.com; 
                   style-src 'self' 'unsafe-inline' https://fonts.googleapis.com; 
                   font-src 'self' https://fonts.gstatic.com; 
                   img-src 'self' data: https:; 
                   connect-src 'self'; 
                   frame-ancestors 'none'; 
                   base-uri 'self'; 
                   form-action 'self';">
</head>
```

**Note**: Not all CSP directives work in meta tags. `frame-ancestors`, `report-uri`, and `sandbox` require HTTP headers.

### 2. Subresource Integrity (SRI)

Add SRI hashes for all external resources (fonts, CDN scripts, stylesheets):

```html
<!-- Example with SRI -->
<link href="https://fonts.googleapis.com/css2?family=Delius&display=swap" 
      rel="stylesheet"
      integrity="sha384-HASH-VALUE-HERE"
      crossorigin="anonymous">

<script src="https://cdn.example.com/library.js"
        integrity="sha384-HASH-VALUE-HERE"
        crossorigin="anonymous"></script>
```

Generate SRI hashes: https://www.srihash.org/

### 3. External Link Security

All external links should include security attributes:

```html
<a href="https://external-site.com" 
   target="_blank" 
   rel="noopener noreferrer">
    External Link
</a>
```

- `rel="noopener"`: Prevents window.opener access
- `rel="noreferrer"`: Prevents referrer information leakage

### 4. Form Security

If implementing forms:

```html
<form action="/submit" method="POST">
    <!-- Use HTTPS endpoints only -->
    <!-- Implement CSRF protection if processing server-side -->
    <!-- Validate all input client and server-side -->
</form>
```

### 5. Input Validation

If collecting any user input:

```javascript
// Example: Sanitize input to prevent XSS
function sanitizeInput(input) {
    const div = document.createElement('div');
    div.textContent = input;
    return div.innerHTML;
}
```

### 6. Third-Party Resources

Minimize external dependencies:
- Only load from trusted CDNs
- Use SRI for all external resources
- Prefer self-hosting when possible
- Regular dependency audits

### 7. HTTPS Configuration

GitHub Pages Settings:
1. Repository → Settings → Pages
2. **✓ Enforce HTTPS** (checked)
3. Custom domain properly configured
4. DNS records pointing to GitHub Pages IPs:
   - 185.199.108.153
   - 185.199.109.153
   - 185.199.110.153
   - 185.199.111.153

### 8. Monitoring and Maintenance

Regular security reviews:
- Monthly: Review security.txt expiration
- Quarterly: Audit external dependencies
- Annually: Review and update security policy
- Continuous: Monitor for new vulnerabilities

## GitHub Pages Limitations

Be aware of these inherent limitations:

### Cannot Implement via GitHub Pages:
1. **Custom HTTP Response Headers**
   - No HSTS (HTTP Strict Transport Security)
   - No X-Frame-Options
   - No X-Content-Type-Options
   - No Referrer-Policy
   - No Permissions-Policy

2. **Server-Side Security**
   - No server-side validation
   - No rate limiting
   - No WAF (Web Application Firewall)
   - No DDoS protection

### Workarounds:

**Option 1: Use Cloudflare (Free)**
- Add Cloudflare in front of GitHub Pages
- Configure security headers via Cloudflare
- Enable Cloudflare's security features
- Keep GitHub Pages as origin

**Option 2: Migrate to Cloudflare Pages or Netlify**
- Full control over HTTP headers
- Built-in security features
- Form handling with security
- Better DDoS protection

## Security Checklist for New Content

Before deploying new HTML/CSS/JS content:

- [ ] CSP meta tag implemented
- [ ] All external resources use SRI hashes
- [ ] External links have `rel="noopener noreferrer"`
- [ ] No inline JavaScript (or CSP allows 'unsafe-inline')
- [ ] No hardcoded credentials or API keys
- [ ] No sensitive data in repository
- [ ] HTTPS enforcement enabled in GitHub Pages settings
- [ ] security.txt file expiration checked
- [ ] All dependencies up-to-date
- [ ] No console.log() with sensitive data in production
- [ ] Error messages don't expose sensitive information

## Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Content Security Policy Reference](https://content-security-policy.com/)
- [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity)
- [GitHub Pages Security](https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https)
- [RFC 9116: security.txt](https://www.rfc-editor.org/rfc/rfc9116.html)
- [Web Security Guidelines](https://infosec.mozilla.org/guidelines/web_security)

## Contact

For security concerns or questions:
- Email: contact@m.neia.au
- security.txt: https://neia.au/.well-known/security.txt

---

**Last Updated**: December 2025
**Next Review**: December 2026
