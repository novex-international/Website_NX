# Conversion Optimization & Design Elevation — Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Optimize novex-international.com for automotive OE/IAM audience — clearer hero, stronger track record framing, improved contact form UX, logical section order.

**Architecture:** Single static HTML file (`index.html`) with embedded CSS and JS. All changes are contained within this one file. No build step, no dependencies added. Edit tool operations use exact string matching — read the file before each task to confirm strings are present as expected.

**Tech Stack:** Static HTML, embedded CSS custom properties, vanilla JS, Formspree (unchanged), GitHub Pages hosting.

---

## Files

- Modify: `index.html` (all tasks)

---

## Task 1: Add new CSS rules

**Files:**
- Modify: `index.html` — append to end of `<style>` block, before `</style>`

- [ ] **Step 1: Add all new CSS rules**

Find the closing `</style>` tag and insert the following block immediately before it:

```css
/* ===== Conversion optimization additions ===== */
.hero-kicker{font-family:var(--serif);font-style:italic;font-size:16px;color:var(--muted);margin-bottom:16px}
.hero-actions .btn{padding:20px 36px}
.nav-cta{padding:18px 64px} /* ensure nav-cta override stays */
.topic-chips{display:flex;flex-wrap:wrap;gap:8px;padding:16px 0 20px}
.chip{background:transparent;border:1px solid var(--struct);color:var(--muted);font-family:var(--sans);font-size:12px;text-transform:uppercase;letter-spacing:.14em;padding:10px 18px;border-radius:2px;cursor:pointer;transition:border-color .3s,color .3s}
.chip:hover{border-color:var(--paper);color:var(--paper)}
.chip.selected{border-color:var(--accent-soft);color:var(--accent-soft)}
.field-topic{border-bottom:1px solid var(--line);padding-bottom:4px}
.field-topic label{display:block;font-size:10px;text-transform:uppercase;letter-spacing:.24em;color:var(--muted);padding-top:16px}
.vnt .status.divested-tag{border-color:var(--muted);color:var(--muted);opacity:.7}
.response-note{font-family:var(--serif);font-style:italic;font-size:15px;color:var(--accent-soft);margin-top:20px}
.form-fine{font-size:12px;color:var(--muted);margin-top:14px}
```

- [ ] **Step 2: Verify CSS is inside `<style>` block**

Open `index.html` in a text editor and confirm the new CSS appears before `</style>` and after the last existing rule (`@media (max-width:980px){...}`). No browser check needed at this stage.

- [ ] **Step 3: Commit**

```bash
rtk git add index.html && rtk git commit -m "style: add CSS for conversion optimization elements"
```

---

## Task 2: Rename Content → Imagery

**Files:**
- Modify: `index.html` — nav link, mobile menu link, section id, section rule label

- [ ] **Step 1: Update desktop nav link**

Find:
```html
    <a href="#content">Content</a>
```
Replace with:
```html
    <a href="#imagery">Imagery</a>
```

- [ ] **Step 2: Update mobile menu link**

Find:
```html
  <a href="#content">Content</a>
```
Replace with:
```html
  <a href="#imagery">Imagery</a>
```

- [ ] **Step 3: Update section id**

Find:
```html
<section id="content" class="section">
```
Replace with:
```html
<section id="imagery" class="section">
```

- [ ] **Step 4: Update section rule label**

Find:
```html
    <div class="rule reveal"><span>content</span></div>
    <div class="sec-head">
      <h2 class="reveal d1">Product imagery that <em>sells</em> parts.</h2>
```
Replace with:
```html
    <div class="rule reveal"><span>imagery</span></div>
    <div class="sec-head">
      <h2 class="reveal d1">Product imagery that <em>sells</em> parts.</h2>
```

- [ ] **Step 5: Commit**

```bash
rtk git add index.html && rtk git commit -m "fix: rename Content to Imagery throughout (nav, section id, label)"
```

---

## Task 3: Hero section updates

**Files:**
- Modify: `index.html` — hero kicker, subtext, CTAs, meta slots

- [ ] **Step 1: Add kicker above headline**

