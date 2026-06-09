# khazen-support

Source for **khazen.khassinx.com** — the public web property for [Khazen](https://apps.apple.com/app/khazen/id6761610239), a personal finance app for Apple platforms.

## What lives here

- `index.html` — landing page (EN)
- `legal/` — Privacy Policy, Terms of Use, Legal index
- `security/` — Security & Responsible Disclosure
- `support/` — User support + FAQ
- `es/` — native localized mirror (Spanish)
- `_layouts/` — Jekyll base + prose layouts
- `assets/css/` — Layer 3 primitives + Layer 2 Khazen brand tokens
- `assets/favicons/` — K monogram favicons (multi-color gradient)
- `.well-known/security.txt` — RFC 9116 machine-readable security policy

## Stack

Static site (Jekyll), served over HTTPS at `khazen.khassinx.com`.

## Localization

EN default (no prefix), ES under `/es/`. Each locale is **natively written**, not machine-translated. Per-page `lang:` front-matter + hreflang tags signal locale to crawlers.

## Contact

- General: [hello@khassinx.com](mailto:hello@khassinx.com)
- Security: [security@khassinx.com](mailto:security@khassinx.com)
