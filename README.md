# Website Sign Up

Standalone newsletter signup page for CL Growth Academy, built on the brand's
existing design tokens (Workshop Ink / Oxblood / Paper / Mustard / Cream —
Alfa Slab One, Yellowtail, Work Sans). Subscribes to
`https://clgrowth.beehiiv.com/subscribe`.

Copied out of the main [cl-growth-academy-website](https://github.com/Killobite2/cl-growth-academy-website)
project so it can be deployed and tracked on its own.

## Keeping it in sync

`newsletter.html`, `css/styles.css` and `js/main.js` are **straight copies**
from the main repo. They used to be trimmed to just what this page needs, and
that is what broke it: the page picked up `.form-pill`, `.sr-only`,
`.section-callout` and the drawn-tick success state upstream, none of which
came across, so eight classes were live in the markup with no CSS behind
them. Whole files cost about 55KB more and remove the failure mode.

To sync, copy those three files over, then re-point the two self-references
this repo owns:

- `<link rel="canonical">` and `og:url` &rarr; `website-sign-up.vercel.app`

Everything else, the brand link included, still points at the main site on
purpose. `vercel.json` rewrites `/` to `/newsletter.html`, since there is no
`index.html` here.

Open `newsletter.html` directly, or serve the folder with any static file
server (e.g. `python3 -m http.server`).
