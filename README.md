# The Scratch Kitchen by Gallo's — Static Website Clone

A fully self-contained, static copy of the Scratch Kitchen website. Every page,
stylesheet, font, image, and the menu PDF is included locally — no server, build
step, or internet connection required.

## How to use
Open `index.html` in any browser, or host the folder on any static host
(Netlify, Vercel, GitHub Pages, S3, Apache/Nginx). All links are relative.
For best results, serve it locally:

    cd scratch-kitchen-clone
    python3 -m http.server 8000   # then visit http://localhost:8000

## What's restored from the original Next.js app
The original is a Next.js site; the capture held server-rendered HTML plus a
JavaScript runtime that doesn't work as plain files. To make a clone that "just
works", the following were rebuilt in a single small `assets/js/site.js`
(no framework, ~5 KB):

- **Desktop hover mega-menu** — the Menu / Private Events / Order & Reserve /
  Our Story dropdowns, with their category columns, sub-notes, and feature
  cards, recreated exactly from the original navigation data.
- **Mobile hamburger drawer** — open/close + animated icon.
- **Scroll-reveal fade-ins** — content uses an `opacity:0` reveal class that the
  original animated in on scroll; restored with an IntersectionObserver (with a
  safety net so nothing is ever left blank).
- **Header scroll state** — transparent at the top, solid once scrolled.

Images were also repointed from Next's server-side optimizer
(`/_next/image?url=…`) to the real local files so they load offline.

External links (Facebook, Instagram, Google Maps embed) still point to the live
services, as in the original.

## Note
This reproduces an existing site's published front end for archival/offline
reference or as a starting point for the site's owner. Make sure you have the
right to reuse the brand, images, and content before publishing it anywhere.
