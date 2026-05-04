# Peter Harris Presents — Funding Project Plan

Password-protected web page for the jazz album series funding plan.

## Live URL

After GitHub Pages is enabled this will publish to:

```
https://humidhaney.github.io/peter-harris-presents/
```

## Access

The page is encrypted with AES-256-GCM (PBKDF2, 250,000 iterations). Visitors must enter the access password to decrypt and view.

## Updating content

1. Edit the source HTML at `Peter_Harris_Presents_Project_Plan.html` (one level up from this folder, kept private).
2. Re-run the encryption script to regenerate `site/index.html`:
   ```bash
   python3 encrypt_page.py
   ```
3. Commit and push the new `index.html`. GitHub Pages will redeploy automatically.

## Why client-side encryption (not just a JS prompt)

A naive password prompt that does `if (input === "secret")` is bypassable in seconds by viewing the page source. This page instead encrypts the entire content with the password as the key — without the correct password the content is unreadable, even with full source access.
