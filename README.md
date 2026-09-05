# PsikiQ

Landing page for PsikiQ — *we see what your market can't*.

**Live:** https://nexus-mkii.github.io/psikiq/

Single self-contained static page. No build step, no framework, no package.json.
The only runtime dependency is Google Fonts (Oswald, Michroma, Chakra Petch,
JetBrains Mono). The ψ mark, the flying Q-orb seeker, the brushed-steel texture,
the wave→particle collapse and the turning-book testimonials are all CSS/SVG/JS
inside `index.html`.

Deploy = serve `index.html`. GitHub Pages builds from `main` at root.

## Open items

- CTA `Book the diagnostic` points at `href="#"` — swap for the GHL calendar /
  booking URL before this takes real traffic.
- Custom domain: psikick.ai / psikick.io once registered — Settings → Pages →
  custom domain, then a CNAME to `nexus-mkii.github.io`.
- Fonts need internet at runtime. If an offline demo is ever a risk, self-host
  the four faces in `fonts/` and swap the `@import` for local `@font-face`.
- The flying seeker and HUD readouts are desktop-only by design (mobile perf).
  It's responsive down to mobile, but the showpiece is the laptop view.
- `prefers-reduced-motion` is respected — leave that in.
- The three testimonials name real people and are marked "true, or about to be".
  Worth their sign-off before this sits on a live brand domain.

## Brand spellings (deliberate, do not "correct")

PsikiQ (wordmark) · psikick.ai / psikick.io (domains) · Qollapsis (engine) ·
AUBIT · NOW Group

## History

Also versioned as a branch in the NOW/NEXUS workspace:
`NEXUS-MKII/dna-x-delivered` @ `psikiq-landing`, folder `psikiq-landing/`.
