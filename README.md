# OptimizeMe public site

Three static pages: a landing page, the privacy policy and the terms of
service. No build step, no dependencies.

These exist because they are **required**, not decorative:

- **Oura's application form** demands public Website, Privacy Policy and
  Terms of Service URLs before it will issue credentials.
- **Apple App Review** requires a publicly hosted privacy policy linked
  from App Store Connect.

## Publishing with GitHub Pages

From a new repository containing this folder:

```bash
git init && git add . && git commit -m "OptimizeMe site"
gh repo create optimizeme-site --public --source=. --push
```

Then in the repository: **Settings > Pages > Source: main branch, /web
folder**. The pages appear at:

```
https://<your-github-username>.github.io/optimizeme-site/
https://<your-github-username>.github.io/optimizeme-site/privacy.html
https://<your-github-username>.github.io/optimizeme-site/terms.html
```

Pages serves over HTTPS, which is what every provider and App Review
expects.

## Keeping them honest

The privacy policy describes real system behaviour: device-local storage,
analysis requests that are computed and discarded, AES-256-GCM encryption
of provider tokens, and no iCloud storage of HealthKit data. If that
behaviour changes, change this page in the same commit. A privacy policy
that drifts from the implementation is worse than none, because it is a
claim you can be held to.
