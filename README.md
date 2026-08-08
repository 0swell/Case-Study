# 🔍 SEO / GEO / AEO Checker

> Herhangi bir web projesini **SEO**, **GEO** (Generative Engine Optimization) ve **AEO** (Answer Engine Optimization) açısından madde madde denetleyen; eksikleri **dosya + kod önerisiyle** raporlayan, tekrar kullanılabilir bir kontrol listesi & talimat seti.

![toplam madde](https://img.shields.io/badge/toplam_madde-129-1f3a5f)
![SEO](https://img.shields.io/badge/SEO-53-2f6fed)
![GEO](https://img.shields.io/badge/GEO-38-8a4dd6)
![AEO](https://img.shields.io/badge/AEO-38-1a9d63)

---

## 📋 Kapsam

| Katman | Odak | Madde | Pay |
|---|---|:--:|:--:|
| **SEO** | Google/Bing için klasik arama motoru optimizasyonu | 53 | %41 |
| **GEO** | YZ motorlarında (ChatGPT · Perplexity · Gemini) kaynak gösterilme | 38 | %29 |
| **AEO** | Cevap motorlarında (öne çıkan snippet · sesli asistan) doğrudan cevap | 38 | %29 |

## 🏷️ İşaretleme

| İşaret | Anlam |
|:--:|---|
| `[✓]` | Uygun |
| `[✗]` | Eksik / negatif |
| `[~]` | Kısmen |
| `[N/A]` | Uygulanamaz |

> Yalnızca `[✗]` ve `[~]` maddeler rapora alınır; her birinin altına **ilgili dosya + yapılacak kod değişikliği** yazılır.

## 🔄 İş Akışı

```
KONTROL  →  RAPOR  →  ÖNERİ  →  (onay)  →  UYGULAMA  →  ↺
```

1. Projeyi checklist'lere göre **denetle**, her maddeyi işaretle.
2. Negatif/kısmen maddeleri **tek rapora** topla.
3. Her maddenin altına: **ilgili dosya + yapılacak kod değişikliği**.
4. **Onaydan sonra** kodda uygula.

Detaylı talimat ve rapor formatı → [`0.instructions.md`](SEO-GEO-AEO-Checklists/0.instructions.md)

## 🚀 Kullanım

Projenin bulunduğu bir AI oturumuna (Claude Code, Cursor vb.) şu prompt'u ver:

```text
Sen kıdemli bir SEO / GEO / AEO uzmanısın. Bu projeyi SEO-GEO-AEO-Checklists/
klasöründeki 1.SEO.md · 2.GEO.md · 3.AEO.md listelerine göre denetle.
KODU DEĞİŞTİRME — sadece raporla.

1. Önce stack'i tespit et (Next.js / WordPress / düz HTML vb.).
2. Her maddeyi işaretle: [✓] uygun · [✗] eksik · [~] kısmen · [N/A] uygulanamaz.
3. Eksik/negatif maddeleri tek raporda topla:
   [✗] 1.A.3 · madde  →  Dosya: ...  →  Değişiklik: ...
4. Sonda "Öncelik Sırası" (etki/çaba) bölümü ekle.
```

## 📁 Yapı

```
SEO-GEO-AEO-Checklists/
├── 0.instructions.md    # denetim talimatı · iş akışı · rapor formatı
├── 1.SEO.md             # 53 madde — taranabilirlik, semantik HTML, on-page, performans
├── 2.GEO.md             # 38 madde — YZ bot erişimi, alıntılanabilirlik, E-E-A-T, entity
├── 3.AEO.md             # 38 madde — schema, soru-cevap formatı, snippet, sesli arama
└── *-ornegı.*           # osmanoz.com üzerinde örnek denetim çıktıları
```

---

<sub>Bir <b>osmanoz.com</b> çalışmasından doğdu · katmanlı mantık: SEO temeli → GEO/AEO üzerine kurulur.</sub>
