# Depoyu GitHub'a yükleme

Bu dosya bir kez kullanılır, sonra silinebilir.

## 1. Organization aç (önerilir)

GitHub'da sağ üstteki profil menüsü → **Settings** → **Organizations** → **New organization** → **Free** planı seç.

Önerilen ad: `hacettepe-gmt471-cdm`

Neden: dördünüz de eşit sahip olursunuz, mezuniyetten sonra hocaya veya bölüme devredilebilir, CV'de kurumsal durur. Kendi hesabın altında da açabilirsin, o zaman bu adımı atla.

## 2. Boş depo oluştur

Organization (veya kendi hesabın) içinde **New repository**:

- **Repository name:** `cdm-analysis-portal`
- **Visibility:** **Private** (proje bitince public yaparsınız)
- **Add a README file:** işaretleme — zaten var
- **.gitignore:** None — zaten var
- **License:** None — zaten var

## 3. Dosyaları yükle

Bu klasörün içinde terminal aç ve sırayla:

```bash
git init
git add .
git commit -m "Proje iskeleti: README, dokumanlar, klasor yapisi"
git branch -M main
git remote add origin https://github.com/<organizasyon>/cdm-analysis-portal.git
git push -u origin main
```

`<organizasyon>` yerine kendi adını yaz.

Terminal kullanmak istemiyorsan: GitHub'da depo sayfasında **uploading an existing file** bağlantısına tıklayıp bu klasörün içindekileri sürükle-bırak yapabilirsin. Ancak `.gitignore` gibi noktayla başlayan dosyalar bu yöntemle bazen atlanır, kontrol et.

## 4. Ekibi ekle

Depo → **Settings** → **Collaborators and teams** → **Add people**

Abdullah, Zine ve dördüncü kişiyi ekle, hepsine **Write** yetkisi ver.

## 5. main dalını koru

Depo → **Settings** → **Branches** → **Add branch protection rule**

- Branch name pattern: `main`
- **Require a pull request before merging** işaretle
- **Require approvals: 1** seç

Böylece kimse doğrudan `main`'e yazamaz, her değişiklik en az bir kişi tarafından görülür.

## 6. Issue'ları aç

Depo → **Issues** → **New issue**. Yol haritasındaki altı aşamayı birer issue olarak gir:

1. Aşama 0 — Kurulum ve ortak dil
2. Aşama 1 — Ayrıştırıcı ve ilk sahne
3. Aşama 2 — Hareket ve zaman çubuğu
4. Aşama 3 — Belirsizlik ve risk
5. Aşama 4 — XR katmanı
6. Aşama 5 — Test, rapor, sunum

Her birine sorumlu ata. İstersen **Projects** sekmesinden basit bir board (Todo / In progress / Done) ekleyip issue'ları oraya bağla.

## 7. İlk iş

`docs/kararlar.md` ve `README.md` içindeki boş alanları doldurun:

- Ekip tablosundaki sorumluluk ve GitHub kullanıcı adları
- Karar kaydındaki `????` tarihleri
- `docs/veri-semasi.md` sonundaki açık soruları ekipçe karara bağlayın

Şema sabitlenmeden kod yazmaya başlamayın.
