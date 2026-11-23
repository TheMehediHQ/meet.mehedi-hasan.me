# meet.mehedi-hasan.me

> An ultra-fast, modern redirect website built with [Astro](https://astro.build). Automatically redirects visitors from **[meet.mehedi-hasan.me](https://meet.mehedi-hasan.me)** to **[Google Meet](https://meet.google.com/nvy-xigu-xum)**.

[![Target Google Meet](https://img.shields.io/badge/Google%20Meet-nvy--xigu--xum-00ac47?style=for-the-badge&logo=google-meet&logoColor=white)](https://meet.google.com/nvy-xigu-xum)
[![Source Domain](https://img.shields.io/badge/Source%20Domain-meet.mehedi--hasan.me-38bdf8?style=for-the-badge)](https://meet.mehedi-hasan.me)
[![Repository](https://img.shields.io/badge/Repository-TheMehediHQ%2Fmeet.mehedi--hasan.me-blue?style=for-the-badge&logo=github)](https://github.com/TheMehediHQ/meet.mehedi-hasan.me)

---

## 📌 Project Overview

- **Project Name:** `meet.mehedi-hasan.me`
- **Repository:** [`TheMehediHQ/meet.mehedi-hasan.me`](https://github.com/TheMehediHQ/meet.mehedi-hasan.me)
- **Source Domain:** [https://meet.mehedi-hasan.me](https://meet.mehedi-hasan.me)
- **Target Destination:** [https://meet.google.com/nvy-xigu-xum](https://meet.google.com/nvy-xigu-xum)

---

## ⚡ Key Features

1. **Triple-Layer Redirection System**:
   - **Edge / Server-Level 302/307 Redirect**: Powered by `vercel.json` (for Vercel) and `_redirects` (for Netlify and Cloudflare Pages) for zero-latency temporary redirection without aggressive browser caching (allowing meeting links to be updated freely in the future).
   - **Immediate Client-Side JavaScript**: Executes `window.location.replace()` in `<head>` to immediately launch the meeting room without adding dummy states to browser history.
   - **HTML `<meta http-equiv="refresh">`**: Immediate fallback for web clients and bots where JavaScript is disabled.
2. **SEO & Privacy Protection**:
   - `robots: "noindex, nofollow"` prevents search engines and web crawlers from indexing private meeting rooms.
   - `rel="canonical"` pointed directly to the Google Meet link.
3. **Catch-All 404 Fallback**:
   - Includes a dedicated `404.astro` page to route any subpath or typos directly into the meeting room.
4. **Clean Fallback UI**:
   - Sleek Google Meet-themed card with animated spinner and a direct **"Join Meeting Now"** button.

---

## 🚀 Local Development

### Prerequisites
- Node.js (`>= 22.12.0`) or [Bun](https://bun.sh)

### Installation & Run

```bash
# Clone the repository
git clone https://github.com/TheMehediHQ/meet.mehedi-hasan.me.git
cd meet.mehedi-hasan.me

# Install dependencies
npm install
# or
bun install

# Start the local development server
npm run dev
# or
bun run dev
```

Visit `http://localhost:4321` in your browser to test the redirection.

### Build for Production

```bash
npm run build
# or
bun run build
```

Production static assets will be output to the `dist/` directory.

---

## 🌐 Deployment

### Vercel (Recommended)
1. Push your code to GitHub.
2. Import repository `TheMehediHQ/meet.mehedi-hasan.me` into [Vercel](https://vercel.com).
3. The framework will be automatically detected as **Astro**.
4. In Vercel Project Settings > **Domains**, add **`meet.mehedi-hasan.me`**.
5. Deploy. `vercel.json` will automatically handle instant 307 edge redirects.

### Cloudflare Pages
1. Connect repository in Cloudflare Dashboard under **Workers & Pages** > **Pages**.
2. Build Settings:
   - Framework preset: `Astro`
   - Build command: `npm run build`
   - Output directory: `dist`
3. Add custom domain **`meet.mehedi-hasan.me`**.
4. Deploy. The `_redirects` file automatically handles edge redirection.

### Netlify
1. Import repository into Netlify.
2. Build command: `npm run build`
3. Publish directory: `dist`
4. Deploy.

---

## 📄 License

MIT © [Mehedi Hasan](https://mehedi-hasan.me)