Find:
```html
    <h1 class="hero-h reveal d1">Architecting <em>sovereign</em> systems.</h1>
```
Replace with:
```html
    <p class="hero-kicker reveal d1">E-Commerce · Catalog Data · Product Imagery</p>
    <h1 class="hero-h reveal d2">Architecting <em>sovereign</em> systems.</h1>
```

Note: the headline gets `d2` delay since kicker now takes `d1`.

- [ ] **Step 2: Update hero subtext delay and content**

Find:
```html
    <p class="hero-sub reveal d2">The e-commerce, content and data partner for OE and aftermarket businesses — and the venture studio behind AI-driven systems and high-performance leadership.</p>
```
Replace with:
```html
    <p class="hero-sub reveal d3">The e-commerce, catalog data and content partner for OE manufacturers and Independent Aftermarket brands — marketplace operations, product data standards, professional imagery and API integration. Built by operators, for operators.</p>
```

- [ ] **Step 3: Swap CTAs and update delay**

Find:
```html
    <div class="hero-actions reveal d3">
      <a class="btn btn-solid" href="#automotive">Automotive expertise <span class="arr" aria-hidden="true">→</span></a>
      <a class="btn btn-line" href="#contact">Get in touch</a>
    </div>
```
Replace with:
```html
    <div class="hero-actions reveal d4">
      <a class="btn btn-solid" href="#contact">Start a conversation <span class="arr" aria-hidden="true">→</span></a>
      <a class="btn btn-line" href="#automotive">See our services <span class="arr" aria-hidden="true">→</span></a>
    </div>
```

- [ ] **Step 4: Update hero-meta slots and delay**

Find:
```html
  <div class="hero-meta reveal d4">
    <div>Headquarters <strong>Florida, USA — operating globally</strong></div>
    <div>Active ventures <strong>Oaza Mira · SyncNX-OS</strong></div>
    <div>Domains <strong>Automotive · Commerce · AI · Leadership</strong></div>
  </div>
```
Replace with:
```html
  <div class="hero-meta reveal d4">
    <div>Expertise <strong>E-Commerce · Catalog Data · Imagery</strong></div>
    <div>Track record <strong>Built &amp; scaled automotive e-commerce from the ground up</strong></div>
    <div>Market <strong>OE &amp; Independent Aftermarket · Operating globally</strong></div>
  </div>
```

- [ ] **Step 5: Commit**

```bash
rtk git add index.html && rtk git commit -m "feat: update hero — kicker, subtext, CTAs, meta slots"
```

---

## Task 4: Marquee updates

**Files:**
- Modify: `index.html` — marquee text content and animation speed

- [ ] **Step 1: Update animation duration in CSS**

Find:
```css
.marquee-track{display:inline-flex;animation:slide 30s linear infinite}
```
Replace with:
```css
.marquee-track{display:inline-flex;animation:slide 40s linear infinite}
```

- [ ] **Step 2: Update marquee content**

Find:
```html
    <span>Automotive E-Commerce</span><span>Product Imagery</span><span>Venture Building</span><span>AI Orchestration</span><span>Spin-offs</span><span>Leadership Engineering</span>
```
Replace with:
```html
    <span>Automotive E-Commerce</span><span>Catalog Data &amp; PIM</span><span>Product Imagery</span><span>360° Photography</span><span>Marketplace Operations</span><span>API &amp; Systems Integration</span><span>OE &amp; Independent Aftermarket</span>
```

- [ ] **Step 3: Commit**

```bash
rtk git add index.html && rtk git commit -m "feat: update marquee to automotive-only terms, slower pace"
```

---

## Task 5: Automotive section copy

**Files:**
- Modify: `index.html` — automotive section headline and subtext

- [ ] **Step 1: Update section headline**

Find:
```html
      <h2 class="reveal d1">E-commerce, data &amp; content — <em>automotive to the core.</em></h2>
```
Replace with:
```html
      <h2 class="reveal d1">Marketplace operations, catalog data &amp; content — <em>built for parts manufacturers and brands.</em></h2>
```

- [ ] **Step 2: Update section subtext**

Find:
```html
      <p class="note reveal d2">Operating reality across OE and Independent Aftermarket — as advisor, operator and venture builder.</p>
```
Replace with:
```html
      <p class="note reveal d2">End-to-end expertise across OE and Independent Aftermarket — from assortment strategy and data standards to marketplace build-out and platform integration.</p>
```

