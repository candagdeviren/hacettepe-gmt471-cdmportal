# data/

Test ve örnek verileri.

## Klasörler

- `ornek/` — CCSDS 508.0-B-1 standardının kendi örnek CDM dosyaları. Ayrıştırıcı testlerinin referansı. Depoya dahildir.
- `kelvins/` — ESA Kelvins veri seti. **Depoya dahil değil** (`.gitignore`'da). Herkes kendi bilgisayarına indirir.
- `tle/` — CelesTrak / Space-Track'ten çekilen TLE dosyaları. Depoya dahil değil.

## Veri kaynakları

| Kaynak | Adres | Not |
| --- | --- | --- |
| CCSDS örnekleri | https://ccsds.org/Pubs/508x0b1e2c2.pdf | Standardın 3.6 bölümü |
| ESA Kelvins | https://kelvins.esa.int/collision-avoidance-challenge/data/ | Anonimleştirilmiş; mutlak zaman ve konum yok |
| CelesTrak | https://celestrak.org | TLE, ücretsiz, kayıt gerekmez |
| Space-Track | https://www.space-track.org | TLE ve katalog, ücretsiz kayıt gerekli |

## Kural

Büyük veri dosyaları depoya konmaz. İndirilen her veri setinin nereden, ne zaman ve hangi parametrelerle alındığı bu dosyaya yazılır.
