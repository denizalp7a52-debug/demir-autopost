# Demir Zeytincilik · otomatik paylaşım (@demiroliveoil)

GitHub Actions üzerinde ücretsiz çalışır. Bilgisayarın açık olması gerekmez.

- `schedule.json`: 30 günlük takvim, 5 Kasım – 4 Aralık 2026. Saatler UTC'dir.
  - Her gün **12:30** (Roma) / 14:30 (TR): Instagram story
  - Her gün **19:00** (Roma) / 21:00 (TR): Instagram gönderisi (açıklama + 5 hashtag + alt metin)
  - **20:30** (Roma) / 22:30 (TR): Reels. 1–7. günler her gün; Antik Anadolu serisi 9, 13, 17 ve 21. günlerde.
- `media/`: paylaşılacak görseller ve videolar (tek klasörde)
- `posted.json`: neyin paylaşıldığının kaydı (sistem kendisi günceller)
- `scripts/autopost.py`: paylaşım programı

## Sık işler

- **Takvimi görmek:** Actions → "Otomatik paylaşım" → Run workflow → `status`
- **Kontrol:** Run workflow → `check` (hesap, görsel ve video adresleri)
- **Durdurmak:** Actions → "Otomatik paylaşım" → ⋯ → Disable workflow
- **Deneme modu:** Settings → Variables → `DRY_RUN` = `true` (hiçbir şey paylaşılmaz)
- **Açıklamayı değiştirmek:** `schedule.json` içinde ilgili satırın `caption` alanını düzenle.
- **Yeni içerik:** `media/` içine dosyayı koy, `schedule.json`'a bir satır ekle (`kind`: `story`, `feed` ya da `reel`).

Notlar:
- GitHub zamanlayıcısı 5–20 dakika gecikebilir. Gecikme 12 saati aşarsa paylaşım "kaçırıldı" sayılır.
- Bir paylaşım başarısız olursa GitHub e-posta gönderir.
- Instagram en fazla 5 hashtag kabul ediyor. Açıklamalarda anahtar kelimeler ilk satırda.
- Story'lerdeki anket ve test çıkartmaları API ile eklenemiyor; istersen o günler story'yi telefondan elle paylaş.