- [ ] **Step 3: Commit**

```bash
rtk git add index.html && rtk git commit -m "feat: sharpen automotive section headline and subtext"
```

---

## Task 6: Imagery section copy

**Files:**
- Modify: `index.html` — imagery section subtext

- [ ] **Step 1: Update section subtext**

Find:
```html
      <p class="note reveal d2">Flexible production — in-house at your warehouse facility or within our own studio infrastructure. High-tech, efficient, cost-effective and rapidly scalable.</p>
```
Replace with:
```html
      <p class="note reveal d2">On-site at your warehouse or in our own studio — standardized sets, 360° spins and marketplace-ready output. High volume, fast turnaround, immediately deployable.</p>
```

- [ ] **Step 2: Commit**

```bash
rtk git add index.html && rtk git commit -m "feat: update imagery section subtext for clarity"
```

---

## Task 7: Ventures section — full rewrite

**Files:**
- Modify: `index.html` — ventures section (labels, headline, subtext, venture order, badges)

This task replaces the entire `<section id="ventures">` block. The automotive ventures (Retromotion, ecanis.shop) move to the top as the primary credibility signal; active ventures (Oaza Mira, SyncNX-OS) move below.

- [ ] **Step 1: Replace the entire ventures section**

Find:
```html
<!-- ============ VENTURES ============ -->
<section id="ventures" class="section">
  <div class="aurora dim" aria-hidden="true"><i></i><i></i><i></i></div>
  <div class="wrap">
    <div class="rule reveal"><span>active ventures</span></div>
    <div class="sec-head">
      <h2 class="reveal d1">We build, operate &amp; <em>spin off.</em></h2>
      <p class="note reveal d2">Not theory. Operating ventures, engineered in-house and built for independence.</p>
    </div>

    <div class="vnt live reveal">
      <a class="vnt-row" href="https://www.oaza-mira.app" target="_blank" rel="noopener">
        <span class="field-tag">remembrance</span>
        <h3>Oaza Mira <span class="dom">oaza-mira.app</span></h3>
        <p>Re-architecting the global diaspora infrastructure for memorial care. AI-driven quality assurance meets emotional proximity — connecting families, service providers and memorial sites through transparency, GPS verification and trust.</p>
        <span class="status live-tag">Live</span>
      </a>
    </div>
    <div class="vnt live reveal d1">
      <a class="vnt-row" href="https://sync-nx.co" target="_blank" rel="noopener">
        <span class="field-tag">commerce</span>
        <h3>SyncNX-OS <span class="dom">sync-nx.co</span></h3>
        <p>The Commerce Operating System. Decoupling complex e-commerce structures through enterprise-grade API orchestration — returning data sovereignty to brands and suppliers. Built for billion-dollar organizations and ambitious mid-market players.</p>
        <span class="status live-tag">Live</span>
      </a>
    </div>

    <div class="rule mid reveal"><span>earlier ventures</span></div>

    <div class="vnt live reveal">
      <div class="vnt-row">
        <span class="field-tag">aftermarket</span>
        <h3>Retromotion <span class="dom"><a href="https://retromotion.com" target="_blank" rel="noopener">retromotion.com</a> &nbsp;·&nbsp; <a href="https://www.ebay.de/str/retromotion" target="_blank" rel="noopener">eBay store</a></span></h3>
        <p>E-commerce platform for automotive spare parts and accessories — OE quality across all vehicle brands, built for the independent aftermarket. Initiated and co-founded. 900,000+ items sold via its eBay store.</p>
        <span class="status">Co-Founder</span>
      </div>
    </div>
    <div class="vnt live reveal d1">
      <div class="vnt-row">
        <span class="field-tag">digitization</span>
        <h3>ecanis.shop <span class="dom"><a href="https://ecanis.shop" target="_blank" rel="noopener">ecanis.shop</a> &nbsp;·&nbsp; <a href="https://www.ebay.de/str/canislupusdigital" target="_blank" rel="noopener">eBay store</a></span></h3>
        <p>Digitalization venture and e-commerce retailer in the independent aftermarket — founded, built and led as CEO and shareholder. 320,000+ items sold via its eBay store.</p>
        <span class="status">Founder &amp; CEO</span>
      </div>
    </div>
  </div>
</section>
```

