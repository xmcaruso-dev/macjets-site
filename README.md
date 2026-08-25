# Mac Jets — Deployment Guide

## Files in this folder
- `index.html` — The full website (single file, all CSS + JS inline)
- `robots.txt` — Tells search engines they can crawl the site
- `sitemap.xml` — Helps search engines find all pages

## Deploy to Vercel (10 minutes)

### Option A: Drag & Drop (easiest)

1. Go to https://vercel.com and sign in
2. Click "Add New..." → "Project"
3. Click "Browse all templates" → scroll to bottom, click "Continue with GitHub" OR look for "Deploy a static site"
4. Actually, easiest way: go to https://vercel.com/new
5. Look for "Drop folder here" or use the upload button
6. Drag this entire `macjets` folder
7. Project name: `flymacjets` or `macjets` (whatever)
8. Click "Deploy"
9. Wait ~30 seconds — site will be live at something like `flymacjets.vercel.app`

### Option B: Via Vercel CLI (faster if you do this often)

```
npm i -g vercel
cd macjets
vercel
```

Follow the prompts. Same result.

## Connect your domain (flymacjets.com)

1. In Vercel, open your deployed project
2. Click "Settings" → "Domains"
3. Add `flymacjets.com` and `www.flymacjets.com`
4. Vercel will show you DNS records to add at Namecheap

5. Go to Namecheap → "Domain List" → click "Manage" next to flymacjets.com
6. Click "Advanced DNS" tab
7. Delete any default records (the parking page CNAME)
8. Add records Vercel told you to add:
   - Usually an A record pointing to `76.76.21.21`
   - Usually a CNAME for `www` pointing to `cname.vercel-dns.com`

9. Wait 5-30 min for DNS to propagate
10. Vercel auto-issues a free SSL cert
11. flymacjets.com is live

## Test the form

Once deployed:
1. Visit your site
2. Fill out the quote form with test data
3. Submit
4. Check matt@dashhaviation.com inbox
5. First Formspree submission will require email verification

## Future updates

To update the site:
- Edit `index.html` locally
- Drag the folder back to Vercel (it'll redeploy)
OR
- Set up GitHub integration so changes auto-deploy

## Notes
- Site is mobile-responsive
- Uses Google Fonts (Fraunces + Inter)
- Form submissions go to Formspree → matt@dashhaviation.com
- Canonical host is https://www.flymacjets.com; quote form posts to https://formspree.io/f/xdaboyel
