# CDM Analiz Portalı

Conjunction Data Message (CDM) dosyalarını okuyup iki uzay nesnesinin yaklaşmasını, konum belirsizliklerini ve çarpışma riskini web üzerinde 3B ve VR/AR ortamında görselleştiren portal.

**Hacettepe Üniversitesi — Geomatik Mühendisliği**
GMT471 Bitirme Projesi, 2026–2027
Danışman: Dr. Öğr. Üyesi Murat Durmaz

---

## Durum

Planlama aşaması. Aşama 0: kurulum ve ortak dil.

## Problem

Uydu operatörlerine gönderilen CDM mesajları, iki uzay nesnesinin tehlikeli yaklaşmasını standart bir formatta bildirir. Mesaj sayılardan oluşur ve içindeki konum belirsizliği bilgisi (kovaryans matrisi) çıplak gözle yorumlanamaz. Bu proje, o mesajı gözle görülebilir bir sahneye dönüştürür.

## Mimari

Veri dört katmandan geçer:

| # | Katman | Girdi | Çıktı | Klasör |
| --- | --- | --- | --- | --- |
| 1 | Ayrıştırma | CDM (KVN / XML) | JSON | `parser/` |
| 2 | Hesap | JSON | Sahne verisi (konum serisi, elipsoid, Pc) | `compute/` |
| 3 | 3B sahne | Sahne verisi | Web sayfası | `web/` |
| 4 | XR | Web sayfası | VR / AR oturumu | `xr/` |

Katmanlar arasındaki sözleşme `docs/veri-semasi.md` dosyasında tanımlıdır. Bu şema sabitlenmeden kod yazılmaz.

## Kapsam

**Kapsam içi:** Hazır CDM dosyalarını okumak, yaklaşmayı canlandırmak, kovaryans elipsoidini çizmek, çarpışma olasılığını göstermek, sahneyi WebXR ile sunmak.

**Kapsam dışı:** Yeni bir çarpışma olasılığı yöntemi geliştirmek, tüm katalogu tarayarak yakınlaşma aramak, manevra planlaması önermek, gerçek zamanlı operasyonel servis sunmak.

## Ekip

| İsim | Sorumluluk | GitHub |
| --- | --- | --- |
| Remzi Can Dağdeviren | | |
| Abdullah Kasım İlen | | |
| Zine Toytekin | | |
| | | |

## Klasörler

```
docs/      proje dokümanları: literatür, kararlar, veri şeması
data/      örnek ve test CDM dosyaları
parser/    1. katman — CDM ayrıştırma
compute/   2. katman — yörünge, kovaryans, olasılık
web/       3. katman — CesiumJS sahnesi
xr/        4. katman — WebXR
```

## Çalışma düzeni

- `main` dalına doğrudan yazılmaz.
- Herkes kendi dalında çalışır: `parser/cdm-okuma`, `web/zaman-cubugu` gibi.
- Birleştirme Pull Request ile yapılır, en az bir kişi gözden geçirir.
- Her önemli karar `docs/kararlar.md` dosyasına tarihli olarak yazılır.

## Kaynaklar

- [CCSDS 508.0-B-1 — Conjunction Data Message](https://ccsds.org/Pubs/508x0b1e2c2.pdf)
- [ESA Kelvins — Spacecraft Collision Avoidance Challenge veri seti](https://kelvins.esa.int/collision-avoidance-challenge/data/)
- [CelesTrak](https://celestrak.org) · [Space-Track](https://www.space-track.org)
- [CesiumJS](https://cesium.com/platform/cesiumjs/) · [WebXR](https://immersiveweb.dev/)

## Lisans

MIT. Ayrıntı için `LICENSE` dosyasına bakın.
