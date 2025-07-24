# Google-Crawl-My-Repo

## Purpose
This project sets up a dummy website using GitHub Pages, designed to be crawled by Google. It includes:
- A link to this GitHub repository
- A `robots.txt` that allows all crawlers
- A `sitemap.xml` for easier discovery
- Support for Google Search Console site verification

## How to Verify Ownership with Google Search Console
1. Go to [Google Search Console](https://search.google.com/search-console/welcome).
2. Add your GitHub Pages site (e.g., `https://<your-username>.github.io/Google-Crawl-My-Repo/`) as a new property.
3. Choose the **HTML file** verification method.
4. Download the HTML file provided by Google (it will be named something like `googleXXXXXXXXXXXX.html`).
5. Replace the contents of `public/google-site-verification.html` in this repo with the contents of the file you downloaded.
6. Commit and push your changes to the `main` branch. The GitHub Actions workflow will redeploy the site.
7. Click "Verify" in Google Search Console.

## How it Works
- The site is deployed automatically to GitHub Pages on every push to `main`.
- The `robots.txt` allows all bots and points to a `sitemap.xml`.
- The homepage contains a link back to this repository.
- Once Google crawls the GitHub Pages site, it will find the link to this repo and (eventually) crawl the repo as well.

## Files of Interest
- `public/index.html`: Main page with a link to this repo
- `public/robots.txt`: Allows all bots and points to the sitemap
- `public/sitemap.xml`: Sitemap for the site
- `public/google-site-verification.html`: Place your Google verification HTML here
- `.github/workflows/deploy.yml`: GitHub Actions workflow for deployment

---
*Happy crawling!*
