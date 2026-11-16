# CH₄ ALERT website

Project website for **CH₄ ALERT (Africa Land Emissions Reporting & Tracking)**, with the public **Africa CH₄ Atlas** at `atlas/`.

It is a plain static site (HTML, CSS, JSON and images), with no build step, so GitHub Pages serves it as is.

```
index.html          Project homepage
publications.html   Project outputs and key references
style.css           Shared styles for the two pages above
assets/             Network map figure and social-preview image
atlas/              Africa CH₄ Atlas (interactive map, read-only)
  index.html
  sites.json        1,016 observation records (contact emails removed)
  meta.json         Country list and integration log
  footprints.json   EM27/SUN 3-day footprints (Jan, Mar, Jul, Oct)
  *.topo.json, *.webp, emissions.json, tracks.json   Map layers
.nojekyll           Tells GitHub Pages to serve files as they are
```

## Publish on GitHub Pages

1. **Create the GitHub account or organisation.** For an address like `https://ch4-alert.github.io`, create a free organisation called `ch4-alert` at <https://github.com/organizations/new> (or use a personal account; the site will then live at `https://<username>.github.io`).
2. **Create the repository.** Name it exactly `ch4-alert.github.io` (or `<username>.github.io`), set it to **Public**, and don't add a README.
3. **Upload the files.** On the new repository page choose **uploading an existing file**, drag in *everything inside this folder* (including the `atlas` and `assets` folders and `.nojekyll`), and click **Commit changes**.
   - With Git instead: `git init`, `git add .`, `git commit -m "First version"`, `git branch -M main`, `git remote add origin https://github.com/ch4-alert/ch4-alert.github.io.git`, `git push -u origin main`.
4. **Turn on Pages.** In the repository go to **Settings → Pages**, set *Source* to **Deploy from a branch**, branch **main**, folder **/(root)**, and save.
5. After a minute or two the site is live at `https://ch4-alert.github.io/`, and the atlas at `https://ch4-alert.github.io/atlas/`.

To link it from the Congo Basin Institute website, ask the CBI web team to add a link to that address, or to embed the atlas:

```html
<iframe src="https://ch4-alert.github.io/atlas/" width="100%" height="800" style="border:0" title="Africa CH₄ Atlas"></iframe>
```

## Before publishing, check

- **Contact email:** replace `YOUR-EMAIL@example.org` in `index.html` (Get in touch section).
- **Team list:** confirm everyone listed under *Team & partners* is happy to be named.
- **Rwanda site:** the homepage lists "Kigali / Mt. Mugogo" until the final location is confirmed.

## Updating the atlas

The atlas is a read-only copy of the contributor version kept on claude.ai. To update it, replace `atlas/sites.json`, `atlas/meta.json` and/or `atlas/footprints.json` with new exports and commit. Remove the `ce` (contact email) values from `sites.json` before publishing.
