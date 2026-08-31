# Testkube sign-in pages

`web/` holds the Testkube look for the Dex pages: nine templates that replace the upstream
templates, and the static assets (CSS, wordmark, favicon, Roboto fonts, background images)
served at `/static/testkube/`. The Dockerfile copies them into `/srv/dex/web` and sets
`DEX_FRONTEND_DIR`, so the image shows these pages with no `frontend` configuration.

The values in `web/static/testkube/styles.css` copy the Testkube dashboard build 1:1
(`src/styles/Colors.ts`, the `AuthPage*`, `Banner`, and `AuthForm*` styled-components, the
antd theme tokens, `src/styles/MediaQueries.ts` in `testkube-cloud-api/js/packages/web`).
The header comment in `styles.css` lists the sources.

The only per-environment value is `frontend.extra.dashboardURL` in the Dex config. The error
page uses it for the "Back to Testkube" button. Without it the button returns to the previous page.
