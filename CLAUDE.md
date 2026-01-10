# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for displaying Narcotics Anonymous (NA) meetings in New Jersey, hosted at gardenstatena.org. It uses the BMLT (Basic Meeting List Toolbox) ecosystem with CroutonJS to display meeting information.

## Architecture

- **Single-page static site**: The entire application is contained in `index.html`
- **CroutonJS**: Third-party library loaded from CDN (`@bmlt-enabled/croutonjs`) that renders meeting data
- **BMLT Root Server**: Fetches meeting data from `https://tomato.bmltenabled.org/main_server/`
- **Google Maps Integration**: Uses Google Maps API for meeting location display

## Key Configuration (in index.html)

The Crouton instance is configured with:
- `custom_query`: Filters for NJ meetings, excludes service body 490 (Western Australia)
- `default_filter_dropdown`: Defaults to in-person venues
- `button_filters`: City-based filtering via `location_municipality`
- `theme`: "florida-nights"
- Day filtering via URL parameter `?day=1-7` (1=Sunday through 7=Saturday)

## Development

No build process - edit `index.html` directly. To test locally, open `index.html` in a browser or use a local server.

## Deployment

GitHub Pages deployment to gardenstatena.org (configured via CNAME file).
