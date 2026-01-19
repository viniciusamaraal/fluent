# Fluent Bot Documentation Site

This folder contains the GitHub Pages website for Fluent Bot.

## Files

- `index.html` - Landing page with app installation, features, and pricing
- `privacy.html` - Privacy policy
- `support.html` - Support and FAQ page

## Setting Up GitHub Pages

1. **Push the docs folder to GitHub**
   ```bash
   git add docs/
   git commit -m "Add GitHub Pages site for Slack app distribution"
   git push
   ```

2. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click `Settings` > `Pages`
   - Under "Source", select `Deploy from a branch`
   - Select branch: `master` (or `main`)
   - Select folder: `/docs`
   - Click `Save`

3. **Wait for deployment**
   - GitHub Pages will build and deploy your site
   - It will be available at: `https://<your-username>.github.io/<repo-name>/`
   - Example: `https://vamaral.github.io/fluent-bot/`

## Required Updates Before Submitting to Slack

### 1. Update OAuth URLs in index.html

Replace `YOUR_CLIENT_ID` with your actual Slack app client ID in the following lines:

**Line ~77:**
```html
<a href="https://slack.com/oauth/v2/authorize?client_id=YOUR_CLIENT_ID&scope=commands,chat:write&user_scope=" class="cta-button">
```

**Line ~179:**
```html
<a href="https://slack.com/oauth/v2/authorize?client_id=YOUR_CLIENT_ID&scope=commands,chat:write&user_scope=" class="cta-button">
```

To find your Client ID:
- Go to https://api.slack.com/apps
- Select your app
- Go to `Basic Information`
- Copy the `Client ID`

### 2. Update Contact Email (Optional)

If you want to use a different support email, update:
- `privacy.html` - Search for `support@fluent-bot.com`
- `support.html` - Search for `support@fluent-bot.com`

### 3. Update GitHub Links (Optional)

Update the GitHub repository link if your repo URL is different:
- `index.html` - Line ~187
- `privacy.html` - Line ~187
- `support.html` - Lines ~287, 293

## URLs to Provide to Slack App Directory

Once GitHub Pages is live, use these URLs when submitting your app:

1. **Installation Landing Page URL:**
   ```
   https://<your-username>.github.io/<repo-name>/
   ```

2. **Privacy Policy URL:**
   ```
   https://<your-username>.github.io/<repo-name>/privacy.html
   ```

3. **App Support URL:**
   ```
   https://<your-username>.github.io/<repo-name>/support.html
   ```

## Current Version

The documentation currently reflects the **free-only version** of Fluent Bot. References to paid subscriptions, BYOK, and Stripe have been removed. When you implement paid tiers, you'll need to update:

- `index.html` - Add pricing tiers section back
- `privacy.html` - Add payment and API key sections
- `support.html` - Add subscription and BYOK FAQs

## Customization

The pages use inline CSS for simplicity. You can customize:

- **Colors:** Update the gradient colors (`#667eea`, `#764ba2`, `#4A154B`)
- **Content:** Modify text, features, pricing information
- **Layout:** Adjust grid layouts, spacing, and responsive breakpoints
- **Branding:** Add your logo by replacing the emoji (🌍) in the header

## Testing Locally

To test the pages locally before pushing:

```bash
# Using Python 3
cd docs
python -m http.server 8000

# Visit http://localhost:8000 in your browser
```

## Notes

- The pages are fully static HTML/CSS with no JavaScript or dependencies
- Mobile responsive design included
- Professional styling matching Slack's design language
- GDPR/CCPA compliance statements included in privacy policy
- All links use relative paths for easy deployment
