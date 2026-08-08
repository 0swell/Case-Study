# osmanoz.com — SEO / GEO / AEO Denetim Raporu

**Proje:** https://osmanoz.com
**Tarih:** 22.07.2026
**Denetleyen:** Senior SEO / GEO / AEO uzmanı yaklaşımıyla otomatik denetim
**Kapsam:** Canlı site + kaynak kod + ham HTML (JS'siz) + görsel/logo varlıkları

> Not: Orijinal `1.SEO.md` / `2.GEO.md` / `3.AEO.md` listelerine dokunulmadı; işaretleme yalnızca bu raporda.

---

## ⚠️ ÖNCE BUNU OKU — Sadece Tasarımı Değiştiren / Kurala Takılan Maddeler

Aşağıda **yalnızca** bir şeyi değiştiren ya da core rules'a takılan maddeler var. Burada olmayan tüm öneriler (schema, OG görseli, title/description, canonical, admin noindex vb.) **görünmez ve kural-uyumlu** — onlara dokunmaya gerek yok.

| # | Değişiklik | Ne değişir / neden takılıyor |
|---|------------|------------------------------|
| 5 | Görünür güncelleme tarihi + veri | **Tasarım (minik):** footer/CV'ye ufak "son güncelleme" metni + hero'ya somut veri. Muted token ile, düzen bozulmaz. |
| 6 | SSS (FAQ) + FAQPage schema | **Tasarım (bölüm) + kural:** yeni görünür bölüm. "3 section scroll-stack" kuralı var; 4. katman yaparsak bozulur. **Çözüm: SSS'i CV içine/footer öncesine koyarız, 3 katman korunur.** Onaylar mısın? |
| 7 | Breadcrumb (görünür + schema) | **Tasarım:** küçük görünür iz eklenir (zaten planlıydı, sisteme uyumlu). |
| 10 | Özel 404 sayfası | **Tasarım:** yeni sayfa, sadece hatalı URL'de görünür; tasarım sistemine uyumlu. |
| 4b | hreflang | **Kurala takılıyor:** düzgün hreflang ayrı URL (`/tr`,`/en`) ister; bizde dil çerez-tabanlı tek URL. **Önerim: yapmayalım** (mimari değişir), sadece canonical yeterli olacak. |


---

## 📊 Genel Skor

| Kategori | Skor | Durum |
|----------|------|-------|
| **SEO** (klasik arama) | **%72** | 🟢 İyi — teknik temel sağlam |
| **GEO** (YZ motorları) | **%46** | 🟡 Orta — schema ve içerik derinliği eksik |
| **AEO** (cevap motorları) | **%29** | 🔴 Zayıf — schema/SSS/soru-cevap hiç yok |

**Tek cümle özet:** Teknik SEO altyapısı (HTTPS, robots, sitemap, semantik HTML, mobil, hız) çok iyi kurulmuş; ama **yapısal veri (JSON-LD schema), SSS/soru-cevap içeriği ve içerik derinliği** hiç olmadığı için site YZ ve cevap motorlarında görünmeye hazır değil. En yüksek getirili 5 iş "Hızlı Kazanımlar" bölümünde.

---

# 1. SEO — %72

## A. Taranabilirlik & İndexleme — %68
- `1.A.3` [~] sitemap.xml var ama **Google Search Console'a gönderilmemiş**; sadece anasayfayı içeriyor
- `1.A.5` [~] /admin ve /api robots.txt'de `Disallow` ✓ ama admin sayfalarında ayrıca `noindex` meta yok
- `1.A.7` [✗] **canonical etiketi yok**
- `1.A.9` [~] Özel 404 sayfası yok (Next varsayılanı çalışıyor); kırık link yok
- `1.A.11` [✗] **hreflang yok** — TR/EN çeviri var ama tek URL, dil sinyali verilmiyor

## B. Site Yapısı & Semantik HTML — %70
- `1.B.4` [~] Tek sayfa mimari — hiyerarşik kategori yapısı yok (tasarım gereği düz)
- `1.B.6` [~] Tek URL (`/`); projeler/CV için ayrı URL veya `#hash` çapası yok
- `1.B.8` [✗] **Breadcrumb yok** (ertelenmişti)
- `1.B.9` [~] Navbar section'lara `scrollTo` ile gidiyor; gerçek `<a href>` iç link yok
- `1.B.10` [~] Anchor'lar kısmen açıklayıcı ("Kod"/"Canlı" biraz generic; sosyal linklerde aria-label ✓)

## C. Site İçi SEO (On-Page) — %83
- `1.C.1` [~] Title var ("Osman Öz — Portfolyo") ama **~20 karakter, 50-60 hedefinin altında**; anahtar kelime zayıf
- `1.C.2` [~] Meta description var ama **~70 karakter (120-155 hedefi kısa)**, CTA zayıf

## D. İçerik & Anahtar Kelime — %77
- `1.D.1` [~] Bilinçli birincil anahtar kelime stratejisi yok (örtük "Osman Öz / Software Developer")
- `1.D.3` [~] React/Next.js/TypeScript geçiyor ama long-tail kelime yok
- `1.D.6` [~] Portfolyo için metin az — thin content sınırında
- `1.D.8` [✗] **Görünür "son güncelleme" tarihi yok**

## E. Performans & Mobil — %94
- `1.E.1` [98] LCP yayın sonrası ölçülür (Next+Vercel ile muhtemelen iyi)
- `1.E.2` [98] CLS ölçülür (font+scroll-stack; kontrol önerilir)
- `1.E.3` [98] INP ölçülür
- `1.E.6` [~] `next/dynamic` lazy load kullanılmamış; logo img'lerinde `loading` yok (etki küçük)

## F. Ölçüm & İzleme — %13
- `1.F.1` [✗] **Google Search Console kurulu değil**
- `1.F.2` [✗] **GA4 / analitik yok** (site kendi CV/kart loglarını tutuyor ama sayfa analitiği yok)
- `1.F.3` [~] Kısmi dönüşüm takibi var (CV indirme + kart tıklama DB'de loglanıyor) ama GA event değil
- `1.F.4` [✗] Sıralama/CTR/organik trafik takibi yok (GSC olmadan mümkün değil)

---

# 2. GEO — %46 (Yapay Zekâ Motorlarında Görünürlük)

## A. YZ Botlarına Teknik Erişim — %80
- `2.A.2` [✗] **llms.txt yok**

## B. İçerik Yapısı — %58
- `2.B.3` [~] Tech-stack listesi var ama tanım/karşılaştırma yapısı yok
- `2.B.4` [✗] **Schema (JSON-LD) yok**
- `2.B.5` [~] İçerik kısa — konuyu 360° ele almıyor (portfolyo doğası)
- `2.B.6` [~] Semantik terimler/eş anlamlılar sınırlı

## C. Alıntılanabilirlik (En Kritik) — %42
- `2.C.1` [✗] **İçerikte özgün istatistik/veri yok**
- `2.C.2` [~] İsim var; net tarih/rakam (mezuniyet yılı, deneyim süresi) sitede yok
- `2.C.3` [✗] İddialar kaynağa dayandırılmamış
- `2.C.4` [~] Sınırlı özgün bakış açısı
- `2.C.6` [~] Alıntılanabilir bağımsız bloklar zayıf

## D. E-E-A-T — %25
- `2.D.1` [~] Hero'da deneyim özeti var ama somut vaka/örnek yok
- `2.D.2` [~] "Software Developer" unvanı var, uzmanlık detayı zayıf
- `2.D.3` [✗] Otorite/tanınırlık sinyali yok
- `2.D.4` [~] İletişim (mail+sosyal) + HTTPS var; "Hakkımda"/gizlilik sayfası yok
- `2.D.5` [✗] **Person/author schema yok**
- `2.D.6` [✗] Görünür güncelleme tarihi yok

## E. Konumlandırma & Karşılaştırma — %17
- `2.E.1` [✗] "X nedir / X vs Y" tarzı içerik yok
- `2.E.2` [97] Kişisel portfolyo — rakip karşılaştırma uygulanamaz
- `2.E.3` [✗] YZ'ye sorulacak sorular ("hangi developer'la çalışmalıyım") cevaplanmamış
- `2.E.4` [~] Developer olduğu belli ama "kime/neden uygun" net değil

## F. Marka Varlığı & Dış İtibar (Off-Site) — kapsam çoğu dışı
- `2.F.1` [99] 3. taraf listelerde yer alma — off-site, zamanla
- `2.F.2` [97] Bağımsız inceleme — kişisel site için uygulanamaz
- `2.F.3` [97] Wikipedia/Wikidata — uygulanamaz
- `2.F.4` [99] Forum/topluluk bahsi — off-site
- `2.F.5` [99] Basın bahsi — off-site
- `2.F.6` [~] Marka tutarlılığı: GitHub/LinkedIn "osmanoz" tutarlı ✓, ama merkezî tanım yok
- `2.F.7` [98] Google Knowledge Panel — yayın sonrası oluşabilir

## G. Ölçüm & Takip (GEO) — hepsi yayın sonrası
- `2.G.1`–`2.G.4` [98] YZ testleri, referral takibi, doğruluk kontrolü — site yayıldıktan sonra periyodik yapılır

---

# 3. AEO — %29 (Cevap Motorları / Snippet / Sesli)

## A. Teknik Erişilebilirlik — %100
- `3.A.2` [98] Hız yayın sonrası ölçülür

## B. Yapısal Veri / Schema (AEO'nun Kalbi) — %0
- `3.B.1` [✗] **JSON-LD yok**
- `3.B.2.a` [✗] FAQPage yok
- `3.B.2.b` [97] HowTo — uygun içerik yok
- `3.B.2.c` [97] Article/BlogPosting — blog yok
- `3.B.2.d` [97] Course — uygulanamaz
- `3.B.2.e` [✗] **Organization/Person yok** (Person birebir uygun olurdu)
- `3.B.2.f` [✗] BreadcrumbList yok
- `3.B.2.g` [97] Product/Review — uygulanamaz
- `3.B.3` [✗] Rich Results testinden geçecek schema yok
- `3.B.4` [97] Schema olmadığı için tutarlılık N/A
- `3.B.5` [✗] **`sameAs` (GitHub/LinkedIn bağı) yok**

## C. Soru-Cevap Formatı (En Kritik) — %10
- `3.C.1` [✗] Sorular başlık (H2/H3) olarak yok
- `3.C.2` [✗] Soru altında öz cevap yok
- `3.C.3` [~] Hero özeti kısmen ters piramit
- `3.C.4` [✗] Doğal dil soru başlıkları yok
- `3.C.5` [✗] Soru kalıpları (nedir/nasıl/hangi) yok

## D. İçeriğin Taranabilirliği — %75
- `3.D.1` [~] Tech-stack rozetleri liste sayılır; genel liste kullanımı az
- `3.D.2` [97] Karşılaştırma/tablo içeriği yok
- `3.D.5` [~] Önemli tanımlar bold ile vurgulanmamış

## E. Öne Çıkan Snippet Hedefleme — %0
- `3.E.1` [✗] "Nedir" tanımı yok
- `3.E.2` [97] "Nasıl" adım içeriği yok
- `3.E.3` [✗] Liste/bullet cevap yok
- `3.E.4` [✗] Snippet'e uygun üst-sayfa cevabı yok

## F. Güven & Doğruluk — %13
- `3.F.1` [~] Bilgiler doğru ama kaynaksız
- `3.F.2` [✗] Net sayı/tarih/istatistik yok
- `3.F.3` [✗] Author/publisher işareti yok
- `3.F.4` [✗] **SSS (FAQ) bölümü yok**

## G. Sesli Arama — %33
- `3.G.1` [~] Ton kısmen doğal
- `3.G.2` [✗] Uzun kuyruk/soru tabanlı ifade yok
- `3.G.3` [97] LocalBusiness/NAP — yerel işletme değil
- `3.G.4` [~] Cevaplar kısa ama soru-cevap formatı yok

---

# 4. Görsel / Logo / Medya SEO Analizi

**Mevcut durum:**
- `public/logo/OZ-Logo-Light.svg` ve `OZ-Logo-Dark.svg` — **SVG (vektör): boyut/hız açısından ideal**, `<title>` etiketi içeriyor (erişilebilirlik ✓).
- Navbar/footer/login logoları `alt="Osman Öz"` ✓; tema kopyası `alt="" aria-hidden` ✓ (doğru, çift okunmaz).
- `src/app/icon.svg` favicon mevcut ✓ (`<title>Osman Öz</title>`).
- Proje kartlarında görsel yok (sadece metin) — alt eksiği yok.
- CV: Vercel Blob'da PDF; site içeriği HTML olduğu için SEO'yu engellemiyor.

**Eksikler:**
- `1.G.1` [✗] **Open Graph paylaşım görseli (og:image) yok** — WhatsApp/LinkedIn/X'te link paylaşınca kapak görseli çıkmaz (en görünür eksik).
- `1.G.2` [~] Logo dosya adları jenerik (`OZ-Logo-*.svg`); `osman-oz-logo-*.svg` daha anlamlı olurdu (etki küçük).
- `1.G.3` [~] `alt="Osman Öz"` yerine `alt="Osman Öz logosu"` daha açıklayıcı (minör).
- `1.G.4` [✗] Person schema'da `image` alanı yok (YZ/Knowledge Panel için profil görseli bağı önerilir).

---

# 🎯 ÖNERİLER (Kod ile Uygulanabilir — Öncelik Sırası)

## ⭐ Hızlı Kazanımlar (en yüksek getiri / düşük efor)

**1. Person + WebSite JSON-LD schema ekle** → AEO/GEO'yu en çok bu yükseltir
`3.B.1, 3.B.2.e, 3.B.5, 2.B.4, 2.D.5` çözer. `layout.tsx`'e `<script type="application/ld+json">` ile Person schema: ad, unvan (Software Developer), `url`, `sameAs` (GitHub + LinkedIn), `alumniOf` (Burdur MAKÜ), `knowsAbout` (React, Next.js, TypeScript, Python, ML). Google ve YZ motorları "Osman Öz kimdir" sorusuna bu veriyle cevap verir.

**2. Open Graph + Twitter görseli ekle** → sosyal paylaşım kapağı
`1.G.1, 1.G.4` çözer. `src/app/opengraph-image.tsx` (Next dinamik OG, 1200×630) — isim + "Software Developer" + logo. Link paylaşımında profesyonel kapak çıkar.

**3. Title & description'ı SEO'ya göre yaz**
`1.C.1, 1.C.2, 1.D.1` çözer.
- Title: `Osman Öz — Software Developer | React, Next.js & TypeScript` (~55 karakter)
- Description: 120-155 karakter, anahtar kelime + CTA ("...projelerimi inceleyin, CV'me ulaşın").

**4. canonical + hreflang ekle**
`1.A.7, 1.A.11` çözer. `metadata.alternates.canonical = "https://osmanoz.com"` ve TR/EN için hreflang. Kopya içerik ve dil sinyali netleşir.

**5. Görünür "son güncelleme" tarihi + net veriler**
`1.D.8, 2.C.2, 2.D.6, 3.F.2` çözer. CV/footer'a "Son güncelleme: ..." ve hero'ya somut veri (mezuniyet yılı, teknoloji sayısı vb.).

## 🔧 Orta Öncelik

**6. SSS (FAQ) bölümü + FAQPage schema** → AEO'nun kalbi
`3.F.4, 3.B.2.a, 3.C.1-5, 3.E.*` çözer. CV section altına 4-6 soru: "Osman Öz kimdir?", "Hangi teknolojilerle çalışır?", "İletişime nasıl geçilir?" — her sorunun altında 40-60 kelime öz cevap + FAQPage JSON-LD. Snippet ve sesli arama için kritik.

**7. Breadcrumb (görünür + BreadcrumbList JSON-LD)**
`1.B.8, 3.B.2.f` çözer. Daha önce not aldığımız iş — görünür breadcrumb + schema birlikte.

**8. Google Search Console + GA4 kur**
`1.F.1, 1.F.2, 1.F.4` çözer. GSC doğrulama + sitemap gönderimi; GA4 (veya Vercel Analytics) sayfa trafiği için. *(Yayın sonrası, insan aksiyonu)*

**9. Admin sayfalarına `noindex` meta**
`1.A.5` çözer. robots.txt Disallow var ama `/admin` layout'a `robots: { index: false }` metadata eklemek ikinci güvenlik katmanı.

**10. Özel 404 sayfası**
`1.A.9` çözer. `src/app/not-found.tsx` — markalı, ana sayfaya dönüş linkli.

## 📌 Off-Site / Süreç İşleri (kod dışı, zamanla)

- `2.F.*` Marka varlığı: LinkedIn/GitHub profillerini zenginleştir, projeleri paylaş, teknik yazı/katkı ile bahis oluştur.
- `2.G.*` YZ takibi: ChatGPT/Perplexity/Gemini'ye periyodik "Osman Öz developer" sorup görünürlüğü izle.
- `llms.txt` (`2.A.2`): kök dizine kısa `llms.txt` — siteyi ve kişiyi YZ botlarına özetler (opsiyonel ama GEO artı).

---

## Onay

Bu rapordaki **Hızlı Kazanımlar (1-5)** ve istersen **Orta Öncelik (6-10)** maddelerini koda uygulayabilirim. Onayını bekliyorum — "hepsini uygula", "sadece hızlı kazanımlar", ya da tek tek seçebilirsin.

---

## 🧩 Schema (Yapısal Veri) — Canlıda Uygulanan JSON-LD

> Not: Öneriler **uygulandı** (22.07.2026). Aşağıdaki schema'lar sitede canlı.
> Kaynak dosyalar: `src/components/atoms/JsonLd.tsx` (Person/WebSite/BreadcrumbList) ve `src/components/organisms/FaqSection.tsx` (FAQPage).

### 1) Person + WebSite + BreadcrumbList — her sayfada (`<head>`/`<body>`)

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Person",
      "@id": "https://osmanoz.com/#person",
      "name": "Osman Öz",
      "alternateName": "Osman Oz",
      "url": "https://osmanoz.com",
      "image": "https://osmanoz.com/opengraph-image",
      "jobTitle": "Software Developer",
      "email": "mailto:iletisim@site.com",
      "address": { "@type": "PostalAddress", "addressLocality": "Burdur", "addressCountry": "TR" },
      "alumniOf": { "@type": "CollegeOrUniversity", "name": "Burdur Mehmet Akif Ersoy Üniversitesi" },
      "knowsAbout": ["React","Next.js","TypeScript","Tailwind CSS","JavaScript","Python","Machine Learning","Flutter","T-SQL","Frontend Development"],
      "sameAs": ["https://github.com/0swell","https://www.linkedin.com/in/osmanoz15"]
    },
    {
      "@type": "WebSite",
      "@id": "https://osmanoz.com/#website",
      "url": "https://osmanoz.com",
      "name": "Osman Öz — Portfolyo",
      "inLanguage": ["tr-TR","en"],
      "publisher": { "@id": "https://osmanoz.com/#person" }
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://osmanoz.com/#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Ana Sayfa", "item": "https://osmanoz.com" },
        { "@type": "ListItem", "position": 2, "name": "Projeler", "item": "https://osmanoz.com/#projeler" },
        { "@type": "ListItem", "position": 3, "name": "CV", "item": "https://osmanoz.com/#cv" },
        { "@type": "ListItem", "position": 4, "name": "SSS", "item": "https://osmanoz.com/#sss" }
      ]
    }
  ]
}
```

### 2) FAQPage — SSS bölümünde

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    { "@type": "Question", "name": "Osman Öz kimdir?", "acceptedAnswer": { "@type": "Answer", "text": "..." } },
    { "@type": "Question", "name": "Osman Öz hangi teknolojilerle çalışıyor?", "acceptedAnswer": { "@type": "Answer", "text": "..." } },
    { "@type": "Question", "name": "Osman Öz yapay zekâ destekli geliştirme yapıyor mu?", "acceptedAnswer": { "@type": "Answer", "text": "..." } },
    { "@type": "Question", "name": "Osman Öz ile nasıl iletişime geçilir?", "acceptedAnswer": { "@type": "Answer", "text": "..." } },
    { "@type": "Question", "name": "Osman Öz'ün CV'si nasıl indirilir?", "acceptedAnswer": { "@type": "Answer", "text": "..." } }
  ]
}
```
> (`text` alanları `dictionaries.ts`'teki tam cevaplarla doldurulur; yukarıda kısaltıldı.)

### Kullanıcının önerdiği ProfilePage varyantı (alternatif)

Aşağıdaki daha sade `ProfilePage` sürümü de geçerlidir; istenirse mevcut `@graph` bununla değiştirilebilir. Tek fark: `image` logo SVG'sine işaret eder ve WebSite/BreadcrumbList içermez.

```json
{
  "@context": "https://schema.org",
  "@type": "ProfilePage",
  "inLanguage": "tr-TR",
  "mainEntity": {
    "@type": "Person",
    "name": "Osman Öz",
    "jobTitle": "Software Developer",
    "url": "https://osmanoz.com",
    "image": "https://osmanoz.com/logo/logoOsmanOz-LightMode.svg",
    "description": "Bilgisayar Mühendisliği mezunu; React, Next.js, TypeScript ile web geliştiriyor.",
    "knowsAbout": ["React", "Next.js", "TypeScript", "Python", "Makine Öğrenmesi"],
    "alumniOf": { "@type": "CollegeOrUniversity", "name": "Burdur Mehmet Akif Ersoy Üniversitesi" },
    "sameAs": ["https://github.com/0swell", "https://www.linkedin.com/in/osmanoz15"]
  }
}
```
