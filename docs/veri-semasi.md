# Katmanlar arası veri şeması

Bu dosya projenin en kritik sözleşmesidir. Katmanlar birbirinin koduna değil, yalnızca bu şemaya bağlıdır. Şema sabitlenmeden kod yazılmaz.

**Durum:** TASLAK — ekipçe onaylanmadı.

---

## 1. Ayrıştırma katmanının çıktısı: `conjunction.json`

CDM dosyasındaki alanlar birebir korunur, isimler sadeleştirilir. Birimler CCSDS standardındakiyle aynı bırakılır: konum km, hız km/s, mesafe m, kovaryans m².

```json
{
  "mesaj": {
    "surum": "1.0",
    "olusturma_tarihi": "2010-03-12T22:31:12.000",
    "uretici": "JSPOC",
    "mesaj_id": "201113719185"
  },
  "goreli": {
    "tca": "2010-03-13T22:37:52.618",
    "iskalama_mesafesi_m": 715.0,
    "goreli_hiz_ms": 14762.0,
    "goreli_konum_rtn_m": [27.4, -70.2, 711.8],
    "goreli_hiz_rtn_ms": [-7.2, -14692.0, -1437.2],
    "carpisma_olasiligi": 4.835e-05,
    "olasilik_yontemi": "FOSTER-1992"
  },
  "nesneler": [
    {
      "sira": 1,
      "katalog_no": "12345",
      "ad": "SATELLITE A",
      "uluslararasi_tanimlayici": "1997-030E",
      "tip": "PAYLOAD",
      "manevra_yetenegi": "YES",
      "referans_sistemi": "EME2000",
      "kovaryans_yontemi": "CALCULATED",
      "durum_vektoru": {
        "konum_km": [2570.097065, 2244.654904, 6281.497978],
        "hiz_kms": [4.418769571, 4.833547743, -3.526774282]
      },
      "kovaryans_rtn": {
        "CR_R": 4.142e+01,
        "CT_R": -8.579e+00,
        "CT_T": 2.533e+03,
        "CN_R": -2.313e+01,
        "CN_T": 1.336e+01,
        "CN_N": 7.098e+01,
        "CRDOT_R": 2.520e-03,
        "CRDOT_T": -5.476e+00,
        "CRDOT_N": 8.626e-04,
        "CRDOT_RDOT": 5.744e-03,
        "CTDOT_R": -1.006e-02,
        "CTDOT_T": 4.041e-03,
        "CTDOT_N": -1.359e-03,
        "CTDOT_RDOT": -1.502e-05,
        "CTDOT_TDOT": 1.049e-05,
        "CNDOT_R": 1.053e-03,
        "CNDOT_T": -3.412e-03,
        "CNDOT_N": 1.213e-02,
        "CNDOT_RDOT": -3.004e-06,
        "CNDOT_TDOT": -1.091e-06,
        "CNDOT_NDOT": 5.529e-05
      },
      "ek": {
        "alan_m2": 5.2,
        "kutle_kg": 251.6
      }
    }
  ]
}
```

### Notlar

- `nesneler` dizisi her zaman iki elemanlıdır (Object1 ve Object2).
- Kovaryans, standartta alt üçgen formda gelir. Tam 6×6 matrise genişletmek hesap katmanının işidir.
- İsteğe bağlı alanlar eksikse `null` yazılır, anahtar silinmez.
- `carpisma_olasiligi` mesajda yoksa `null` olur; o durumda hesap katmanı kendisi hesaplar.

---

## 2. Hesap katmanının çıktısı: `scene.json`

Görselleştirme katmanı yalnızca bu dosyayı okur. Astronomi veya matris bilgisi gerektirmez.

```json
{
  "tca": "2010-03-13T22:37:52.618",
  "zaman_araligi_s": [-600, 600],
  "adim_s": 10,
  "nesneler": [
    {
      "sira": 1,
      "ad": "SATELLITE A",
      "tip": "PAYLOAD",
      "yol": [
        { "t": -600, "konum_km": [2570.1, 2244.7, 6281.5] },
        { "t": -590, "konum_km": [2596.6, 2273.7, 6260.3] }
      ],
      "elipsoid": {
        "yari_eksenler_m": [6.4, 50.3, 8.4],
        "donme_matrisi": [[1,0,0],[0,1,0],[0,0,1]],
        "sigma": 1
      }
    }
  ],
  "risk": {
    "iskalama_mesafesi_m": 715.0,
    "goreli_hiz_ms": 14762.0,
    "carpisma_olasiligi": 4.835e-05,
    "yontem": "FOSTER-1992",
    "kaynak": "hesaplandi"
  }
}
```

### Notlar

- `t`, TCA'ya göre saniye cinsinden görelidir. Negatif değer yaklaşmadan önce demektir.
- `yari_eksenler_m`, kovaryansın özdeğerlerinin karekökü. `sigma` kaç standart sapmalık hacmin çizildiğini söyler (1σ varsayılan, arayüzde değiştirilebilir).
- `donme_matrisi`, elipsoidi RTN çerçevesinden sahne çerçevesine döndürür.
- `risk.kaynak` değeri `"cdm"` ya da `"hesaplandi"` olur. İkisi de varsa ikisini de göstermek iyi olur; karşılaştırma raporda işe yarar.

---

## Açık sorular

- [ ] Zaman aralığı ve adım sabit mi olacak, kullanıcı mı ayarlayacak?
- [ ] Yol noktaları hangi referans sisteminde verilecek? (EME2000 mi, Cesium'un beklediği ECEF mi?)
- [ ] Elipsoid sadece TCA anında mı, yoksa her adımda mı çizilecek?
- [ ] Alan adları Türkçe mi İngilizce mi kalsın? (Şu an Türkçe; kod İngilizce olacaksa değiştirelim.)
