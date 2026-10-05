# zp360.js — 360° Ürün Görüntüleyici / 360° Product Viewer

Sürükleyerek döndürülen, bağımlılıksız (saf JavaScript) 360° ürün görüntüleyici.
[Zümrüt Plastik](https://www.zumrutplastik.com.tr) ürün sayfaları için geliştirildi.

A lightweight, dependency-free 360° product viewer in vanilla JavaScript, built for
[Zümrüt Plastik](https://www.zumrutplastik.com.tr) product pages.

Developed by **Ramazan Zengin**

**Canlı örnek / Live demo:** [22 Litre Market Alışveriş Sepeti](https://www.zumrutplastik.com.tr/22-litre-market-alisveris-sepeti)

---

## Özellikler / Features

- Saf JavaScript, harici kütüphane yok (tek dosya: `zp360.js`)
- Fare ile sürükleme, dokunmatik ekranda parmakla çevirme, klavye ok tuşları
- Yakınlaştırma ve tam ekran
- Küçük resim şeridi ile açıya atlama
- Görseller açılışta önceden yüklenir, yükleme çubuğu gösterilir
- Otomatik dönüş (kapatılabilir); "hareketi azalt" ayarı açık olan cihazlarda dikkate alınır
- Erişilebilirlik: `aria-label` ve klavye odağı

## Kurulum / Usage

1. Ürünü 10°'de bir çekilmiş 36 kare olarak hazırlayın ve şöyle adlandırın:
   `01.webp`, `02.webp` … `36.webp`

2. Sayfaya görüntüleyici kutusunu ve script'i ekleyin:

```html
<div class="zp360"
     data-base="https://cdn.jsdelivr.net/gh/ramazanzengin-dev/360-View-Test@main/KLASOR/"
     data-count="36"
     data-ext=".webp"
     data-label="22 Litre Market Alışveriş Sepeti 360° görünümü"></div>

<script src="https://cdn.jsdelivr.net/gh/ramazanzengin-dev/360-View-Test@main/zp360.js" defer></script>
```

`KLASOR/` yerine görsellerin bulunduğu klasörü yazın.

## Ayarlar / Options

| Özellik | Varsayılan | Açıklama |
|---|---|---|
| `data-base` | — | Kare görsellerinin klasör adresi (sonunda `/` olmalı) |
| `data-count` | `36` | Kare sayısı |
| `data-ext` | `.webp` | Dosya uzantısı |
| `data-thumbs` | `10` | Küçük resim sayısı |
| `data-sensitivity` | `8` | Sürükleme hassasiyeti (piksel / kare) |
| `data-autoplay` | açık | Otomatik dönüşü kapatmak için `"false"` |
| `data-color` | `#1f5fd6` | Vurgu rengi |
| `data-label` | `Ürünün 360° görünümü` | Ekran okuyucu metni |
| `data-frames-var` | — | Görsel adreslerini bir dizi değişkeninden almak için değişken adı |

## Lisans / License

MIT — ayrıntılar için [LICENSE](LICENSE) dosyasına bakın.
