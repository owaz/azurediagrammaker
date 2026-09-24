# Host-specific delivery notes

Optional reference for `azure-architecture-diagram-maker`. `SKILL.md` is host-neutral; consult this file only when the current host matches one of the sections below. Every rule in `SKILL.md` (sanitised self-contained SVG, no overwriting sources, real returned URIs only, never claim an uninspected or clipped preview) still applies.

## Scout

- **Destination resolution:** prefer workspace tools for workspace documents when they are exposed; otherwise use permitted local artifact tools. Resolve bare input filenames through the active workspace first — the process directory is not the workspace. If input cannot be located without workspace access, ask for an accessible path.
- **Artifact URIs:** use `workspace://` URIs for workspace artifacts, or renderable execution-directory PNGs with URL-encoded `file:///` paths. Use only URIs the host actually returned; never invent a path or download link.

## Cowork / Copilot-style hosts

- Build under the session's scratch folder and publish through the host's artifact tools (create/copy) so the user receives a real deliverable link; a scratch copy the user cannot see is not delivery.
- Inline previews are available only where the host renders returned image artifacts; otherwise deliver the PNG as a file and say the inline preview is unavailable.

## Other hosts

Each host has its own attachment scheme (returned artifact IDs, signed URLs, chat attachments). Discover it from the live tool schemas and use whatever the tool actually returns. Do not assume a browser tool can read local files, and do not assume screenshots land on the local filesystem — transfer tool-managed screenshots through supported artifact tools or expose their actual accessible URIs.

## macOS Quick Look and similar OS preview fallbacks

Do not use automatic OS preview/thumbnail generation (e.g. macOS Quick Look) as a PNG source: rectangular SVGs can come back as cropped square previews. Report "PNG preview unavailable in this host" rather than deliver clipped artwork. Cropping again cannot restore lost content.

## Playwright / browser execution tools

The full procedure lives in `SKILL.md` → *Rasterization without a repository*. Summary: fresh blank page (never an authenticated application's tab), minimal document with `body { margin: 0 }` and the SVG `display: block`, await `document.fonts.ready` and embedded-image decoding, measure the root SVG, capture that element, inspect the raster. Pass sanitised SVG as a data string — never interpolate untrusted text into executable code — and do not depend on `require()`, dynamic `import()`, filesystem modules, or server-side packages being exposed. Avoid CSS `max-width` rules that silently scale or crop. Close only tabs/contexts the task created.
