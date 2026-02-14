# Work Orders — attentionfirst.dev

## WO-01: DNS and GitHub Pages Setup

**Goal:** attentionfirst.dev resolves to the GitHub Pages site.

### Steps
1. In GitHub repo settings → Pages → enable from branch `main`
2. Configure DNS at registrar:
   - `A` records pointing to GitHub Pages IPs (185.199.108-111.153)
   - `CNAME` for `www` → `ppiankov.github.io`
3. CNAME file already in repo: `attentionfirst.dev`
4. Wait for HTTPS provisioning (automatic via GitHub)
5. Verify: `curl -I https://attentionfirst.dev` returns 200

### Acceptance
- `https://attentionfirst.dev` loads the site
- HTTPS enforced (no mixed content)
- `www.attentionfirst.dev` redirects to apex

---

## WO-02: ppiankov.dev Redirect

**Goal:** ppiankov.dev redirects to attentionfirst.dev.

### Options (pick one)
- **A)** Registrar-level redirect (simplest — no repo needed)
- **B)** Separate GitHub Pages repo with meta refresh
- **C)** Cloudflare page rule

### Acceptance
- `https://ppiankov.dev` → `https://attentionfirst.dev`

---

## WO-03: Content Refinement

**Goal:** Sharpen tool descriptions after each tool ships v0.1.0.

### Rules
- One sentence per tool. No paragraphs
- Link to repo only — no separate tool pages yet
- Add version badge when tool has tagged release
- Add `brew install` line when formula exists

### Trigger
- Run after each tool reaches v0.1.0 tagged release
- Update only the changed tool's description

---

## WO-04: Additional Spectre Tools

**Goal:** Add kafkaspectre, pgspectre, mongospectre when they have READMEs.

### Steps
1. Wait for README.md to exist in each repo
2. Add tool entry under Spectre section
3. One commit per tool added

### Acceptance
- Only tools with shipped README appear on the site
- No placeholder entries

---

## WO-05: Responsive and Accessibility Audit

**Goal:** Verify site works on mobile, tablet, screen readers.

### Steps
1. Test on iPhone Safari, Android Chrome, desktop Firefox
2. Run Lighthouse accessibility audit — target 100
3. Fix any contrast, focus, or semantic issues
4. Verify no horizontal scroll on 320px viewport

### Acceptance
- Lighthouse accessibility: 100
- Lighthouse performance: 100 (it's static HTML)
- No JavaScript added

---

## Non-Goals

- No blog
- No analytics or tracking
- No JavaScript
- No build tools or bundlers
- No separate pages per tool (repo README is the docs)
- No newsletter signup
- No pricing, no SaaS, no platform language
