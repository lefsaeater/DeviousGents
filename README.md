# The Devious Gents

The official band website for The Devious Gents, based in Bozeman, Montana:
https://thedeviousgents.com.

## Editing

Edit [index.html](index.html) to change the home page content or styles.
The [contact page](contact.html) and [thank-you page](contact-thanks.html) share
[contact styles](assets/contact.css).
No dependencies or build tools are required. Open it in a browser to preview.

The page includes a responsive band introduction, band artwork, show
announcements, and a link to the contact form. There are no external font, image,
or script dependencies; submitting the contact form uses FormSubmit.

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

The band section also includes a responsive performance gallery using
[the window-light photo](assets/images/window-light-vignette.jpg) and
[the crowd-view photo](assets/images/crowd-view.jpg). Photos retain their full
original framing, include descriptive alternative text, and load lazily. They
appear side by side on larger screens and stack on phones.

Update the shows section when dates are confirmed, replacing the announcement
message with real venue, date, and ticket information. The band section can be
expanded as music and more photos become available.
Instagram links currently point to `https://www.instagram.com/thedeviousgents/`.
Keep the page description and Open Graph metadata in sync with content changes.

## Contact form

The contact page also includes an **Email us directly** button that opens the
visitor's email app using a `mailto:` link to `raanders+thedeviousgents@hotmail.com`,
without going through FormSubmit.

[contact.html](contact.html) posts names, reply email addresses, request topics,
and messages to FormSubmit for delivery to
`raanders+thedeviousgents@hotmail.com`. The visitor's `email` field becomes the
email Reply-To address. FormSubmit's hosted reCAPTCHA is enabled explicitly;
visitors complete it after clicking **Send request**. Do not disable `_captcha`
or switch to an AJAX submission that bypasses this flow.

Before accepting public requests:

1. Publish the pages, then submit an initial request from the live contact page.
2. Check the recipient inbox (and junk folder) for FormSubmit's activation email
   and click its confirmation link. Until activation, delivery is not ready.
3. Submit a second test request, complete the CAPTCHA, and verify that the
   message reaches the inbox, Reply-To uses the visitor's email, and the browser
   returns to [contact-thanks.html](contact-thanks.html).

Use an HTTP server for local form testing, not a `file://` URL. The `_next`
redirect intentionally points to the production HTTPS thank-you page. Native
browser validation checks required fields and email format; CAPTCHA verification
and email forwarding are handled by FormSubmit, not GitHub Pages. Provider errors
remain visible on the provider's page rather than showing a local success message.
The site needs no API keys or mail credentials. The recipient address is public
in the form action; after activation, FormSubmit can supply an opaque action URL
to replace it (see [FormSubmit documentation](https://formsubmit.co/documentation)).

The form discloses the external processing and links to FormSubmit's privacy
policy. FormSubmit documents retaining submissions for 30 days. Avoid collecting
sensitive information. Delivery depends on FormSubmit's availability and the
recipient mailbox; CAPTCHA reduces spam but cannot eliminate it.

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
