# GitHub Pages update — LinkedIn preview size fix

LinkedIn Post Inspector returned: "size was larger than our threshold; maximum size for this input stream is 3145728 bytes".

The previous HTML embedded Plotly's full JavaScript library (about 4.8 MB), putting it over LinkedIn's scraper limit. This version stores Plotly in a separate local file. It remains fully interactive and needs no external CDN.

Upload **all three files** into the root of your existing GitHub repository (same level):

- `index.html` (the website page and LinkedIn metadata, under 3 MB)
- `plotly.min.js` (local visualization library)
- `linkedin-preview.png` (social link preview image)

Commit all three files, wait for GitHub Pages deployment to complete, and verify the dashboard still works at https://ammonyorgason.github.io/us-economy-1960s/ . Then paste that URL into https://www.linkedin.com/post-inspector/ and click Inspect again.

**Important:** The webpage still works offline after downloading the entire folder. The HTML file alone is no longer self-contained because the local JavaScript was split out. This is necessary to satisfy LinkedIn's HTML scraper limit without losing the interactive features.
