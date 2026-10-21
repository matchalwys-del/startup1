# Chevron (upgraded)

Dua versi dari file yang sama:

- `web/` : index.html + config.js + icons.js (+ font.css sebagai sumber build). Buka langsung atau hosting statis.
- `extension/` : ekstensi Chrome (Manifest V3) yang menggantikan halaman New Tab.

## Pasang ekstensi
1. Buka `chrome://extensions`, aktifkan **Developer mode**.
2. **Load unpacked**, pilih folder `extension`.
3. Buka tab baru.

## Yang diubah
- config.js: URL ChatGPT -> chatgpt.com, Twitter -> x.com (trigger `x` ditambah), Telegram -> https, trigger `whatsapp` ditambah,
  teks Slack dibuat lebih kontras, hotkey untuk Spotify (P), Twitch (V), X (X), Drive (F), Wikipedia (K), Slack (U),
  ikon untuk VK/DuckDuckGo/Bing/Yandex, macro baru: Claude (Q), Google Maps (O), Tokopedia (B), Shopee (H).
- icons.js: 8 ikon baru (VK, DuckDuckGo, Bing, Yandex, Tokopedia berupa huruf sederhana; Claude, Maps, Shopee berupa glyph generik).
- Konversi mata uang: exchangerate.host (butuh key) -> open.er-api.com (tanpa key).
- AI: model sekarang bisa diatur di settings (`query.AI.model`, default `gpt-4o-mini`), prompt sistem tidak lagi mengaku cutoff 2021.
- Ekstensi: script inline dipindah ke app.js / coloration.js (syarat MV3), saran pencarian Google memakai fetch (bukan JSONP).

## Catatan
- Belum diuji di Chrome sungguhan (lingkungan tanpa internet). Sintaks bundle sudah dicek dan fungsi mata uang dites dengan mock.
- API key OpenAI tetap disimpan di localStorage.
- Di Chrome, kotak alamat biasanya merebut fokus saat tab baru dibuka, jadi hotkey halaman bisa perlu klik dulu.
