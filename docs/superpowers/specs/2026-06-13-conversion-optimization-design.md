# Conversion Optimization & Design Elevation — NOVEX International

**Date:** 2026-06-13
**Site:** novex-international.com (static single-page, GitHub Pages)
**Primary audience:** Automotive OE manufacturers & Independent Aftermarket brands/sellers
**Primary CTA:** Contact form
**Goal:** Inform about service portfolio, drive interaction

---

## Scope

1. Navigation clarity
2. Hero section — messaging, hierarchy, CTAs, meta-slots
3. Marquee — audience-relevant terms only
4. Automotive section — headline & subtext
5. Content/Imagery section — rename + subtext
6. Section reordering — reduce scroll friction for primary audience
7. Ventures section — reframe as track record
8. Contact section — form UX, qualification, trust signals
9. Design elevation — visual details

---

## Constraints

- Keep existing design language (color palette, typography, animations)
- No client logos or names in hero (no written permission; names remain in existing body-text positions)
- Sold ventures (Retromotion, ecanis.shop) referenced historically only
- No external dependencies added

---

## 1. Navigation

| Element | Current | New |
|---|---|---|
| Nav link | Content | Imagery |
| Mobile menu | Content | Imagery |

---

## 2. Hero Section

### Kicker (new element above headline)
- HTML: `<p class="hero-kicker reveal d1">E-Commerce · Catalog Data · Product Imagery</p>` — inserted before `.hero-h`
- Styling: italic Besley, 16px, `var(--muted)`, margin-bottom 16px
- No background, no border — pure typographic label
```css
.hero-kicker { font-family: var(--serif); font-style: italic; font-size: 16px; color: var(--muted); margin-bottom: 16px; }
```

### Headline
Unchanged: "Architecting sovereign systems."

### Subtext
**Current:**
> "The e-commerce, content and data partner for OE and aftermarket businesses — and the venture studio behind AI-driven systems and high-performance leadership."

**New:**
> "The e-commerce, catalog data and content partner for OE manufacturers and Independent Aftermarket brands — marketplace operations, product data standards, professional imagery and API integration. Built by operators, for operators."

### CTAs (order swapped)
1. Primary (btn-solid): "Start a conversation →" → `#contact`
2. Secondary (btn-line): "See our services →" → `#automotive`

Both buttons: padding increased to `20px 36px` (from `18px 32px`) for more visual weight.

### Hero-Meta (3 slots)
| Slot | Content |
|---|---|
| Expertise | E-Commerce · Catalog Data · Imagery |
| Track record | Built & scaled automotive e-commerce from the ground up |
| Market | OE & Independent Aftermarket · Operating globally |

---

## 3. Marquee

**Current:** Automotive E-Commerce · Product Imagery · Venture Building · AI Orchestration · Spin-offs · Leadership Engineering

**New:** Automotive E-Commerce · Catalog Data & PIM · Product Imagery · 360° Photography · Marketplace Operations · API & Systems Integration · OE & Independent Aftermarket

Animation duration: 40s (from 30s) — slower, more premium feel.

---

## 4. Automotive Section

### Section headline
**Current:** "E-commerce, data & content — automotive to the core."
**New:** "Marketplace operations, catalog data & content — built for parts manufacturers and brands."

### Section subtext
**Current:** "Operating reality across OE and Independent Aftermarket — as advisor, operator and venture builder."
**New:** "End-to-end expertise across OE and Independent Aftermarket — from assortment strategy and data standards to marketplace build-out and platform integration."

Caps (4 service boxes): unchanged — descriptions are already precise.

---

## 5. Imagery Section (renamed from Content)

### Section id & anchor
`id="content"` → `id="imagery"` — update nav links accordingly.

### Section headline
Unchanged: "Product imagery that sells parts."

### Section subtext
**Current:** "Flexible production — in-house at your warehouse facility or within our own studio infrastructure. High-tech, efficient, cost-effective and rapidly scalable."
**New:** "On-site at your warehouse or in our own studio — standardized sets, 360° spins and marketplace-ready output. High volume, fast turnaround, immediately deployable."

---

## 6. Section Reordering

**New order:**
1. Hero
2. Marquee
3. Automotive (`#automotive`)
4. Imagery (`#imagery`)
5. Ventures → renamed "Track Record" (`#ventures`)
6. Founder (`#founder`)
7. Contact (`#contact`)
8. Thesis (`#thesis`)
9. AI (`#ai`)
10. Leadership (`#leadership`)
11. Principles (`#principles`)
12. Footer

