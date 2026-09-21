# PsikiQ home — GHL transplant kit

Two pastes put the whole page on a GHL website page.

1. **Page settings → Custom CSS** → paste `psikiq-home.css`.
2. Add one **Section** (full width, padding 0) → one **Row** (full width, padding 0)
   → one **Column** (padding 0) → one **Custom Code** element → paste `psikiq-home.html`.

`test.html` is a harness that wraps the kit in a GHL-style 1170px container to prove
the full-bleed breakout works — open it at `/psikiq/ghl/test.html` on the Pages site.

The page root is `.pq`; every page-level style is scoped to it so GHL's own
body/heading/anchor defaults can't leak in, and `.pq` breaks out of any container
with `width:100vw; margin-left:calc(50% - 50vw)`.

Images point at the GitHub-hosted copies. To make the GHL page self-sufficient,
upload `psi-split.webp` and `psi-gold.webp` to GHL's media library and swap the
two `src` URLs.

Before the quiz works from `psikiq.io`, the engine's CORS allowlist
(`lmg/config/quiz_embed.json`) must include `https://psikiq.io` and
`https://www.psikiq.io`.
