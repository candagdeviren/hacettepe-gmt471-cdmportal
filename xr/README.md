# xr/ — 4. katman: VR / AR

**Sorumlu:** (atanacak)

## Görev

3B sahneyi WebXR ile VR gözlükte ve telefonda AR olarak açılabilir hale getirmek.

## Yapılacaklar

- [ ] WebXR desteğinin algılanması, "VR'da aç" düğmesi
- [ ] VR oturumunda sahnenin açılması
- [ ] AR modunda sahnenin yüzeye yerleştirilmesi
- [ ] Oturum içinde temel gezinme (yakınlaştırma, döndürme, zamanı oynatma)
- [ ] Hangi cihaz ve tarayıcıların desteklediğinin test edilmesi ve raporlanması

## Dikkat edilecekler

- Bu katman en sona bırakıldı: diğer üçü çalışmadan gösterilecek bir şey yok.
- Fiziksel gözlük bulunamazsa tarayıcının WebXR emülatör eklentisiyle test edilebilir.
- AR modunda ölçek seçimi kritik: sahne masaüstü boyutuna indirilmeli.
- Literatürde VR'ın algılama düzeyindeki durumsal farkındalığı azaltabildiğine dair bulgu var (Nejad ve ark., 2025). Test sonuçlarını raporda bu bulguyla karşılaştırmak iyi olur.

## Kaynaklar

- WebXR: https://immersiveweb.dev/
- CesiumJS ile WebXR entegrasyonu örnekleri
