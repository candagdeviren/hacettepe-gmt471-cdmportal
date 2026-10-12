# parser/ — 1. katman: Ayrıştırma

**Sorumlu:** (atanacak)

## Görev

CDM dosyasını (KVN ve XML) okuyup `docs/veri-semasi.md` içindeki `conjunction.json` yapısına çevirmek.

## Yapılacaklar

- [ ] KVN formatını okuyan ayrıştırıcı
- [ ] XML formatını okuyan ayrıştırıcı
- [ ] Zorunlu alanların varlığını doğrulama
- [ ] Birim kontrolü (köşeli parantez içindeki birimler standartla uyuşuyor mu)
- [ ] `data/ornek/` içindeki dosyalarla test

## Dikkat edilecekler

- Satır başına tek `anahtar = değer` ataması var (CCSDS 6.3.1.4).
- Anahtar sırası standartta sabit (6.3.1.9), ama ayrıştırıcı sıraya bağımlı olmamalı.
- `OBJECT = OBJECT1` ve `OBJECT = OBJECT2` satırları iki nesne bloğunu ayırır. Aynı anahtar (örneğin `X`) her iki blokta da geçer.
- `COMMENT` ile başlayan satırlar atlanır, ama bazı faydalı bilgiler (apogee, perigee, eğim) yorum içinde geliyor.
- Birimler değerden en az bir boşlukla ayrılır ve köşeli parantez içindedir (6.3.3).
- Tüm zaman etiketleri UTC'dir. İki format mümkün: `yyyy-mm-ddThh:mm:ss.ddd` ve `yyyy-dddThh:mm:ss.ddd`.

## Referans

CCSDS 508.0-B-1, Bölüm 3 (KVN) ve Bölüm 4 (XML).
