
# Google-Crawl-My-Repo

This project sets up a dummy website using GitHub Pages, designed to be crawled by Google.


## Structure
- All site files are in the `public` folder.
- The workflow copies `README.md` into `public/README.md` for display on the homepage.
- The homepage fetches and renders the README using JavaScript and the Marked library.
- The GitHub repository URL is automatically detected from the workflow context and injected into the homepage. You do not need to manually set or edit the repo URL anywhere.

## Modular Usage
To use this setup in any repo:
1. Copy the `.github` folder and `public` folder into your repository.
2. The workflow will automatically detect your repo URL and inject it into the homepage.
3. No manual changes to the repo URL are needed.

## How to Verify Ownership with Google Search Console
1. Go to [Google Search Console](https://search.google.com/search-console/welcome).
2. Add your GitHub Pages site (e.g., `https://<your-username>.github.io/Google-Crawl-My-Repo/`) as a new property.
3. Choose the **HTML file** verification method.
4. Download the HTML file provided by Google (it will be named something like `googleXXXXXXXXXXXX.html`).
5. Place the file in the `public` folder as `google-site-verification.html`.
6. Make sure GitHub Pages deployment by GitHub Actions is active.
7. Commit and push your changes to the `main` branch. The workflow will redeploy the site.
8. Click "Verify" in Google Search Console.

## How it Works
- The site is deployed automatically to GitHub Pages on every push to `main`.
- The `robots.txt` allows all bots and points to a `sitemap.xml`.
- The homepage contains a link back to this repository and displays the README.
- Once Google crawls the GitHub Pages site, it will find the link to this repo and (eventually) crawl the repo as well.

## Files of Interest
- `public/index.html`: Main page with a link to this repo and README rendering
- `public/robots.txt`: Allows all bots and points to the sitemap
- `public/sitemap.xml`: Sitemap for the site
- `public/google-site-verification.html`: Place your Google verification HTML here
- `.github/workflows/deploy.yml`: GitHub Actions workflow for deployment

## Submit a sitemap
Use the following tool to submit your sitemap, and wait a few days for the "couldn't fetch" error to go away:
[Google Url Inspection Tool](https://support.google.com/webmasters/answer/9012289?hl=en)

## Local Testing
To test the site locally and see the README rendered:

```bash
python3 -m http.server --directory public 8000
```

Then open your browser at [http://localhost:8000/index.html](http://localhost:8000/index.html)