Replace with:
```html
<!-- ============ VENTURES ============ -->
<section id="ventures" class="section">
  <div class="aurora dim" aria-hidden="true"><i></i><i></i><i></i></div>
  <div class="wrap">
    <div class="rule reveal"><span>track record</span></div>
    <div class="sec-head">
      <h2 class="reveal d1">Built from the ground up. <em>Operated. Sold.</em></h2>
      <p class="note reveal d2">First-hand experience building and scaling automotive e-commerce operations — not consulting from the outside, but operating from within.</p>
    </div>

    <div class="rule mid reveal"><span>automotive track record</span></div>

    <div class="vnt live reveal">
      <div class="vnt-row">
        <span class="field-tag">aftermarket</span>
        <h3>Retromotion <span class="dom"><a href="https://retromotion.com" target="_blank" rel="noopener">retromotion.com</a> &nbsp;·&nbsp; <a href="https://www.ebay.de/str/retromotion" target="_blank" rel="noopener">eBay store</a></span></h3>
        <p>E-commerce platform for automotive spare parts and accessories — OE quality across all vehicle brands, built for the independent aftermarket. Initiated and co-founded. 900,000+ items sold via its eBay store.</p>
        <span class="status divested-tag">Divested</span>
      </div>
    </div>
    <div class="vnt live reveal d1">
      <div class="vnt-row">
        <span class="field-tag">digitization</span>
        <h3>ecanis.shop <span class="dom"><a href="https://ecanis.shop" target="_blank" rel="noopener">ecanis.shop</a> &nbsp;·&nbsp; <a href="https://www.ebay.de/str/canislupusdigital" target="_blank" rel="noopener">eBay store</a></span></h3>
        <p>Digitalization venture and e-commerce retailer in the independent aftermarket — founded, built and led as CEO and shareholder. 320,000+ items sold via its eBay store.</p>
        <span class="status divested-tag">Divested</span>
      </div>
    </div>

    <div class="rule mid reveal"><span>active ventures</span></div>

    <div class="vnt live reveal">
      <a class="vnt-row" href="https://www.oaza-mira.app" target="_blank" rel="noopener">
        <span class="field-tag">remembrance</span>
        <h3>Oaza Mira <span class="dom">oaza-mira.app</span></h3>
        <p>Re-architecting the global diaspora infrastructure for memorial care. AI-driven quality assurance meets emotional proximity — connecting families, service providers and memorial sites through transparency, GPS verification and trust.</p>
        <span class="status live-tag">Live</span>
      </a>
    </div>
    <div class="vnt live reveal d1">
      <a class="vnt-row" href="https://sync-nx.co" target="_blank" rel="noopener">
        <span class="field-tag">commerce</span>
        <h3>SyncNX-OS <span class="dom">sync-nx.co</span></h3>
        <p>The Commerce Operating System. Decoupling complex e-commerce structures through enterprise-grade API orchestration — returning data sovereignty to brands and suppliers. Built for billion-dollar organizations and ambitious mid-market players.</p>
        <span class="status live-tag">Live</span>
      </a>
    </div>
  </div>
</section>
```

- [ ] **Step 2: Commit**

```bash
rtk git add index.html && rtk git commit -m "feat: reframe ventures as track record, automotive ventures first"
```

---

## Task 8: Contact section — copy, form, JS

**Files:**
- Modify: `index.html` — contact section label, headline, body copy, response note, form fields, microcopy, JS

- [ ] **Step 1: Replace the entire contact section**

