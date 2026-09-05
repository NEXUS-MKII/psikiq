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

- **`[data-cta="book"]` still has no destination** — set `BOOK_URL` in the
  script's wiring block to the GHL calendar link. It is the only unset value.
  (`[data-cta="quiz"]` is wired — see below.)
- Custom domain: psikick.ai / psikick.io once registered — Settings → Pages →
  custom domain, then a CNAME to `nexus-mkii.github.io`.
- Fonts need internet at runtime. If an offline demo is ever a risk, self-host
  the four faces in `fonts/` and swap the `@import` for local `@font-face`.
- The flying seeker and HUD readouts are desktop-only by design (mobile perf).
  It's responsive down to mobile, but the showpiece is the laptop view.
- `prefers-reduced-motion` is respected — leave that in.
- The three testimonials name real people and are marked "true, or about to be".
  Worth their sign-off before this sits on a live brand domain.

## The Prognosis diagnostic (wired, headless)

The quiz is a live hosted service; this page renders it in PsikiQ markup off
its API. The engine scores — nothing about the scoring is reimplemented here.

    Base URL   https://crisisquiz.nowgroup.co.nz     <- single const, QUIZ_BASE
    Config     GET  /quiz/api/prognosis/config
    Submit     POST /quiz/api/prognosis/submit
    Hosted     /quiz/prognosis   (used as the no-JS CTA fallback)

**Moving it to a PsikiQ host** (e.g. `quiz.psikick.ai`) is one line — change
`QUIZ_BASE` — *plus* adding the new origin to the engine's CORS allowlist at
`lmg/config/quiz_embed.json`, or the browser blocks every call.

CORS is allow-listed for `https://nexus-mkii.github.io` and verified working
from it. Note that this allows every Pages site on the account, not just
`/psikiq/` — that is how Pages origins work. A custom domain tightens it.

Verified end-to-end from the live origin: 138-option type-ahead, 12 universal
+ 3 sector questions for trades, a reveal after every answer, axis 6% -> 100%,
honeypot posted offscreen, contact skippable, and both read shapes — the
sector case (3 tiles) and the coarse-only case (1 tile, sector and gap
dropped, with a note saying why). Only 4 of 25 verticals have a sector model,
so coarse-only is the common path, not an edge case.

## Section iv — the instrument

Positions the AUBIT Business Diagnostic on **Greiner's growth model**: five
phases of growth, each ending in the crisis that forces the next (leadership,
autonomy, control, red tape, growth). Note the spelling — Larry E. Greiner,
*Evolution and Revolution as Organizations Grow*. The page uses the classic
five-phase form; the 1998 revision adds a sixth (alliances → crisis of identity)
if it's ever wanted.

The quiz it points at is not built. When it is, it should explain itself as it
runs — each question stating what it establishes and why — because that is the
positioning, not decoration.

## Brand spellings (deliberate, do not "correct")

PsikiQ (wordmark) · psikick.ai / psikick.io (domains) · Elenchus (engine,
renamed from Qollapsis 2026-09-05) · AUBIT · NOW Group

## History

Also versioned as a branch in the NOW/NEXUS workspace:
`NEXUS-MKII/dna-x-delivered` @ `psikiq-landing`, folder `psikiq-landing/`.
