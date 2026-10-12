# web/ — 3. katman: 3B sahne

**Sorumlu:** (atanacak)

## Görev

`scene.json` dosyasını okuyup tarayıcıda 3B sahneyi çizmek.

## Yapılacaklar

- [ ] CesiumJS kurulumu, ekranda Dünya
- [ ] Dosya yükleme ekranı
- [ ] İki nesnenin yörüngelerinin çizimi
- [ ] Zaman çubuğu ve animasyon kontrolü
- [ ] Belirsizlik elipsoidlerinin yarı saydam çizimi
- [ ] Bilgi paneli: TCA, ıskalama mesafesi, göreli hız, çarpışma olasılığı
- [ ] TCA anına atlama düğmesi

## Dikkat edilecekler

- Ölçek problemi bu katmanın en büyük zorluğu: yörünge yarıçapı binlerce km, ıskalama mesafesi birkaç yüz metre. İki nesne tüm Dünya görünümünde tek piksel gibi görünür. Yakınlaştırılmış ayrı bir görünüm gerekebilir.
- Elipsoid de aynı sebeple çok küçük kalacak. Ölçek çarpanı seçeneği sunulabilir, ama ekranda açıkça yazılmalı — abartılmış bir elipsoid yanıltıcı olur.
- Renk anlam taşımalı: uydu ve çöp farklı, risk seviyesi farklı renkte.

## Kaynaklar

- CesiumJS: https://cesium.com/learn/cesiumjs-learn/
- oacmpy — CCSDS mesajlarını Cesium'un CZML formatına çeviren örnek
- KeepTrack.space — arayüz ve hacim çizimi örneği
