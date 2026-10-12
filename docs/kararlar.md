# Karar kaydı

Projede alınan her önemli kararı buraya yazıyoruz: ne, neden, kim, ne zaman. Rapor yazarken en çok bu dosyaya ihtiyaç duyulacak.

Format: tarih, karar, gerekçe. Yeni kararlar en üste eklenir.

---

## 2026-10-?? — Konu seçimi

**Karar:** GMT471 bitirme projesi konusu olarak "Development of an Immersive Conjunction Data Message Analysis Portal" seçildi. Danışman: Dr. Öğr. Üyesi Murat Durmaz.

**Gerekçe:** Konu uzay durumsal farkındalığı, web geliştirme ve konum belirsizliği analizini bir araya getiriyor. Bölüm müfredatındaki GNSS ve dengeleme konularıyla doğrudan bağlantılı; aynı zamanda web ve 3B görselleştirme tarafında yeni beceri kazandırıyor.

---

## 2026-10-?? — Kapsam sınırı: CDM üretimi yok

**Karar:** Kendi yakınlaşma senaryolarımızı üretmeyeceğiz. Hazır CDM verisiyle çalışılacak.

**Gerekçe:** Projenin odağı görselleştirme ve analiz; senaryo üretimi ayrı bir iş yükü ve kapsamı gereksiz büyütüyor.

**Açık nokta:** Herkese açık tek CDM koleksiyonu olan ESA Kelvins veri seti anonimleştirilmiş; mutlak zaman ve konum içermiyor, bu yüzden doğrudan 3B sahneye yerleştirilemiyor. Hocaya başka bir kaynak olup olmadığı sorulacak.

---

## 2026-10-?? — Dört katmanlı mimari

**Karar:** Sistem dört bağımsız katmana ayrıldı: ayrıştırma, hesap, 3B sahne, XR. Katmanlar birbirine yalnızca `docs/veri-semasi.md` içindeki JSON sözleşmesi üzerinden bağlanır.

**Gerekçe:** Dört kişilik ekipte herkes kendi katmanını diğerleri bitmeden geliştirip test edebilsin. Bir katman gecikirse diğerleri durmaz.

---

## Şablon

```
## YYYY-MM-DD — Karar başlığı

**Karar:** Ne yapmaya karar verildi.

**Gerekçe:** Neden bu seçildi, alternatifler nelerdi.

**Karara katılanlar:** İsimler.
```
