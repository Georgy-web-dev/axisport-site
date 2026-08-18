# Axis Port LTD — [axisport.uk](https://axisport.uk)

Five-page marketing site for a London commodities trading company.

No build step, no dependencies, no CMS, no JavaScript framework. Clone it and
open `index.html` — that is the whole development setup.

```
index.html  about.html  products.html  contact.html  privacy.html  404.html
css/style.css      ← every style, one file
img/               ← photography, logo-mark.svg, og-card.jpg (link preview)
favicon.svg  robots.txt  sitemap.xml
```

Deployed as static files on Cloudflare Pages.

## How it is built

**One stylesheet.** Every rule lives in `css/style.css`, driven by custom
properties at the top. Brand purple is `--purple: #6d28d9` — change it there and
the whole site follows.

**A mobile nav with no JavaScript.** The menu is a hidden checkbox and a `<label>`
styled as the burger; the open state is a sibling selector on `:checked`. It
keeps working with JS disabled, and there is no toggle handler to get out of sync
with the DOM.

**A contact form with no backend.** Submitting composes a `mailto:` with the
fields pre-filled and hands off to the visitor's mail client. A five-page
brochure site does not justify a server, a form service subscription, or the
GDPR surface of storing submissions — the message goes straight from the sender
to the recipient and nothing sits in between.

**Header and footer are duplicated per page** rather than templated. At five
pages that is cheaper to read and to change than introducing a static site
generator and a build step; past roughly ten it stops being true.

**`img/og-card.jpg`** is the WhatsApp / Telegram / LinkedIn link preview.
Regenerate it if the tagline or the logo changes.

## Swapping the form for a hosted service

If submissions ever need to be logged rather than emailed, point the form at
Formspree or host on Netlify and use Netlify Forms, then delete the script block
at the bottom of `contact.html`. Nothing else depends on it.

## License

Code is free to read and reuse. The Axis Port name, logo and copy belong to the
company and the photography is licensed to it — neither is covered.
