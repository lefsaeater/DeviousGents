# The Devious Gents

A simple static website for https://thedeviousgents.com.

## Editing

Edit [index.html](index.html) to change the page content or styles.
No dependencies or build tools are required. Open it in a browser to preview.

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
