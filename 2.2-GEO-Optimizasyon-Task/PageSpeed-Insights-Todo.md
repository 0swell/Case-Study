# PageSpeed Insights — Todo (osmanoz.com)

> Negatif / nötr, değişmesi gereken maddeler. Tamamlananlar `[x]` işaretlenir.
> ▲ = negatif (kritik) · ○/■ = nötr (Puanlanmamış / öneri)

## Performans

- [ ] ▲ **Oluşturma engelleme istekleri (Render-blocking)** — Tahmini tasarruf: 300 ms
  - Engelleyen dosya: `chunks/3l7swn1k6q_z4.css` (7,0 KiB · 150 ms)
  - Çözüm: kritik CSS'i satır içine al (inline), kritik olmayanı ertele (defer)

- [ ] ▲ **Eski JavaScript (Legacy JS / polyfill)** — Tahmini tasarruf: ~14 KiB
  - Dosya: `chunks/3xf3z0o5am-10.js` (13,7 KiB)
  - Gereksiz polyfill'ler: Array.prototype.at, Array.prototype.flat, Array.prototype.flatMap, Object.fromEntries, Object.hasOwn, String.prototype.trimEnd, String.prototype.trimStart
  - Çözüm: modern tarayıcı hedefi (Baseline / ES6+), polyfill'siz derleme

- [ ] ▲ **Kullanılmayan JavaScript'i azalt** — Tahmini tasarruf: 79 KiB
  - `chunks/0mqhnfw3in9hj.js` (43,2 KiB → 30,2 KiB tasarruf)
  - `chunks/3xf3z0o5am-10.js` (70,6 KiB → 27,3 KiB tasarruf)
  - `chunks/2m4fzlufi_usw.js` (37,5 KiB → 21,4 KiB tasarruf)
  - Çözüm: kod bölme / lazy load (framer-motion dahil)

- [ ] ○ **LCP dökümü** — LCP öğesi: hero paragrafı ("Bilgisayar Mühendisliği mezunu, Yazılım Mühendisliği yüksek lisans öğrencisiyim…")
  - Time to First Byte: 0 ms · Öğe oluşturma gecikmesi: 2.570 ms (asıl darboğaz)
  - Çözüm: render'ı bloke eden CSS + JS'i azalt (üstteki maddeler bunu düzeltir)

- [ ] ○ **DOM boyutunu optimize et** — Puanlanmamış
  - Toplam öğe: 114 · DOM derinliği: 12 · Maksimum alt öğe: 18
  - Çözüm: gereksiz sarmalayıcı (wrapper) div'leri azalt, DOM'u sadeleştir

- [ ] ■ **Resim öğelerinde width/height yok** — Puanlanmamış (CLS riski)
  - `<img src="/logo/logoOsmanOz-LightMode.svg" alt="Osman Öz" class="... h-7 w-auto sm:h-8">`
  - `<img src="/logo/logoOsmanOz-LightMode.svg" alt="Osman Öz" class="... h-12 w-auto sm:h-14">`
  - Çözüm: logo görsellerine açık `width` ve `height` ekle

- [ ] ○ **Uzun ana iş dizisi görevi (TBT)** — 1 uzun görev
  - `chunks/3xf3z0o5am-10.js` — başlangıç 2.551 ms · süre 85 ms
  - Çözüm: uzun görevi böl / azalt (kod bölme ile ilişkili)

## Erişilebilirlik

- [ ] ▲ **Kontrast yetersiz** — arka plan/ön plan renkleri düşük kontrastlı
  - Etkilenen: "Merhaba", "Projeler", "CV", "TR" butonları ve "Software Developer" gibi `text-muted` metinler
  - Çözüm: `text-muted` tonunu koyulaştır (WCAG AA kontrast oranını sağla)

- [ ] ▲ **SVG (role="img") erişilebilir metin alternatifi yok** — [Erişilebilirlik + Ajan Tabanlı, tek düzeltme]
  - `ul.flex > li > a.inline-flex > svg` (sosyal medya ikonları): `<svg role="img" ... width="18" height="18">` — alt metin yok
  - Çözüm: SVG'lere `<title>` veya `aria-label` ekle

## Ajan Tabanlı Tarama (GEO — 1/2)

- [ ] ▲ **Erişilebilirlik ağacı düzgün biçimlendirilmemiş** — yukarıdaki SVG alt-metin sorunuyla AYNI kök
  - Aynı `<svg role="img">` öğesi; düzeltmesi yukarıdaki maddeyle birlikte çözülür (bir taşla iki kuş)

## En İyi Uygulamalar (skor 100 — opsiyonel güvenlik sertleştirmesi)

- [ ] ○ **Güvenlik başlıkları (opsiyonel)** — Puanlanmamış öneriler
  - CSP (XSS), güçlü HSTS, COOP izolasyonu, XFO/CSP ile clickjacking, Trusted Types
  - Çözüm: `next.config.ts` üzerinden ilgili HTTP güvenlik başlıklarını ekle
