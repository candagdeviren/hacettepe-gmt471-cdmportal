# Literatür ve mevcut çalışmalar

Raporun "literatür taraması" ve "mevcut çalışmalar" bölümlerinin ham malzemesi. Yeni kaynak okuyan herkes buraya bir satır eklesin.

---

## Standart

**CCSDS 508.0-B-1 — Conjunction Data Message** (Haziran 2013, Teknik Düzeltme 2 ile Ekim 2021)
https://ccsds.org/Pubs/508x0b1e2c2.pdf

Projenin temel referansı. Yakınlaşma analizi üreten kurumlarla uydu operatörleri arasındaki mesaj formatını tanımlar.

Bizim için kritik bölümler:
- **Bölüm 3** — KVN formatının yapısı ve tüm alan tanımları. Ayrıştırıcı bu bölüme göre yazılacak.
- **Bölüm 4** — XML formatı.
- **Ek D** — Formatın neden böyle tasarlandığı. Raporun giriş bölümü için gerekçeler burada.
- **Ek E** — RTN/TVN koordinat sistemleri, kovaryans, Pc yöntemlerinin tanımları.
- **Ek F** — Çarpışma olasılığı literatürünün temel kaynak listesi.

---

## Veri kaynakları

**ESA Kelvins — Spacecraft Collision Avoidance Challenge**
https://kelvins.esa.int/collision-avoidance-challenge/data/
Herkese açık tek gerçek CDM koleksiyonu. 2015–2019 arası ESA tarafından toplanmış; 15.321 yakınlaşma olayına ait 199.082 CDM. Anonimleştirilmiş: mutlak zaman ve bazı yörünge elemanları yok, yalnızca göreli durumlar var.

**CelesTrak** https://celestrak.org · **Space-Track** https://www.space-track.org
TLE yörünge verileri, ücretsiz. SOCRATES servisi günlük yakınlaşma listeleri üretir.

---

## Benzer araçlar

| Araç | Ne yapıyor | Bizim farkımız |
| --- | --- | --- |
| **KeepTrack.space** | Açık kaynak uzay görselleştirme platformu. Collisions eklentisi hazır çarpışma listesi gösterir; Debris Screening eklentisi uydu etrafında arama hacmi çizer. | Onların çizdiği kutu bir arama filtresi, bizimki verinin kendisinden gelen kovaryans hacmi. Ayrıca CDM'i doğrudan okumuyorlar. |
| **Stuff in Space** | WebGL ile yörüngedeki nesnelerin gerçek zamanlı 3B haritası. | Yalnızca konum gösterir, belirsizlik ve risk analizi yok. |
| **AstriaGraph** (UT Austin) | Açık kaynak yörünge nesnesi veri ve görselleştirmesi; yakın geçişleri gösterebiliyor. | Kovaryans görselleştirmesi ve XR yok. |
| **Privateer Wayfinder** | AstriaGraph'ın ticari devamı. Crow's Nest ile NASA CARA tabanlı ücretsiz risk değerlendirmesi. | Ekran tabanlı, CDM girdisi almıyor. |
| **LeoLabs Space Platform** | Ticari. Günün yakınlaşmaları, ıskalama mesafesi ve Pc ile listeleniyor. | Ücretsiz görünümde kovaryans gösterilmiyor; derin özellikler lisans arkasında. |
| **SatGuard** | Açık kaynak Python hattı: SGP4, Pc (Foster/Chan/Alfano), CDM üretimi, CesiumJS küresi. MIT. | Bize en yakın proje. **Kodu mutlaka incelenmeli.** |
| **oacmpy** | CCSDS mesajlarını (OEM, AEM, CDM) Cesium'un CZML formatına çeviriyor. | Ayrıştırma + görselleştirme köprüsü için doğrudan örnek. |
| **Conjunction Watch** | Tüm katalogu tarayıp yaklaşan yakın geçişleri 3B görünümle listeliyor. | Tarama odaklı, belirsizlik yok. |

---

## Akademik kaynaklar

**Görselleştirme ve XR**

- Nejad ve ark., "Impacts of 3D visualizations and virtual reality in display designs for remote monitoring of satellite operations", *Frontiers in Virtual Reality*, 2025. Projeyle en örtüşen çalışma. Senaryoda çöp uydusunu çevreleyen elipsoid konum belirsizliğini gösteriyor ve çarpışma olasılığını izlemek için kullanılıyor. Bulgu: görselleştirmeler kavrama ve öngörü düzeyindeki durumsal farkındalığı iyileştiriyor, ancak VR algılama düzeyini azaltıyor. Tartışma bölümü için değerli.
- AR tabanlı yörünge sistemleri ve uzay çöpü görselleştirmesi, 2025. HoloLens 2 üzerinde LEO/MEO/GEO çöp görselleştirmesi.

**Çarpışma olasılığı**

- Alfano, "Probability of Collision: Valuation, variability, visualization, and validity", *Acta Astronautica*. Üç boyutlu problem, göreli hız vektörüne dik karşılaşma düzlemine yansıtılarak iki boyuta indirgeniyor; kovaryans elipsoidi elipse, çarpışma tüpü daireye dönüşüyor.
- Uluğ ve ark. (ESA), "Spacecraft Collision Avoidance Challenge: design and results", 2020, arXiv:2008.03069. Kelvins veri setinin resmî makalesi. İlk CDM'i izleyen günlerde düzenli güncellemeler geliyor ve zamanla konum belirsizlikleri azalıyor — portalda "belirsizliğin küçülmesi" animasyonu için fikir kaynağı.
- CCSDS Ek F'deki temel kaynaklar: Foster & Estes (1992), Chan (1997), Patera (2001), Alfano (2005), McKinley (2006), Alfriend ve ark. (1999).

---

## Literatür boşluğu

CDM üzerine makine öğrenmesi literatürü zengin, 3B uydu görselleştirmesi için açık kaynak araçlar mevcut, VR'ın uydu operasyonlarındaki etkisi akademik olarak ölçülmüş. Ancak bu üçünü birleştiren — CDM'i doğrudan girdi alan, web tabanlı, açık erişimli ve sürükleyici bir analiz portalı — bulunamadı. Projenin özgünlük iddiası burada.