Find:
```html
<!-- ============ CONTACT ============ -->
<section id="contact" class="section">
  <div class="aurora dim" aria-hidden="true"><i></i><i></i><i></i></div>
  <div class="wrap">
    <div class="rule reveal"><span>contact</span></div>
    <div class="cols">
      <div>
        <h2 class="reveal d1">Let's build something that <em>lasts.</em></h2>
        <p class="body-copy reveal d2">If you are building a venture, scaling a system or looking for a strategic partner who masters both the human and the technical game — let's talk.</p>
        <div class="c-list">
          <div class="c-row reveal"><span>Company</span>NOVEX INTERNATIONAL LLC · Florida, USA</div>
          <div class="c-row reveal d1"><span>Contact</span>Exclusively via the inquiry form — we reply to every serious request.</div>
          <div class="c-row reveal d2"><span>Ventures</span><a href="https://www.oaza-mira.app" target="_blank" rel="noopener">oaza-mira.app</a> &nbsp;·&nbsp; <a href="https://sync-nx.co" target="_blank" rel="noopener">sync-nx.co</a></div>
        </div>
      </div>
      <form action="https://formspree.io/f/xnjygllz" method="POST" class="reveal d2" id="cform">
        <p class="hp" aria-hidden="true"><label>Leave this field empty<input type="text" name="_gotcha" tabindex="-1" autocomplete="off"></label></p>
        <div class="field"><label for="f-name">Name</label><input id="f-name" name="name" type="text" autocomplete="name" required></div>
        <div class="field"><label for="f-email">Email</label><input id="f-email" name="email" type="email" autocomplete="email" required></div>
        <div class="field"><label for="f-company">Company <span style="opacity:.6">(optional)</span></label><input id="f-company" name="company" type="text" autocomplete="organization"></div>
        <div class="field"><label for="f-msg">Message</label><textarea id="f-msg" name="message" required></textarea></div>
        <button class="btn btn-solid" type="submit">Send inquiry <span class="arr" aria-hidden="true">→</span></button>
        <p id="form-note" role="status" aria-live="polite">Thank you — your message has been prepared. We will get back to you shortly.</p>
      </form>
    </div>
  </div>
</section>
```

Replace with:
```html
<!-- ============ CONTACT ============ -->
<section id="contact" class="section">
  <div class="aurora dim" aria-hidden="true"><i></i><i></i><i></i></div>
  <div class="wrap">
    <div class="rule reveal"><span>let's talk</span></div>
    <div class="cols">
      <div>
        <h2 class="reveal d1">Let's build something that <em>lasts.</em></h2>
        <p class="body-copy reveal d2">If you are an OE manufacturer, Independent Aftermarket brand or marketplace seller looking for an experienced partner in e-commerce, catalog data or product imagery — we want to hear from you.</p>
        <p class="response-note reveal d2">We reply to every serious inquiry within 24 hours.</p>
        <div class="c-list">
          <div class="c-row reveal"><span>Company</span>NOVEX INTERNATIONAL LLC · Florida, USA</div>
          <div class="c-row reveal d1"><span>Contact</span>Exclusively via the inquiry form below.</div>
          <div class="c-row reveal d2"><span>Ventures</span><a href="https://www.oaza-mira.app" target="_blank" rel="noopener">oaza-mira.app</a> &nbsp;·&nbsp; <a href="https://sync-nx.co" target="_blank" rel="noopener">sync-nx.co</a></div>
        </div>
      </div>
      <form action="https://formspree.io/f/xnjygllz" method="POST" class="reveal d2" id="cform">
        <p class="hp" aria-hidden="true"><label>Leave this field empty<input type="text" name="_gotcha" tabindex="-1" autocomplete="off"></label></p>
        <div class="field"><label for="f-name">Name</label><input id="f-name" name="name" type="text" autocomplete="name" required></div>
        <div class="field"><label for="f-email">Email</label><input id="f-email" name="email" type="email" autocomplete="email" required></div>
        <div class="field"><label for="f-company">Company <span style="opacity:.6">(optional)</span></label><input id="f-company" name="company" type="text" autocomplete="organization"></div>
        <div class="field-topic">
          <label>How can we help? <span style="opacity:.6">(optional)</span></label>
          <div class="topic-chips">
            <button type="button" class="chip" data-value="Automotive E-Commerce">Automotive E-Commerce</button>
            <button type="button" class="chip" data-value="Product Imagery">Product Imagery</button>
            <button type="button" class="chip" data-value="API &amp; Systems Integration">API &amp; Systems Integration</button>
            <button type="button" class="chip" data-value="Advisory / Workshops">Advisory / Workshops</button>
            <button type="button" class="chip" data-value="Something else">Something else</button>
          </div>
          <input type="hidden" name="topic" id="f-topic">
        </div>
        <div class="field"><label for="f-msg">Message</label><textarea id="f-msg" name="message" required></textarea></div>
        <button class="btn btn-solid" type="submit">Send inquiry <span class="arr" aria-hidden="true">→</span></button>
        <p class="form-fine">No spam. No automated replies. A real response to a real inquiry.</p>
        <p id="form-note" role="status" aria-live="polite">Thank you — your message has been prepared. We will get back to you shortly.</p>
      </form>
    </div>
  </div>
</section>
```

