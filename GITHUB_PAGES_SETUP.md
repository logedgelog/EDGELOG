# GitHub Pages Setup Guide

## Enable GitHub Pages (2 minutes)

### Step 1: Go to Repository Settings
1. Go to your GitHub repository
2. Click **Settings** (top right)
3. Click **Pages** (left sidebar)

### Step 2: Configure Pages
1. **Source:** Select "Deploy from a branch"
2. **Branch:** Select "main"
3. **Folder:** Select "/ (root)"
4. Click **Save**

GitHub will display your site URL:
```
https://yourusername.github.io/edgelog
```

### Step 3: Wait for Deployment
- First deployment takes ~1 minute
- You'll see a checkmark when ready
- Visit your URL to confirm it's live

## Using Your Site

### Access Points
- **Home:** `https://yourusername.github.io/edgelog/`
- **Login:** `https://yourusername.github.io/edgelog/login.html`
- **Journal:** `https://yourusername.github.io/edgelog/EdgeLog_v61.html`
- **Admin:** `https://yourusername.github.io/edgelog/admin.html`

### Share the Link
- Share login page link with users: `https://yourusername.github.io/edgelog/login.html`
- They'll be redirected after login
- All data stored in Firestore (not on GitHub)

## Deploy Changes

Every time you push to main, GitHub Pages auto-updates:

```bash
# Make changes
git add .
git commit -m "feat: describe change"
git push origin main

# Wait ~30 seconds for GitHub Pages to deploy
# Your changes are live!
```

## Custom Domain (Optional)

### Add Custom Domain
1. Go to Settings → Pages
2. Under "Custom domain" add your domain: `edgelog.yourdomain.com`
3. Update DNS records at your registrar
4. DNS propagation takes 5-48 hours
5. GitHub auto-provisions HTTPS certificate

### DNS Records Needed
- **CNAME:** `edgelog.yourdomain.com` → `yourusername.github.io`

Or A records:
- `185.199.108.153`
- `185.199.109.153`
- `185.199.110.153`
- `185.199.111.153`

## Troubleshooting

### Site Not Loading?
- Check Settings → Pages shows your URL
- Verify branch is "main"
- Check folder is "/" (root)
- Refresh page (Ctrl+F5)

### Changes Not Showing?
- Confirm push was successful: `git push origin main`
- Wait 30 seconds for GitHub to deploy
- Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
- Check for errors in browser console (F12)

### Firebase Not Working?
- Check firebase-config.js has correct credentials
- Verify Firestore database is created
- Check Authentication providers are enabled
- See console errors (F12)

## Performance Notes

✅ **Fast:** GitHub Pages serves from edge locations worldwide
✅ **HTTPS:** Automatic SSL/TLS certificate
✅ **Reliable:** 99.99% uptime SLA
✅ **No Cost:** Free tier for public repos

## GitHub Pages vs Other Hosting

| Feature | GitHub Pages | Netlify |
|---------|--------------|---------|
| Cost | Free | Free |
| Setup | 2 minutes | 2 minutes |
| Auto-deploy | Yes | Yes |
| Custom domain | Yes | Yes |
| HTTPS | Yes | Yes |
| Edge CDN | Yes | Yes |
| Build step | No | Optional |

Both work great! GitHub Pages is simpler for static sites.

## Security Considerations

✅ **GitHub doesn't see credentials** – Firebase handles auth
✅ **No API keys exposed** – Config is client-side only (public)
✅ **HTTPS everywhere** – Automatic SSL/TLS
✅ **Firestore rules** – Control access to user data

⚠️ **Important:** Don't commit real Firebase credentials if sharing publicly
- firebase-config.js is visible to everyone
- Users should have their own Firebase project
- Or: Use environment variables + GitHub Secrets

## Next Steps

1. ✅ Enable GitHub Pages (done!)
2. Update firebase-config.js with your credentials
3. Test login: `https://yourusername.github.io/edgelog/login.html`
4. Share the link with traders
5. Monitor Firestore usage in Firebase Console

---

**Questions?** See README.md or GitHub Pages docs at https://pages.github.com
