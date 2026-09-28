# FS Softwares Solution Explorer

Private, responsive, dependency-free static website for the established 20-system software library.

## Run

`npm start` then open http://localhost:3000. Requires Python 3.

## Behavior

- Browse 20 canonical profiles, filter by 14 industry contexts, and search names, modules and original pain points.
- Select customer priorities. Rank eligible systems by covered-priority count; break ties by industry relevance then library order.
- Keep a three-system comparison shortlist while changing filters. Browser local storage preserves the browsing context and shortlist.
- Generate, copy or download a concise discussion brief. Explicit shortlist takes precedence over automatic suggestions. Uncovered priorities are shown as scope gaps.
- Native accessible dialogs and keyboard controls support profile inspection and comparison. No external assets, analytics or CRM integration. Account records are held separately from the catalog.

## Content provenance

System names, market, summary, original pain points, proposed capabilities, recommended modules and integration flows are extracted from `FS_Softwares_2026_Master_Software_Library_Batch_01.docx`, current library content read on 2026-09-25. Source library identifier: `libfile_144c1bde82908191b2ca1c1476342124`.

The 2026–2036 Master Business Plan V2 also confirms the 20-product portfolio. No financing, personal details or client records are embedded in this app.

Industry associations, priority mappings, discovery questions and suggested demo workflows are editorial guidance derived from the source. They are not assertions of release readiness, certified compliance, integration availability, price or guaranteed business outcomes. The interface and exported brief make that distinction explicit.

## Deployment

Client source directory: `out`. Run `npm run build` to package the Worker and static assets in `dist`. Deploy with owner-private Sites access. Keep the existing project identifier in `.openai/hosting.json`; do not create another Site when editing. Do not enable public access without explicit user approval.


## Optional email/password accounts

The site remains behind the private ChatGPT access gate. App accounts do not add people to the site viewer list and do not create email mailboxes. The configured native owner is authorized from the trusted Sites identity header. The owner can open `/accounts`, set an optional password for their own account, and provision existing email addresses with Admin or Viewer permissions. No public signup exists.

- Generate a temporary password or assign one of 14–128 characters. Credentials appear once and must be delivered by the administrator; the app sends no emails.
- Temporary passwords expire after seven days and must be changed before explorer access.
- Password hashes use scrypt (N=32768, r=8, p=3) with individual random salts.
- Opaque session tokens are stored as SHA-256 digests. Cookies are HttpOnly, Secure, SameSite=Strict and expire after eight hours.
- Password changes, resets, role changes and disabling revoke app sessions. Login attempts are rate limited. JSON mutations enforce same-origin requests and a custom request header.
- An assigned app account requires its password; an unprovisioned approved site viewer may continue using ChatGPT access. The owner always retains administrative access through their configured native identity.
- Disabling an app account does not remove the separate Sites sharing grant.

Runtime bindings: `DB` (D1), `ASSETS` (static files), `FS_OWNER_ID` and `FS_OWNER_EMAIL` (server-only owner configuration). No passwords, session tokens or production identities are embedded in client files.

## Validation

`npm test` runs the account lifecycle and permission tests against actual SQLite with a D1 API adapter. Tests cover temporary passwords, forced change, expiration, reset, disabled accounts, role enforcement, CSRF, throttling, logout and direct asset gating.

References: Cloudflare Node.js crypto support: https://developers.cloudflare.com/workers/runtime-apis/nodejs/crypto/ ; Worker-first asset routing: https://developers.cloudflare.com/workers/static-assets/routing/worker-script/ .

The canonical catalog is in `src/server/catalog.mjs` and is returned only by authenticated `/api/catalog` requests. It is not a publicly served static file. The static application shell contains no catalog data.


## Public visitor registration
This copy accepts contact details and business intake at /register. Registration is self-reported, not email or SMS verified. Server-side format checks, consent, throttling, and an 8-hour HttpOnly session gate the catalog. Visitor sessions never recover or impersonate accounts by email. Administrators review the latest 200 submissions under Account & access. FS_PUBLIC_REGISTRATION=1 enables this flow. The original Site is independent.

## Signal visual theme
Shared theme.css applies black #000001, yellow #FFEA00 and lilac #B39CFF across all screens. Flat surfaces, 4px spacing, responsive heading scale, visible focus and reduced-motion support. Font stacks prefer locally available Blauer Nue/Rubik and use Arial otherwise; no third-party font files or brand assets included.

## Perspective refresh
Dark hero with 37 decorative image cards, a perspective cylinder, cyan-foot gradient actions, a functional library link, pause control and reduced-motion handling. User-supplied CloudFront image URLs have graceful gradient fallbacks. Poppins loads from Google Fonts with system fallback. Existing app remains scrollable and FS branded; the fictional shop mock and WhatsApp action are not used. Registration remains deferred to output actions.
