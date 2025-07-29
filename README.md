

Set up a dummy website using GitHub Pages to prove ownership and request crawling by google

## How to use
* Add the `.github` folder to your repo
* Verify ownership at google
* Submit a sitemap to Google


## Verify ownership
1. Go to [Google Search Console](https://search.google.com/search-console/welcome).
2. Add your GitHub Pages site (e.g., `https://<your-username>.github.io/Google-Crawl-My-Repo/`) as a new property.
3. Choose the **HTML file** verification method.
4. Download the HTML file provided by Google (it will be named something like `googleXXXXXXXXXXXX.html`).
5. Place the file in the `.github/` folder using the exact filename provided by Google (e.g., `.github/googled68ad817016e862c.html`).
6. Make sure GitHub Pages deployment by GitHub Actions is active.
7. Commit and push your changes to the `main` branch. The workflow will redeploy the site.
8. Click "Verify" in Google Search Console.



## Submit a sitemap

Your sitemap will be available at:
```
https://<your-github-username>.github.io/<your-repo-name>/sitemap.xml
```
Copy and submit this URL in Google Search Console. If you fork or copy this setup, just replace `<your-github-username>` and `<your-repo-name>` accordingly.

Use the following tool to submit your sitemap, and wait a few days for the "couldn't fetch" error to go away:
[Google Url Inspection Tool](https://support.google.com/webmasters/answer/9012289?hl=en)

## Local Testing
To test the site locally and see the README rendered:

```bash
mkdir -p public
cp README.md public/README.md
python3 -m http.server --directory public 8000
```

Then open your browser at [http://localhost:8000/index.html](http://localhost:8000/index.html)
