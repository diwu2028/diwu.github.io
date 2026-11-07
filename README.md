# Di Wu — screenshot-based academic website

## Open and edit without coding
Open index.html in a browser (double-click works; no server needed).
Open editor.html, or append ?edit=1 to index.html, to edit.
- Click any outlined text to edit. Select text and use B, I, U or the text-link button.
- Click a picture or logo to replace it with an image upload or URL and change alt text.
- Click social icons or navigation in editor mode to change their label/link/icon.
- Settings / Navigation changes colors, font size, maximum width, contact email and all four navigation links. Upload a licensed Avenir font file to make the exact font available on devices without Avenir.
- Switch Page opens Home, Architecture, Contact without changing navigation links.
- Add / delete / reorder News, papers and Architecture images using inline controls.
- Paper PDF/DOI/Project links have a dedicated edit button. Empty PDF URLs are not rendered as fake links.
- Architecture starts empty; add images, captions, descriptions and optional project links.
- Preview hides the editing outlines and controls temporarily.
- Edits auto-save to IndexedDB on this browser/device only. They do not modify the live site or source file.
- Backup exports di-wu-content.json. Import restores it, including uploaded images and font.
- Export Site downloads one self-contained index.html with all content and uploaded images/fonts embedded. Replace your published index.html with this file to update the website.

The editor is not an authenticated publishing backend. Visitors cannot change the public website through it; each editor changes only their own browser draft. There are no passwords or GitHub tokens in the site.

## Deploy to GitHub Pages
Create USERNAME.github.io. Upload index.html, editor.html and .nojekyll from this folder to the repository root.
Settings → Pages → Deploy from a branch → main → /(root).
Updates: edit visually, click Export Site, upload the new index.html to the repository and commit. Preserve any existing CNAME file.
Keep the backup JSON separately for recovery. If using local files and draft persistence is unavailable in your browser, use Backup/Import explicitly.

## Domain bought through Wix
Domain registration must remain renewed; the Wix website plan is independent.
1. GitHub repository Settings → Pages → Custom domain: enter your domain and save. Preserve the generated CNAME file when updating.
2. Wix Domains → Manage DNS (or your actual DNS host if nameservers are elsewhere).
3. Set @ A records to 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153.
4. Set www CNAME to USERNAME.github.io with no protocol or repository path. Remove conflicting website A/CNAME entries; preserve email MX/TXT records.
5. Wait for DNS and enable Enforce HTTPS on GitHub Pages.
6. Verify the domain in GitHub account Settings → Pages with the TXT record GitHub supplies.

## Content review notes
The screenshot biography, News dates and paper statuses are preserved, including second-year and IEEE Sensor 2025 / Under review. Some right-hand screenshot text is truncated; verify reconstructed endings and author spellings using your own bibliography. Research figure images and portrait/logo are crops from supplied screenshots; replace them with originals for best quality. The five verified DOI links are prefilled; absent PDF URLs remain blank. Materials Horizons screenshot title differs from the title on the publisher DOI page; check the preferred final title before launch.
Lab address: tiilt Lab, Mudd 3104, 2233 Tech Drive, Evanston IL 60208, from official tiilt contact page and Northwestern Mudd Hall address.

Official references:
https://tiilt.northwestern.edu/contact/
https://www.mccormick.northwestern.edu/contact/maps.html
https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site
https://support.wix.com/en/article/connecting-a-wix-domain-to-an-external-site
