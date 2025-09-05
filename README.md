# Oushadhi Path — Ayurvedic Provenance Portal (Frontend)

Modern, responsive static frontend to trace the provenance of Ayurvedic herbal products on blockchain. Includes Home, Trace (QR/Product Code input), Details (map + timeline), and About pages with a shared navbar and footer.

## Quick start

1) Open `index.html` directly in your browser, or serve the folder via a static server:

Windows PowerShell:
```
cd "C:\Users\Sumit Sengar\Desktop\Oushadhi Path"
python -m http.server 8000
```
Then visit `http://localhost:8000`.

## Pages

- Home (`index.html`): Hero with Ayurvedic theme and CTAs.
- Trace (`input.html`): Enter a batch ID or simulate a QR scan.
- Details (`details.html`): Map placeholder, timeline of collection/processing/tests, product and community info.
- About (`about.html`): Blockchain, FHIR, sustainability, and contact.

## Features

- Mobile-first layout, sticky translucent navbar, accessible buttons/inputs.
- Mock data rendering in `assets/js/main.js` when navigating to `details.html?batch=...`.
- Utility CSS classes in `assets/css/styles.css` for consistent spacing and layout.

## Simulate a trace

1) Go to `Trace`.
2) Click "Use Demo Batch" or "Simulate Scan".
3) Click "View Traceability" to navigate to details with `?batch=BATCH-AYU-2025-0001`.

## Integrating a real QR scanner (optional)

Replace the placeholder with a web scanner library (e.g., `@zxing/browser`). On successful scan, call `goToDetailsWithBatch(scannedValue)`.

## Hooking to a backend

Replace mock data in `renderProvenanceIfPresent()` with an API fetch to your blockchain indexer or gateway. Suggested endpoint: `GET /api/provenance?batch=...` returning collection events, processing steps, quality tests (ideally FHIR resources/bundles or normalized JSON).

## Tech notes

- Styling: custom CSS with CSS variables, minimal utilities, and modern effects.
- Maps: current placeholder shows GPS and location text; integrate Leaflet/Mapbox/Google Maps if desired.
- Data: FHIR-compatible structure recommended; blockchain: Hyperledger Fabric.

## License

MIT for the frontend portion unless specified otherwise by the project owner.


