# Web Karaoke

Web karaoke pribadi — cari & putar video karaoke dari YouTube. Dibangun sebagai satu file HTML statis (`index.html`), tanpa build step. Auto-deploy ke Vercel setiap push ke `main`.

## Arsitektur

- **Frontend**: `index.html` — satu file statis (HTML + CSS + JS). Pencarian lagu, antrean, favorit, riwayat (localStorage), pemutar YouTube IFrame + fallback embed, mic + reverb opsional.
- **Backend pencarian**: Google Apps Script "Web Karaoke API" (terpisah, tidak di repo ini) — proxy pencarian YouTube via Innertube (tanpa API key). Kalau backend down, frontend otomatis fallback ke instance publik Invidious, lalu ke tempel-link manual.
- **Deploy**: Vercel, auto-deploy setiap push ke `main`.

## Pengembangan

Edit lewat artifact Muse `web-karaoke`, lalu export → commit `index.html` yang baru → push. Jangan edit `index.html` langsung di repo tanpa sinkronisasi balik ke artifact.

## Kontrak

Lihat `CHARTER.md` di `~/workspace/karaoke-web/` (milik developer, tidak di-push).
