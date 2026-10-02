# 360 görüntüleyici

Ürünleri 360° gösterebilmek için yazdığımız küçük bir script. Ürün görseli fareyle ya da parmakla sürüklenince dönüyor. Bizim işimizi gördü, belki başkasının da işine yarar diye paylaşıyoruz.

**Not:** Henüz deneme aşamasında. Biz tek bir üründe test ediyoruz. Kendi sitenizde kullanmadan önce bir ürün sayfasında denemenizi öneririz.

## Neler var

- Sürükleyerek döndürme (bilgisayar ve telefon)
- Açılışta kendi kendine yavaş dönme, dokununca duruyor
- Yakınlaştırma, uzaklaştırma ve tam ekran
- Altta açı küçük resimleri ve kaydırma çubuğu
- İsterseniz köşeye logo
- Telefonda sade görünüm

Dışarıdan hiçbir kütüphane yüklemiyor, veri toplamıyor, çerez kullanmıyor. Sayfayı yeniden yüklemeden geçiş yapan sitelerde de (Next.js, React vb.) çalışıyor.

## Ne lazım

Ürünün etrafında eşit aralıklarla çekilmiş fotoğraflar. 36 fotoğraf (her biri 10 derece) iyi sonuç veriyor, 24 de olur. Dosya adları sırayla gitmeli:

```
urun_01.webp
urun_02.webp
...
urun_36.webp
```

Fotoğrafları çekerken telefonu sabitleyin, ürünü her seferinde aynı açıda çevirin. Arka planın düz olması işi çok kolaylaştırıyor. Görselleri 1000x1000 px WebP'ye çevirirseniz sayfa da hızlı açılır.

Bu repodaki `sepet-360` klasörü örnek olarak duruyor, dosya düzenini oradan görebilirsiniz.

## Kurulum

### 1. Görselleri bir yere yükleyin

Görsellerin internetten `https` ile açılabilmesi lazım. Kendi sunucunuz varsa oraya koyabilirsiniz. Yoksa GitHub iş görüyor:

1. GitHub'da **Public** bir repo açın.
2. **Add file > Upload files** deyip görsellerin olduğu klasörü sayfaya sürükleyin. Zip olarak değil, klasör olarak yükleyin, yoksa GitHub zip'i açmıyor.
3. **Commit changes** deyin.

Görseller şu adresten açılır:

```
https://cdn.jsdelivr.net/gh/KULLANICI/REPO@main/KLASOR/urun_01.webp
```

Adresi tarayıcıda açıp görselin geldiğini kontrol edin. Gelmezse birkaç dakika bekleyin.

### 2. Scripti sitenize ekleyin

İki yolu var, sitenize hangisi uyuyorsa:

**Dosya olarak:** `zp360.js` dosyasını sitenize yükleyin ve `</body>` etiketinden hemen önce ekleyin:

```html
<script src="/zp360.js"></script>
```

**Yapıştırarak:** Kullandığınız e-ticaret altyapısında "özel kod", "script ekle" ya da "custom code" gibi bir alan varsa, `zp360.js` dosyasının içeriğini başına `<script>`, sonuna `</script>` ekleyerek oraya yapıştırın. Kategori sorarsa **Fonksiyonel** ya da **Zorunlu** seçin. Analitik ya da pazarlama seçerseniz çerezleri reddeden ziyaretçilerde çalışmayabilir.

Sadece belirli sayfalarda çalışsın isterseniz, koddaki `SAYFALAR` listesine sayfa adreslerini yazın:

```js
var SAYFALAR = ['/urun-adresi'];
```

Boş bırakırsanız, aşağıdaki div hangi sayfadaysa orada çalışır.

### 3. Div'i sayfaya koyun

Görüntüleyicinin çıkmasını istediğiniz yere (örneğin ürün açıklamasına, HTML modunda) `ornek-div.html` içindekini yapıştırın. Adresleri kendi görsellerinizle değiştirin.

| Ayar | Ne işe yarar |
|---|---|
| `data-base` | Görsel adresinin numaradan önceki kısmı |
| `data-ext` | Dosya uzantısı, varsayılan `.webp` |
| `data-count` | Kaç görsel olduğu, varsayılan 36 |
| `data-logo` | Köşedeki logo (isteğe bağlı) |
| `data-logo-alt` | Logonun alt metni |
| `data-label` | Ekran okuyucular için ürün adı |
| `data-color` | Buton ve çubuk rengi, örn. `#c0392b` |
| `data-thumbs` | Alttaki küçük resim sayısı, varsayılan 10 |
| `data-autoplay` | `false` yazarsanız kendi kendine dönmez |

## Sorun çıkarsa

- **Hiçbir şey görünmüyorsa:** Div'in sayfada durduğundan emin olun, bazı editörler kaydederken `data-` ile başlayan ayarları siliyor. Scriptin sitede yüklü ve açık olduğuna da bakın.
- **Kutu var ama görsel boşsa:** Görsel adresi yanlıştır ya da `https` değildir. Adresi tarayıcıda tek başına açıp kontrol edin.
- **Görseller değişmiyorsa:** jsDelivr eski hâli önbellekte tutuyor olabilir. `https://purge.jsdelivr.net/gh/KULLANICI/REPO@main/KLASOR/urun_01.webp` adresini bir kere açın.

Kapatmak isterseniz scripti kaldırmanız ya da devre dışı bırakmanız yeterli, sitenin geri kalanına dokunmuyor.

## Lisans

MIT. İstediğiniz gibi kullanabilir, değiştirebilirsiniz. Bir sorun çıkarsa sorumluluk kabul etmiyoruz, kendi sitenizde denemeden kullanmayın.

Hata bulursanız ya da öneriniz varsa Issues kısmından yazabilirsiniz.
