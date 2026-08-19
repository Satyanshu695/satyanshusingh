# Satyanshu Portfolio

A single-page personal portfolio site for Satyanshu, a Computer Science student. It presents an about section, academic scorecard, projects, certificates, goals, and a contact area.

## Technologies

- Plain HTML, CSS, and vanilla JavaScript (no build step, no framework)
- Google Fonts (Space Grotesk, Inter, JetBrains Mono)
- Netlify Forms for the contact form submission handling

## Running locally

Serve the site with the Netlify CLI so Forms behaves the same as production:

```bash
netlify dev
```

Then open the printed local URL. Since this is static HTML, you can alternatively open `index.html` directly in a browser, though the contact form submission will only work when served through Netlify (locally via `netlify dev` or once deployed).
