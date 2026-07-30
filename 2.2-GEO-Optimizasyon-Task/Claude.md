# GEO Optimizasyon

Bu dosya öncelikli olarak bir GEO sonrasında SEO ve AEO optimizasyon talimatıdır. Bu Claude.md'yi (`osmanoz.com`) için **GEO / SEO / AEO** optimizasyonu olarak yürüt: önce mevcut durumu checklist'lere göre denetle, negatifleri düzeltmek için, öneri maddelerini kodda uygula, önerileri ana fikir olarak düşün, bu ana fikirleri daha detaylı düşünüp uygulayabilirsin. Sonra sonucu raporla. Bu talimatları **Google'da çalışan bir Senior Dijital Pazarlama ve SEO / GEO / AEO uzmanı** olarak uygula.

---

## İş Akışı

​```text
┌─ 1 · KONTROL   ─┐  ┌─ 2 · UYGULAMA   ─┐  ┌─ 3 · RAPOR ─┐
│  Checklist'leri │→ │  Negatif (✗) ve │→│  rapor.pdf   │→ ↺ DÖNGÜ
│  tara & işaretle│  │  önerileri uygula│  │  oluştur     │  (opsiyonel)
└─────────────────┘  └──────────────────┘  └─────────────┘
​```

1. **KONTROL** — İlgili checklist'teki her maddeyi tek tek denetle ve işaretle.
2. **UYGULAMA** — Negatifleri düzeltmek için öneri maddelerini kodda doğru şekilde uygula.
3. **RAPOR** — Yapılanları `rapor.pdf` olarak çıkar. Rapor üzerinde düzeltilen maddeleri uygun işaretle gösterebilirsin. Varsa yapılamayanları da sebebiyle belirt.
4. **↺ DÖNGÜ** *(opsiyonel)* — İsteğe bağlı, tekrar sor, kalan madde varsa akışı baştan çalıştır.

---

## İşaretleme

**Standart:** `[✓]` pozitif (uygun) · `[✗]` negatif (uygun değil) · `[~]` kısmen · `[N/A]` Bu seçeneklerden herhangi biri için uygun değilse
**Özel:** `[97]` → 100 üzerinden, puanla ifade edilen maddelerde skoru köşeli parantez içinde yaz (ör. PageSpeed skoru).

---

## Teknik Temel: `PageSpeed-Insights-Todo.md`

Bu dosyadaki maddeler sitenin bazı teknik performans, erişilebilirlik ve en iyi uygulama eksikleridir. **Tüm maddeleri sırayla uygula**, her düzeltilmesi gerekeni veya önerileri kodda gerçekleştir ve tamamlananı `[✓]` olarak işaretle. Uygulanan her maddenin gerçekten çözüldüğünü doğrula — kısmi çözümü `[~]` bırakma, tamamla.

---

## GEO Katmanı: `2.GEO.md`

Bu dosya sitenin YZ arama motorlarında (ChatGPT, Perplexity, Gemini, Claude) görünürlüğünü artıran GEO kontrol listesidir. **Her maddeyi denetle ve kodda uygulanabilir olanları uygula**: YZ botlarına erişim (`robots.txt`, `llms.txt`), semantik ve JS'siz okunabilir HTML, alıntılanabilir somut veriler, E-E-A-T sinyalleri ve yapısal veri (schema / JSON-LD). Kod dışı (off-site) maddeleri öneri olarak işaretle, uygulananları `[✓]` yap.

---

## Rapor: `rapor.pdf`

Uygulama bittikten sonra bir **analiz raporu** oluştur (`rapor.pdf`):

- Başlangıçta negatif (`[✗]`) olan maddelerden hangilerinin uygulandığını listele.
- Uygulanamayan madde varsa **neden** uygulanamadığını kısaca açıkla.
- Her checklist'in son durumunu (pozitif/negatif/kısmi sayısı) özetle.
- İstatistik, yüzde, analiz ve gerekliyse grafik veya panel veya chart de ekleyebilrsin.
- Tüm maddeler tamamlandıysa raporu **yemyeşil (tüm maddeler `[✓]`)** bir checklist görünümünde sunabilirsin.
