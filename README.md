# Khazen Support

Public-facing support, legal, and FAQ pages for **[Khazen — Personal Finance](https://apps.apple.com/app/id6761610239)**.

Hosted via GitHub Pages at: **https://khassinx.github.io/khazen-support/**

## Pages

| File | Live URL | Purpose |
|------|----------|---------|
| [`index.html`](./index.html) | [/](https://khassinx.github.io/khazen-support/) | Landing page with links to all docs |
| [`privacy-policy.html`](./privacy-policy.html) | [/privacy-policy.html](https://khassinx.github.io/khazen-support/privacy-policy.html) | Privacy Policy (referenced in App Store Connect + Settings → About) |
| [`terms.html`](./terms.html) | [/terms.html](https://khassinx.github.io/khazen-support/terms.html) | Terms of Service |
| [`support.html`](./support.html) | [/support.html](https://khassinx.github.io/khazen-support/support.html) | FAQ + contact info |

## Editing

All pages are self-contained HTML with inline CSS. No build step required — edit, commit, push, and GitHub Pages serves the new version within ~30 seconds.

To match Khazen's iOS app theme, the CSS variables at the top of each `<style>` block control the color palette:

```css
--bg:        #0A1429;   /* Khazen navy background */
--teal:      #5EEAD4;   /* Khazen teal accent */
--purple:    #B891E8;   /* Khazen purple accent */
--text:      #FFFFFF;
--text-mut:  rgba(255,255,255,0.66);
--text-dim:  rgba(255,255,255,0.45);
```

If you change the design system in the iOS app, also update these variables here so the web pages stay visually consistent.

## Why a separate repo?

- The iOS app code lives in a private repo. These pages need to be public (App Store, in-app links, search engines).
- Updating legal docs shouldn't require an iOS release.
- This pattern mirrors [`khassinx/asvab-coach-support`](https://github.com/khassinx/asvab-coach-support) which serves the same purpose for the ASVAB Coach app.

## Contact

For privacy questions, data requests, or anything else: **hello@khassinx.com**