- [ ] **Step 2: Add chip JS — insert before the closing `})();` of the IIFE**

Find (the last few lines of the script, near the end):
```js
  var form=document.getElementById('cform');
  var formLoadedAt=Date.now();
```
Replace with:
```js
  /* topic chip selector */
  document.querySelectorAll('.chip').forEach(function(chip){
    chip.addEventListener('click',function(){
      document.querySelectorAll('.chip').forEach(function(c){c.classList.remove('selected')});
      chip.classList.add('selected');
      document.getElementById('f-topic').value=chip.getAttribute('data-value');
    });
  });

  var form=document.getElementById('cform');
  var formLoadedAt=Date.now();
```

- [ ] **Step 3: Commit**

```bash
rtk git add index.html && rtk git commit -m "feat: improve contact section — copy, response note, topic chips, microcopy"
```

---

## Task 9: Section reordering

**Files:**
- Modify: `index.html` — move Founder and Contact sections earlier; move Leadership section later

**Current order** (after imagery): Ventures → Leadership → Thesis → AI → Principles → Founder → Contact

**Target order**: Ventures → Founder → Contact → Thesis → AI → Leadership → Principles

This task works best as a cut-and-paste of entire section blocks. Read the file first to get exact whitespace.

- [ ] **Step 1: Move Founder section — delete from current position**

Find and delete the entire founder section by replacing it with a single blank comment placeholder:

Find:
```html
<!-- ============ FOUNDER (minimal) ============ -->
<section id="founder" class="section">
  <div class="wrap">
    <div class="rule reveal"><span>initiator</span></div>
    <div class="row">
      <h2 class="reveal d1">Initiated by <em>Manuel Schuetterle.</em></h2>
      <div class="reveal d2">
        <p>Strategic thinker, system architect and venture builder. Manuel has spent the last decade building technology-driven businesses, implementing AI infrastructure and mentoring 50+ entrepreneurs across Europe and beyond.</p>
        <p class="principle-line">His work is guided by one principle: build systems that outlast the founder.</p>
        <a class="btn btn-line" href="https://linkedin.com/in/manuel-schuetterle" target="_blank" rel="noopener">LinkedIn <span class="arr" aria-hidden="true">→</span></a>
      </div>
    </div>
  </div>
</section>
```
Replace with:
```html
<!-- FOUNDER MOVED — see after ventures -->
```

- [ ] **Step 2: Move Contact section — delete from current position**

Find (immediately after the founder placeholder from step 1, this is the contact section):
```html
<!-- ============ CONTACT ============ -->
<section id="contact" class="section">
```

Note: Do NOT delete the contact section yet — you need to know its content. Instead, in step 3 you will insert both sections at the new position and then in step 4 delete them.

**Alternative approach (safer):** Do this in your editor/IDE as a cut-paste operation on the HTML file directly, placing the founder and contact blocks immediately after `</section>` of the ventures section, then removing the originals. This is easier than using find-replace for large blocks.

After the operation, the order should be:
```
</section>  ← end of ventures
<!-- ============ FOUNDER (minimal) ============ -->
<section id="founder">...</section>
<!-- ============ CONTACT ============ -->
<section id="contact">...</section>
<!-- ============ THESIS ============ -->
<section id="thesis">...</section>
...
<!-- ============ LEADERSHIP ============ -->  ← moved here from earlier
<section id="leadership">...</section>
<!-- ============ PRINCIPLES ============ -->
<section id="principles">...</section>
```

- [ ] **Step 3: Move Leadership section**

After the founder/contact move, Leadership currently sits between Ventures and Thesis. Move the entire `<section id="leadership">` block from its current position to after `</section>` of the AI section.

