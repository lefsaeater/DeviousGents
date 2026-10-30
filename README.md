# The Devious Gents

The official band website for The Devious Gents, based in Bozeman, Montana:
https://thedeviousgents.com.

## Editing

Edit [index.html](index.html) to change the page content or styles.
No dependencies or build tools are required. Open it in a browser to preview.

The page includes a responsive band introduction, band artwork, show
announcements, and an Instagram contact section. Styles are included in the HTML,
with no external font, image, or script dependencies.

The supplied band images live in [assets/images](assets/images):
[transparent color logo](assets/images/devious-gents-badge-transparent.png) is the
primary brand mark in the header and hero, displayed directly against the site
background without a frame. Its turquoise, orange, and red palette and
Western-inspired serif typography guide the site design. The
[white-background color logo](assets/images/devious-gents-color.jpg) is retained
for Open Graph sharing previews so it remains readable on different platforms.
The [black-and-white logo](assets/images/devious-gents-logo.png) is a smaller,
secondary accent in the band section. Both are displayed uncropped with their
original proportions. Keep these assets with the HTML when publishing.

Update the shows section when dates are confirmed, replacing the announcement
message with real venue, date, and ticket information. The band and contact
sections can be expanded as music, photos, and a booking email become available.
Instagram links currently point to `https://www.instagram.com/thedeviousgents/`.
Keep the page description and Open Graph metadata in sync with content changes.

## Publishing

GitHub Pages publishes the root of the `main` branch after changes are pushed.
[CNAME](CNAME) preserves the custom domain; [.nojekyll](.nojekyll) disables
Jekyll processing.

## Domain setup

In GoDaddy's DNS management for `thedeviousgents.com`, configure:

| Type | Name | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | lefsaeater.github.io |

Replace conflicting website records for `@` and `www`. Disable domain forwarding
if enabled. Leave unrelated records, including email MX and TXT records, intact.
If apex AAAA records exist, remove conflicting values or use GitHub's documented
IPv6 addresses instead.

After DNS propagates and GitHub provisions the certificate, enable **Enforce
HTTPS** under the repository's **Settings > Pages**.

For additional protection, verify domain ownership in the `lefsaeater` account's
**Settings > Pages** using GitHub's supplied TXT record.

See [GitHub's custom domain documentation](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site).
