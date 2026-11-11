# PhishEz — browser-only email safety checker

A static, browser-based prototype designed for GitHub Pages. Email text is processed locally in the browser; no PhishEz backend or hosted analysis API is used.

## Deploy
1. In repository Settings → Pages, select **GitHub Actions** as the build and deployment source.
2. Push to the main branch. The included workflow deploys the static site.
3. Open https://ezellermaier-cell.github.io/phisez/ after deployment completes.

## Current capabilities and limitations
- Paste email text or upload/drop an .eml file.
- Local heuristic checks for suspicious language, reply-to mismatch, IP-based links, Punycode and risky file extensions.
- Extracts URLs and displays basic sender/header information.
- Does not make external analysis API calls.
- This initial static version does **not** independently perform DNS, SPF/DKIM/DMARC verification, redirect traversal, attachment detonation, or local neural-model inference. Authentication results are read from supplied headers only.
- A low risk score is not proof an email is safe. Do not open suspicious attachments.

## Privacy
The page does not transmit email content to a PhishEz server. GitHub serves the static website files. Browser clipboard access is only requested when the user clicks Paste.