Leadership section to move:
```html
<!-- ============ LEADERSHIP ============ -->
<section id="leadership" class="section">
  <div class="wrap">
    <div class="rule reveal"><span>leadership</span></div>
    <div class="cols">
      ...entire section content...
    </div>
  </div>
</section>
```

Target position: between `</section>` of `#ai` and `<section id="principles">`.

- [ ] **Step 4: Verify order in file**

After the reordering, scan the file top-to-bottom and confirm section order:
1. `id="top"` (hero)
2. `.marquee`
3. `id="automotive"`
4. `id="imagery"`
5. `id="ventures"`
6. `id="founder"`
7. `id="contact"`
8. `id="thesis"`
9. `id="ai"`
10. `id="leadership"`
11. `id="principles"`

- [ ] **Step 5: Commit**

```bash
rtk git add index.html && rtk git commit -m "refactor: reorder sections — founder+contact after ventures, leadership after ai"
```

---

## Task 10: Verify in browser + final commit

**Files:**
- Read: `index.html` — final state check

- [ ] **Step 1: Open site locally**

```powershell
Start-Process "C:\Users\manue\Website_NX\index.html"
```

- [ ] **Step 2: Verify hero**

Check:
- Kicker "E-Commerce · Catalog Data · Product Imagery" appears above headline in italic muted serif
- Subtext reads "Built by operators, for operators." at end
- Primary CTA is dark/filled "Start a conversation" → scrolls to contact
- Secondary CTA is outlined "See our services" → scrolls to automotive
- Hero-meta shows: Expertise / Track record / Market

- [ ] **Step 3: Verify marquee**

Check: No "Venture Building", "Spin-offs", or "Leadership Engineering" in the scrolling strip. Animation feels slower/more premium than before.

- [ ] **Step 4: Verify section order on scroll**

Scroll through the full page. Confirm order: Automotive → Imagery → Track Record (ventures) → Initiator (founder) → Let's talk (contact) → Thesis → AI → Leadership → Principles.

- [ ] **Step 5: Verify ventures section**

Check:
- Section label reads "track record"
- Headline: "Built from the ground up. Operated. Sold."
- First divider: "automotive track record" with Retromotion and ecanis.shop showing "Divested" badge (muted, slightly faded)
- Second divider: "active ventures" with Oaza Mira and SyncNX-OS showing "Live" badge

- [ ] **Step 6: Verify contact form**

Check:
- Section label reads "let's talk"
- Body copy addresses OE/IAM audience specifically
- Response note "We reply to every serious inquiry within 24 hours." appears in accent-soft italic left of form
- Topic chips appear: 5 chips, click one — it highlights in accent color, others deselect
- Microcopy "No spam. No automated replies." appears below submit button

- [ ] **Step 7: Check mobile (resize browser to < 980px)**

Check:
- Nav hamburger works, "Imagery" appears in mobile menu
- Hero kicker visible
- Topic chips wrap cleanly on mobile
- All sections in correct order

- [ ] **Step 8: Final commit**

```bash
rtk git add index.html && rtk git commit -m "chore: verified conversion optimization — all tasks complete"
```

---

## Self-Review Notes

**Spec coverage:**
- ✅ Nav: Content → Imagery (Task 2)
- ✅ Hero kicker (Task 3)
- ✅ Hero subtext + "built by operators" (Task 3)
- ✅ Hero CTA order + padding (Task 3 + Task 1 CSS)
- ✅ Hero-meta slots (Task 3)
- ✅ Marquee content + speed (Task 4)
- ✅ Automotive headline + subtext (Task 5)
- ✅ Imagery section subtext (Task 6)
- ✅ Section reorder (Task 9)
- ✅ Ventures reframe — label, headline, subtext (Task 7)
- ✅ Automotive ventures first + Divested badge (Task 7)
- ✅ Contact label, headline, body copy (Task 8)
- ✅ Response commitment (Task 8)
- ✅ Topic chips + hidden input + JS (Task 8)
- ✅ Form microcopy (Task 8)
- ✅ All new CSS (Task 1)

**No placeholders found.**

**Type consistency:** No shared function signatures across tasks. JS chip selector uses `.chip`, `.selected`, `#f-topic` consistently with HTML and CSS definitions.
