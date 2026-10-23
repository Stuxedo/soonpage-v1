# Changelog

All notable changes to soonpage-v1 are documented here.

Since v26.10.23 this project uses [Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, with `-1`, `-2`… for later releases the same day); earlier releases used Semantic Versioning.

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
