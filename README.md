# Psalmy Design website

Open `index.html` from the extracted folder to browse the site. Home and Pricing use plain HTML, CSS and JavaScript. There is no installation or build step.

## Publish on GitHub Pages

1. Create a public GitHub repository and copy the extracted contents directly into the root of its `main` branch. Include the empty `.nojekyll` file. Keep `index.html` alongside `pricing.html`.
2. In the repository, open **Settings → Pages**.
3. Under **Build and deployment**, select **Deploy from a branch**, then choose **main** and **/ (root)**. Save.
4. When GitHub finishes deploying, open `https://USERNAME.github.io/REPO-NAME/`.
5. Set up the Apps Script endpoint below and verify delivery from the live Pricing page. If you add a custom domain later, configure it in the repository’s Pages settings.

## Connect the project form to email

1. Open [Google Apps Script](https://script.google.com/), create a project, paste the contents of `Code.gs`, and check that `TO_EMAIL` is `psalmydesign@gmail.com`.
2. Open **Deploy → New deployment**, choose **Web app**, set **Execute as** to **Me**, and set **Who has access** to **Anyone**.
3. Authorize the project and copy its web app URL ending in `/exec`.
4. Paste that URL between the quotes in `APPS_SCRIPT_URL` at the top of `script.js`. Commit the update to GitHub and wait for Pages to refresh.
5. Submit a test request from the live site. Check the inbox and spam folder, and verify that Reply addresses the test sender.

The form uses the brief’s cross-origin POST approach. The browser treats a completed network request as success and cannot read the Apps Script response. Confirm delivery in the inbox during setup. A missing endpoint or a network failure offers WhatsApp and preserves the form entries. If you later change the Apps Script code, update the deployed web app to a new version under **Manage deployments**.

## Placeholders and items to review

| Item | Current state | Where to edit |
| --- | --- | --- |
| Form endpoint | Blank until the Apps Script web app is deployed | `APPS_SCRIPT_URL` in `script.js` |
| Currency | Naira, as specified by the brief’s working assumption | Package prices and budget markup in `pricing.html` |
| Package contents, timings and revisions | Proposed defaults from the brief | Package cards and FAQ in `pricing.html` |
| Budget ranges | Four draft ranges from the brief | Budget options in `pricing.html` and `BUDGETS` in `Code.gs` |
| FAQ and reply timing | Five draft answers. The form promises an email or WhatsApp follow-up without specifying a response time. | FAQ and form introduction in `pricing.html` |
| Work samples | Three neutral cards with “Project name” and “Project type” | Selected work in `index.html` |
| Wordmark | “Psalmy” in the heading font, with a matching P favicon | Navbar and footer in each HTML file, plus `assets/favicon.svg` |
| Testimonials | Hidden until real quotes are added | `SHOW_TESTIMONIALS` and `TESTIMONIALS` in `script.js` |
| Social profiles | Instagram and LinkedIn placeholders are hidden until URLs are added | `SOCIAL_URLS` in `script.js` |
| Repository and custom domain | GitHub repository and optional custom domain still to be assigned | GitHub Pages settings |

The form timestamps requests in Lagos time. The Home hero uses a decorative illustration of desktop and mobile layouts. The three portfolio cards are placeholders.
