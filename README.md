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

## Visual layout editor upgrade
- Replace only editor.html in your GitHub repository to install the new editor. It reads content from the existing index.html and then restores any browser draft. Back up your old draft first.
- Text mode: select a text box, then set its font size and font color in the toolbar. These apply to the selected text element, not only a highlighted word.
- Layout mode: freely drag text, images, logo, navigation or social icons. Resize using the eight selection handles. Images preserve aspect ratio by default; uncheck Image ratio for free proportions.
- Pink edge/center alignment guides and snapping appear only during manipulation, and disappear on release. Hold Alt to temporarily disable snapping.
- X and width use parent-relative percentages; Y and height use pixels. Text box height is a minimum so text is never clipped. Font size separately controls text scale.
- Undo, redo and reset selection are available for layout changes.
- Desktop positions and styling are embedded in the exported index.html. Public mobile views use natural flow instead of manual offsets.
- Import supports both old JSON backups and exported HTML files, preserving your content while using the new editor features.
- Export Site, then click the download link. Replace index.html on GitHub to publish. This does not require changing editor.html again.

## Multi-selection and keyboard upgrade
Default: single click selects and dragging moves. No mode switch is required. Double-click text to edit; Escape finishes text editing. Double-click an image to replace it, or a social/navigation link to edit its address.
Drag on blank space to draw a selection marquee. Elements intersecting the box are selected. Hold Shift/Ctrl/Cmd while selecting to add/remove items. Drag any selected item to move the group; the group selection handles resize it.
Ctrl+Z / Cmd+Z undoes editor changes outside text/input fields. Ctrl+Shift+Z / Cmd+Shift+Z or Ctrl+Y redoes. While typing in a field, normal text undo remains available. A grouped drag is one undo step; selection-only clicks do not create layout history.
Use the standalone editor.html upgrade exactly as before; it reads your existing index.html and browser draft. Back up drafts before upgrading. Export the resulting index.html to publish changes.

## Shift movement, content boundaries and News update
Hold Shift while dragging to constrain movement horizontally or vertically. The dominant initial drag direction determines the axis while Shift is held. Release Shift to move freely. Shift-click still toggles selection; Shift-drag retains the selection. Snapping never moves the locked axis.
The editor displays two dashed vertical content boundaries. Drag either independently to change the entire site's available content width. Text reflows, columns adapt, images resize and manual pixel offsets/heights scale with the available width. Content width is shown above the page. Boundary movement is one undo step and is retained in backup and export. Preview/public views hide the boundaries but retain the chosen content area; public mobile layouts use safe natural margins.
This release updates News to the 16 supplied entries, August 2026 through March 2025. The editor applies that update once to older published content or browser drafts while preserving other content and layout. Later manual News edits remain intact.
Upgrade by replacing editor.html. Export and upload index.html to publish both the new News and content-width changes.

## Expanded color panel and bold-color fix
Bold text now inherits its existing text color, including publication authors. Bold/regular formatting changes weight only.
The editor color panel is always expanded: saturation/brightness square, hue slider, current color preview, HEX, individual R/G/B fields, and common color swatches are visible together. No system color-picker popup is required. HEX/RGB/visual controls update together and apply to all selected text elements. Colors remain saved in browser drafts and embedded in exported index.html.
Upgrade by replacing editor.html, then export and upload index.html to apply the color inheritance fix to the public website as well.

## Editable DOI/PDF links and custom images
DOI, PDF and Project anchors are selectable independent elements: click to select, drag to move, use selection handles to resize or set font size. Double-click to edit the visible label and URL. The paper-links row is full width to keep percentage-based movement and resizing stable.
The Insert Image toolbar button uploads an independent PNG/JPG/WebP/GIF (or image URL), with optional click-through link and page assignment. The new image supports selection, group movement, proportional/free resizing, property edits and deletion. Its image bytes, link and geometry are embedded in backup/export.
Double-click a CV/Scholar/Twitter/LinkedIn/Email icon to upload a custom image and edit its link. Uploaded icons have transparent backgrounds instead of the built-in blue circle. The existing icon position is retained. Click then drag/resize as with other images. Use the Image / Link toolbar button as an alternative to double-clicking.
Replace editor.html to upgrade while preserving current published content/browser drafts; export and upload index.html to publish the new links and images.

## Universal image deletion and object arrangement
- Select any image, including the original logo, portrait, paper figure, gallery image, built-in social icon or inserted image. Click Delete Image or press Delete/Backspace. Text inputs retain normal typing behavior. Multi-selected images can be deleted together.
- Deletion removes the image from the visible page, browser draft and exported/public rendering while preserving its source for undo/recovery. Ctrl+Z restores the last action; Restore Deleted Images restores all removed images. Deleting a paper figure preserves its citation.
- A multi-object arrangement panel appears for 2+ selected objects: left/horizontal center/right and top/vertical center/bottom alignment.
- For 3+ objects, distribute horizontal left/center/right or vertical top/center/bottom anchors, or make horizontal/vertical gaps equal.
- Enter a spacing value in pixels and apply fixed horizontal/vertical gaps for 2+ objects.
- Alignment reference can be the selection bounds, page content area, or last-selected key object.
- Each arrangement operation is a single undo step. Draft and HTML exports retain the resulting positions.
- Source is now maintained in src/editor.js, src/styles.css and src/content.json. python build.py regenerates the self-contained pages. Users still edit visually without running code.

## Universal selected-element deletion fix
The Delete Selected button and Delete/Backspace now work on all selected objects: text boxes, images, DOI/PDF links, navigation and social links. Mixed multi-selections delete in one undo step. While typing inside a text box or input, Delete/Backspace still deletes characters normally. Ctrl+Z restores deleted objects; Restore Deleted Elements restores all deleted objects. Deleted text and image state persists in browser drafts and HTML exports.

### 插入文本框与预览定位修复
工具栏点击「插入文本框」，输入内容并保存；双击文本框继续编辑，单击选择后可拖动、缩放、改字号颜色、删除及撤销。先选择某篇论文的元素，再插入图片或文本框，新物件会跟随这篇论文定位。编辑按钮改为悬浮显示，不再撑高 News 或论文排版。编辑、预览、导出使用一致的内容坐标。旧草稿中的自由图片首次打开时会转换为区域定位。
更新时先替换 editor.html，在原浏览器打开以保留草稿；确认后导出 index.html 并上传 GitHub。