Navigation links updated to match new section IDs.
Footer links updated to match.

---

## 7. Ventures Section — Reframed as Track Record

### Section label
**Current:** "active ventures"
**New:** "track record"

### Section headline
**Current:** "We build, operate & spin off."
**New:** "Built from the ground up. Operated. Sold."

### Section subtext
**Current:** "Not theory. Operating ventures, engineered in-house and built for independence."
**New:** "First-hand experience building and scaling automotive e-commerce operations — not consulting from the outside, but operating from within."

### Status badges
- Retromotion: "Co-Founder" → "Divested"
- ecanis.shop: "Founder & CEO" → "Divested"

### "Divested" badge styling
Same `.status` class, additional class `.divested-tag`:
```css
.vnt .status.divested-tag {
  border-color: var(--muted);
  color: var(--muted);
  opacity: 0.7;
}
```

### Internal venture order (swapped)
Automotive ventures (Retromotion, ecanis.shop) move to the TOP of the section — they are the primary credibility signal for the automotive audience. Active ventures (Oaza Mira, SyncNX-OS) move below.

Rule dividers:
- Top label: "automotive track record"
- Bottom label: "active ventures"

This sequence reads: "here's the automotive pedigree → here's what we're building now."

---

## 8. Contact Section

### Section label
**Current:** "contact"
**New:** "let's talk"

### Body copy (left column)
**Current:** "If you are building a venture, scaling a system or looking for a strategic partner who masters both the human and the technical game — let's talk."
**New:** "If you are an OE manufacturer, Independent Aftermarket brand or marketplace seller looking for an experienced partner in e-commerce, catalog data or product imagery — we want to hear from you."

### Response commitment (new, left column)
Added below body-copy, above `.c-list`:
```html
<p class="response-note">We reply to every serious inquiry within 24 hours.</p>
```
Styling: italic, `var(--accent-soft)`, font-size 15px, margin-top 20px.

### Contact form — new Topic Selector field

New field inserted after Company, before Message:

```html
<div class="field field-topic">
  <label>How can we help?</label>
  <div class="topic-chips">
    <button type="button" class="chip" data-value="Automotive E-Commerce">Automotive E-Commerce</button>
    <button type="button" class="chip" data-value="Product Imagery">Product Imagery</button>
    <button type="button" class="chip" data-value="API & Systems Integration">API & Systems Integration</button>
    <button type="button" class="chip" data-value="Advisory / Workshops">Advisory / Workshops</button>
    <button type="button" class="chip" data-value="Something else">Something else</button>
  </div>
  <input type="hidden" name="topic" id="f-topic">
</div>
```

Chip styling:
```css
.topic-chips { display: flex; flex-wrap: wrap; gap: 8px; padding: 16px 0 20px; }
.chip {
  background: transparent;
  border: 1px solid var(--struct);
  color: var(--muted);
  font-family: var(--sans);
  font-size: 12px;
  text-transform: uppercase;
  letter-spacing: .14em;
  padding: 10px 18px;
  border-radius: 2px;
  cursor: pointer;
  transition: border-color .3s, color .3s;
}
.chip:hover { border-color: var(--paper); color: var(--paper); }
.chip.selected { border-color: var(--accent-soft); color: var(--accent-soft); }
```

JS: clicking a chip sets `.selected` class (deselects others) and populates `#f-topic` hidden input. Topic selection is optional — no form validation required on this field.

### Microcopy under submit button
```html
<p class="form-fine">No spam. No automated replies. A real response to a real inquiry.</p>
```
Styling: font-size 12px, `var(--muted)`, margin-top 14px.

---

## 9. Design Elevation Details

| Element | Change |
|---|---|
| Hero kicker | Italic Besley, `var(--muted)`, 16px, above `.hero-h` |
| Hero CTAs | Padding `20px 36px` (from `18px 32px`) |
| Marquee speed | `40s` (from `30s`) |
| Topic chips | Premium chip UI (no native select/radio) |
| Divested badge | Muted, opacity 0.7, clearly intentional |
| Response note | Italic, `var(--accent-soft)`, left of form |
| Form microcopy | 12px muted, below submit |

---

## Out of scope

- Color palette changes (intentionally kept — distinctive and strong)
- Adding new imagery or media assets
- Backend / form processing changes (Formspree stays)
- Leadership, Thesis, AI, Principles section copy (unchanged)
