# Deployment Guide

## Deploying to GitHub Pages

This application is designed to work perfectly with GitHub Pages since it's a single HTML file with no build process.

### Initial Setup

1. **Create a GitHub repository**
   ```bash
   # If not already initialized
   git init
   git add .
   git commit -m "Initial commit: Power Anomaly Detector"
   ```

2. **Push to GitHub**
   ```bash
   # Replace YOUR_USERNAME with your GitHub username
   git remote add origin https://github.com/YOUR_USERNAME/poweranomaly.git
   git branch -M main
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click "Settings"
   - Scroll to "Pages" in the left sidebar
   - Under "Source", select "main" branch
   - Select "/ (root)" as the folder
   - Click "Save"

4. **Wait for deployment**
   - GitHub will build and deploy your site (takes 1-2 minutes)
   - Your site will be available at: `https://YOUR_USERNAME.github.io/poweranomaly/`

### Custom Domain

This repository is configured to use **gridsense.us** as the custom domain.

**DNS Configuration (Namecheap):**

1. **Add CNAME Record**
   - Host: `@` (or leave blank for root domain)
   - Value: `YOUR_USERNAME.github.io.` (note the trailing dot)
   - TTL: Automatic

2. **Optional: Add www subdomain**
   - Host: `www`
   - Value: `YOUR_USERNAME.github.io.`
   - TTL: Automatic

3. **GitHub Settings**
   - The CNAME file is already in the repository with `gridsense.us`
   - Go to Settings → Pages
   - Verify custom domain shows `gridsense.us`
   - Check "Enforce HTTPS" (may take a few minutes after DNS propagates)

**DNS Propagation:**
- DNS changes can take up to 24-48 hours to propagate
- Check status: `dig gridsense.us` or use dnschecker.org
- GitHub will automatically provision SSL certificate once DNS is verified

### Updates

To update the live site:

```bash
# Make your changes to index.html
git add index.html
git commit -m "Description of changes"
git push
```

GitHub Pages will automatically redeploy within 1-2 minutes.

### Testing Locally

Before pushing changes, test locally:

```bash
# Option 1: Python
python3 -m http.server 8000

# Option 2: Just open the file
open index.html

# Visit: http://localhost:8000
```

## Repository Structure

```
poweranomaly/
├── index.html           # Main application (served by GitHub Pages)
├── cases/              # User-submitted anonymized data
│   └── README.md
├── CONTRIBUTING.md     # Contribution guidelines
├── DEPLOYMENT.md       # This file
├── README.md           # Project documentation
├── LICENSE             # MIT License
├── .gitignore         # Git ignore rules
└── CLAUDE.md          # Claude Code documentation
```

## Important Notes

### Privacy & Security
- The app runs entirely client-side
- No server-side processing needed
- No API keys or secrets to configure
- User data never leaves their browser

### Performance
- Single HTML file (~100KB)
- Chart.js loaded from CDN
- Should load in <1 second on decent connections
- Works offline once loaded

### Browser Compatibility
- Chrome 90+
- Firefox 88+
- Safari 14+
- Edge 90+

No polyfills needed for modern browsers.

## Troubleshooting

### Site not updating
1. Check GitHub Actions tab for build status
2. Hard refresh browser (Cmd+Shift+R / Ctrl+F5)
3. Clear browser cache
4. Wait 5 minutes and try again

### 404 Error
1. Verify GitHub Pages is enabled in settings
2. Check that you pushed to the correct branch (main)
3. Ensure index.html is in the root directory

### Custom domain not working
1. Verify DNS propagation (can take up to 24 hours)
2. Check CNAME file is in repository root
3. Ensure DNS points to YOUR_USERNAME.github.io (not the repo name)
4. Enable "Enforce HTTPS" in GitHub settings

## Monitoring

### GitHub Insights
Track usage via:
- Repository Insights → Traffic
- Shows visitors, views, clones
- Updated daily

### User Feedback
Encourage users to:
- Open issues for bugs
- Submit PRs with anonymized data
- Star the repository if they find it useful

## Maintenance

### Regular Tasks
- Monitor issues for bug reports
- Review PRs with submitted data
- Update CLAUDE.md for any architectural changes
- Test with new browser versions

### Backups
GitHub serves as your backup, but consider:
- Exporting submitted cases periodically
- Backing up issues/discussions
- Documenting major version changes

## Legal Compliance

### DMCA/Takedown Requests
If you receive a takedown notice:
1. Consult legal counsel
2. Document the request
3. Consider removing specific cases if needed
4. The tool itself is legal - it's just math and visualization

### Privacy Compliance
- No cookies used
- No user tracking
- No data collection
- GDPR/CCPA compliant by design (no data leaves browser)

## Success Metrics

Track impact via:
- GitHub stars/forks
- Issues reporting billing errors
- Submitted cases in `cases/` directory
- Media mentions or regulatory references

---

Ready to deploy? Just push to GitHub and enable Pages!
