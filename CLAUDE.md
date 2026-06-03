# AyuVinc Landing Page — Claude Context

## What this repo is
GitHub Pages site serving **www.ayuvinc.com** — the public landing page for AyuVinc Healthcare Systems.

- **Repo:** `ayuvinc/ayuvinc.github.io`
- **Live URL:** https://www.ayuvinc.com
- **Deploys:** automatically on every push to `main` via GitHub Pages (allow ~1 min)
- **Stack:** Single self-contained `index.html` — no build step, no framework, no dependencies except Google Fonts (Inter)

---

## Repo structure

```
ayuvinc.github.io/
├── index.html        ← entire site (HTML + CSS + JS in one file)
├── images/
│   ├── aditya.png    ← Aditya Kaushal (Founder & CEO)
│   ├── raghu.png     ← Raghu Raja Sharma (Co-Founder & CTO)
│   ├── komal.png     ← Dr. Komal Sharma (Co-Founder & CCO)
│   ├── vipin.jpg     ← Dr. Vipin Koushal (Advisor — PGI Chandigarh)
│   ├── lotika.jpg    ← Lotika Khajuria (Advisor — Former Drug Controller J&K)
│   └── madhav.png    ← Dr. Madhav Kumar (Advisor — Harvard Business School)
├── CNAME             ← maps GitHub Pages to www.ayuvinc.com
├── .nojekyll         ← disables Jekyll processing
└── README.md         ← basic repo description
```

---

## Page sections (in order)

| Section | ID | Purpose |
|---|---|---|
| Nav | — | Sticky. Logo + Our Story / Products / Contact Us links + "Request a Demo" CTA |
| Hero | `#hero` | Headline, sub-text, CTA, micro-copy, trust bar |
| Problem | `#problem` | 3 stat cards + founder quote |
| Products | `#products` | 3 launch products + 1 coming-next card |
| Team | `#team` | 3 founder cards + mission bar + 3 advisor cards |
| Traction | `#traction` | 25 clinics card + PGI Chandigarh engagement card |
| Contact | `#contact` | Name + role + email grid for all 3 founders |
| Footer | — | Logo + copyright |

---

## Design system (CSS variables)

```css
--teal:        #008080   /* primary brand colour */
--teal-dark:   #005f5f   /* hover states */
--teal-light:  #e6f4f4   /* badges, pill backgrounds */
--teal-xlight: #f2fafa   /* section backgrounds, hero gradient */
--bg:          #f9fafb   /* page background */
--white:       #ffffff
--text:        #111827   /* primary text */
--muted:       #6b7280   /* secondary text */
--border:      #e5e7eb
```

Font: **Inter** (Google Fonts) — weights 300, 400, 500, 600, 700.

---

## Key decisions made (do not undo without reason)

- **No strategic/financial data on the landing page.** Gross margins, session pricing, cost per hour, EBITDA targets — all of that lives in the password-gated investor deck (`ayuvinc.com/introduction`), not here. Landing page audience is clinicians, hospitals, and partners — not investors reading unit economics.
- **Nav order:** Our Story → Products → Contact Us. This is intentional — story before product.
- **Contact section has no photos.** Founders appear once in the Team section. The contact grid is email-only to avoid duplication.
- **Haath card has no English translation of the name.** "Haath" (हाथ) is the product name — do not add "hand" as a literal translation.
- **73.3% gross margin removed** from traction section — strategic info, not landing page content.
- **Mobile nav:** hamburger menu (id: `hamburger`) toggles `mobile-menu` div. Nav links hidden on mobile via media query.

---

## Related repos

| Repo | Purpose |
|---|---|
| (this repo) `introduction/` | Investor introduction deck — password-gated at ayuvinc.com/introduction (AES-encrypted). Source of truth for financial metrics and product facts. Read this before adding any numbers to the landing page. |
| `ayuvinc/akcoach` | akcoach fitness coaching app (separate product, different domain) |
| `ayuvinc/Pharma-Base` | Drug interactions database for Dhara |
| `ayuvinc/Transplant-workflow` | AI-assisted transplant workflow automation — Setu |
| `ayuvinc/machinepersonhood` | machinepersonhood.com — AI agent staffing agency (future product) |

---

## How to make changes

1. Edit `index.html` directly — CSS is in `<style>` at the top, JS is in `<script>` at the bottom
2. To add/replace images: drop files into `images/` folder, reference as `images/filename.ext`
3. Commit and push to `main` — live in ~1 minute
4. No build step needed

```bash
# Quick deploy
git add .
git commit -m "your message"
git push origin main
```

---

## gh CLI note
If using `gh` CLI: `export PATH="$HOME/.local/bin:$PATH"` before gh commands (installed at `~/.local/bin/gh`).

---

## What to improve next (when product UI is ready)
- Add a product screenshot or short GIF of Dhara/Vaani in the Products section — the single biggest gap vs. top pre-seed pages. Every competitor page shows what the product looks like.
