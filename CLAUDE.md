# sitrip homepage

Company homepage for sitrip (시트립), served at https://sitrip.co.kr via GitHub Pages.
Plain HTML + CSS, no build step: `index.html`, `styles.css`, `CNAME`.

## Design system: Astryx tokens (do not replace)

This site uses the token names and values of **Astryx** (Meta's open source design system, MIT) as plain CSS. There is no React and no Astryx package here, only the tokens.
Source: https://github.com/meta/astryx (`@astryxdesign/theme-neutral` 0.7.16, `dist/theme.css`). The workspace rules are in `../docs/design-system.md`.

- Keep the Astryx neutral look: tokens in `:root` of `styles.css` (`--color-*`, `--radius-*`, `--spacing-*`, `--size-element-*`, `--font-size-*`, `--text-*-leading`). Change or add UI by reusing these tokens and the existing patterns (`.btn`, `.chip`, `.card`, `.feature`, `.section`).
- Two things are sitrip's own, not Astryx's: the accent color (`--color-accent` `#0066FF`, with `--color-on-accent`, `--color-text-accent`, `--color-accent-muted`) and the font (`--font-family-body`, Pretendard).
- Use `--color-accent` for fills and `--color-text-accent` for text and icons on a background. Text on an accent fill uses `--color-on-accent`.
- Never hard-code a color, spacing, font size, line height or radius in a rule; use a token. A value that is not a step of the Astryx scale goes to the nearest step. Page-level sizes above the scales use the `--layout-*` tokens.
- A font size and its line height go together: `xs`/`sm` with `--text-supporting-leading`, `base` with `--text-body-leading`, `lg` with `--text-large-leading`, `xl` with `--text-heading-2-leading`, `2xl` with `--text-heading-1-leading`, `3xl`/`4xl`/`5xl` with `--text-display-3`/`-2`/`-1-leading`.
- Do not switch to another design system, UI kit, CSS framework (Tailwind, Bootstrap, etc.), or a different color palette/font unless the user explicitly asks to change the design. The Wanted Design System was dropped on 2026-11-18; do not bring it back.
- Dark mode follows `prefers-color-scheme`; when adding a color token, define it in both the light and dark blocks.
- Font sizes and line heights have a second set of values for touch screens narrower than 1024px (the `pointer: coarse` block). When adding one of these tokens, define it in both blocks.

## Licensing rules (commercial site)

- **Keep the MIT notice** in the header comment of `styles.css` (Astryx copyright line and permission text) and the credit in the footer (`.footer__credit`). If you modify the design, it stays "Modified by sitrip."
- **No photos, illustrations, or stock images.** Do not copy any images, icons, or illustrations from the Astryx site, its templates or anywhere else.
- **Do not use the Meta or Astryx logo or name** in sitrip branding (trademarks are not covered by MIT). Naming Astryx in the license credit is fine.
- Fonts: only **Pretendard** (SIL OFL 1.1, via jsDelivr). Do not add Figtree (the Astryx neutral font, no Korean glyphs) or other fonts unless their license is confirmed for commercial use.
- Only add assets whose license clearly allows commercial use, and note the license in the footer credit.

## Privacy

- Never commit personal documents (contracts, IDs, photos). `.gitignore` blocks jpg/jpeg/heic/pdf.
- Do not put the business address or 사업자등록번호 on the page unless the user asks.

## Search engines

- The site is kept out of search results with `<meta name="robots" content="noindex, nofollow">` in `index.html`. Keep it unless the user asks to allow search.
- Do not add a `robots.txt` that disallows crawling: blocked crawlers can't see `noindex`, so the URL could still show up in results.

## Content

- sitrip: 여행에 필요한 모든 서비스를 만드는 회사. First product: 여행 가계부 (in development).
- 여행 가계부 is a **web service** (mobile web first, also PC browsers; no app install). There is no iOS or Android app. Planned app URL: `app.sitrip.co.kr`. Screen previews show one phone screen and one PC browser window.
- **AI 검색 is the core feature** of 여행 가계부 (ask about your spending in natural language). Keep it the most prominent feature (`.highlight` block in the Product section).
- Contact: nespot2@sitrip.co.kr
- Page copy is Korean; keep the tone short and plain.
- The `#en` section ("In English", `lang="en"`) is a short English summary for overseas reviewers (startup programs such as Cloudflare for Startups). When the Korean product copy changes, update `#en` to match. It must not outrank the AI 검색 `.highlight` block.
