# Changelog

All notable changes to soonpage-v1 are documented here.

Since v26.10.23 this project uses [Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, with `-1`, `-2`… for later releases the same day); earlier releases used Semantic Versioning.

## v26.11.13-1

### Fixed

- **Registered office country.** The Imprint page now gives the full registered office, ending in "United Kingdom": 124 City Road, London, EC1V 2NX, England, United Kingdom.

## v26.11.13

### Changed

- **New registered office.** The Imprint page now shows Stux Group Ltd's new registered office, 124 City Road, London, EC1V 2NX, England (it was 82a James Carter Road, Mildenhall). The company number and "Registered in England and Wales" are unchanged.

## v26.11.12

### Fixed

- **The commit script's push hint** now names the current branch (`test`) and the release tag, and reminds you to open the pull request into `main`. It used to say to push to `main`.

## v26.11.07-1

### Fixed

- **CI passes again.** The HTML check rejected the Discord link preview's `<script id="discord:component-embed">`, as its id has a colon. Discord looks for that exact id, so `.htmlvalidate.json` now allows it (`valid-id` in relaxed mode) instead of renaming it. CI had failed on every push since the preview was added.

## v26.11.07

### Changed

- **All rights reserved.** The License section now reads "Copyright (c) 2026 Stux.Group. All rights reserved. This repository is not licensed for reuse or redistribution", and a `LICENSE` file says the same.

## v26.11.06

### Changed

- **Work happens on `test`.** Changes reach `main` only through a pull request from `test` (CI now runs on pushes to `test` too), and releases are made and tagged on `test`. CONTRIBUTING has a Branches section, and the README's Versioning section says so.

## v26.10.26

### Security

- CI uses Node.js 24 instead of the end-of-life Node.js 20, which has no fix for the Brotli decoder vulnerability CVE-2026-111497

## v26.10.23-1

### Added

- A full icon set from the brand's own icon: `favicon.ico` (16, 32 and 48px) and `apple-touch-icon.png` at the site root, and a `site.webmanifest` with 192px, 512px and maskable icons, so the page has a proper icon in browser tabs, bookmarks and on phone home screens (the home-screen icons sit on a white background, as iOS would otherwise fill the icon's transparent corners with black). Every page lists the same icons, served from this site instead of the media host
- Discord link previews: sharing any page in Discord shows a custom preview in the Stuxedo brand colour, with the page's name, what it is and a few links (Stuxedo, Status, Dash on the coming-soon page; the legal pages link back to Boring Legal Stuff). Names and descriptions show as plain text, and the 404 page has none. They're pre-built into each page by `python scripts/build-discord-embeds.py`, which `scripts/build-sitemap.py` now runs too
- `tests/site.sh`, which checks that every preview is valid JSON under Discord's 3,000-byte limit and none is on the 404 page, that the icon files have the right sizes, and that every page's `<head>` carries the same icon tags. CI runs it

## v26.10.23

### Added

- `tests/version.sh`, which checks that `VERSION.md` is a valid Date Version, a real calendar date not in the future, and the same as the newest entry in this changelog

### Changed

- Switched from Semantic Versioning to [Date Versioning](https://datevers.ing): releases are numbered by their UTC release date as `YY.MM.DD`, with `-1`, `-2`… for later releases the same day. This release follows v1.0.2
- `commit.sh` and `commit.bat` refuse a `VERSION.md` that isn't a valid Date Version or is dated in the future (UTC), and warn when it's dated before today
- `README.md` and `CONTRIBUTING.md` describe Date Versioning and the release steps

## v1.0.2

### Fixed

- The footer's copyright line had a second, hidden copy of the © icon inside its screen-reader text; it's gone, leaving the visible icon and a plain "©" for screen readers. Nothing changes on screen

## v1.0.1

### Fixed

- The footer no longer says "Stuxedo is operated by Stux.Cloud, which is operated by Stux Group Ltd."; that belongs on the Imprint, which still says who operates the page. The copyright line names Stuxedo instead of Stux.Group ("© 2026 Stuxedo. All rights reserved."), matching the live pages

## v1.0.0

### Added

- Archived [Stuxedo/soonpage](https://github.com/Stuxedo/soonpage) at commit `529174e` (`v1.2.2`), the last state before Stuxedo's rebrand to the tuxedo-cat logo (neon `#4bf708` on dark, deep `#032f14` on light), preserving history up to that point as this repository's own `main` branch

### Changed

- Served from `soonpage-v1.stuxedo.net` instead of `soonpage.stuxedo.net` (CNAME, canonical URLs, sitemap and robots.txt)
- Logo, icon and favicon now point at the archived assets under `https://global.media.stuxedo.com/v1/` instead of the live Stuxedo brand assets, which have been replaced
- README and CONTRIBUTING describe this repository as an archive
