# compute/ — 2. katman: Hesap

**Sorumlu:** (atanacak)

## Görev

`conjunction.json` dosyasını alıp `scene.json` üretmek.

## Yapılacaklar

- [ ] TCA çevresinde yörünge yayılımı (konum serisi üretme)
- [ ] Alt üçgen kovaryansı tam 6×6 matrise genişletme
- [ ] Konum alt matrisinden (3×3) özdeğer ve özvektör çıkarma
- [ ] Elipsoid yarı eksenleri ve dönme matrisi üretme
- [ ] Çarpışma olasılığı hesabı (Foster-1992 ile başla)
- [ ] CDM'deki Pc değeriyle karşılaştırma ve doğrulama

## Dikkat edilecekler

- Durum vektörü ve kovaryans **TCA anında** verilir (CCSDS 5.2.2). Animasyon için öncesi ve sonrası hesaplanmalı.
- Kovaryans değerleri sol üstten sağ alta, satır satır, alt üçgen formda sıralanır (5.2.7).
- Kovaryans RTN sisteminde, durum vektörü EME2000 gibi bir atalet sisteminde. Elipsoidi sahneye yerleştirmeden önce dönüşüm gerekir.
- Köşegen terimlerden biri sıfırsa, o terime ait tüm satır ve sütun yok sayılmalı (5.2.8).
- Birim karışıklığına dikkat: konum km, kovaryans m².
- Özdeğerlerin karekökü standart sapmaları verir; elipsoidin yarı eksenleri bunlardır. Hangi σ seviyesinin çizildiği ekranda belirtilmeli.

## Kaynaklar

- CCSDS 508.0-B-1, Ek E (RTN tanımı, kovaryans) ve Ek F (Pc kaynakları)
- Foster & Estes (1992), Alfano (2005)
- SatGuard projesi — aynı girdiyle sonuç karşılaştırması için
