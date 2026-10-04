# Yayın TV (Android TV / Android box)

## APK üretme
**A) Android Studio:** klasörü aç → Build > Build APK(s) → `app/build/outputs/apk/debug/app-debug.apk`
**B) Bilgisayarında Gradle varsa:** `gradle assembleDebug`
**C) Kurulumsuz:** klasörü GitHub'a yükle → Actions > Build APK > çıkan `YayinTV-apk` dosyasını indir.

## Cihaza kurma
- Box'ta "Bilinmeyen kaynaklar"a izin ver, APK'yı USB / "Send Files to TV" / Downloader ile kur.
- Veya ADB: `adb connect KUTU_IP:5555 && adb install -r app-debug.apk`

## Kumanda
Yukarı/Aşağı: kanal değiştir · OK / Sol / Menü: kanal listesi · listede OK: seç · Geri: listeyi kapat, tekrar Geri: çık.
Son izlenen yayın açılışta otomatik başlar.

## Liste güncelleme
`app/src/main/assets/www/db.json` dosyasını değiştirip yeniden derle.
Kayda `"hls": "https://.../index.m3u8"` eklersen o kayıt YouTube yerine hls.js ile oynar.
