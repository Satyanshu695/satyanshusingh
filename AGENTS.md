# AGENTS.md

## Architecture

This is a static, single-file portfolio site: everything (markup, CSS, JS) lives in `index.html` at the project root. There is no build step, bundler, or framework — Netlify serves this file directly.

## Key files

- `index.html` — the entire site: nav, hero, about, academics, projects, certificates, goals, and contact sections, plus a `<script>` block driving section switching, a certificate lightbox, and the contact form's AJAX submission.

## Contact form

The Contact section includes a real `<form name="contact" data-netlify="true">` wired up for [Netlify Forms](https://docs.netlify.com/forms/setup/). Key details:

- Submissions are intercepted client-side (`e.preventDefault()`) and POSTed via `fetch` to `/` with `application/x-www-form-urlencoded` content, per Netlify's AJAX form pattern.
- A hidden `form-name` input and a honeypot (`bot-field`) field are included for build-time detection and spam protection.
- Because this is a static site (not SSR), no separate form skeleton file is needed — Netlify's build bot parses `index.html` directly.
- View submissions in the Netlify UI under Forms, or configure email notifications there.

## Conventions

- Section navigation is handled by toggling a `.active` class on `.content-section` elements based on `data-nav` links — there is no client-side router.
- Color palette and fonts are defined as CSS custom properties in `:root` at the top of the `<style>` block; reuse those variables for any new UI rather than hardcoding colors.
