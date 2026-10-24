# RusDNS VPN

Tek dokunuşla bağlanan, DNS sorgularını Rusya'daki Yandex DNS'e (77.88.8.8 / 77.88.8.1) yönlendiren Android uygulaması. Uzak sunucu gerekmez, hesap yok, ayar yok.

## APK nasıl alınır

### Yol 1: GitHub ile (bilgisayara bir şey kurmadan)
1. github.com'da boş bir repo aç, bu klasörün içeriğini yükle (`.github` klasörü dahil).
2. Repo'da **Actions** sekmesine gir, "APK derle" workflow'unu çalıştır (otomatik de çalışır).
3. Bittiğinde çalışmanın sayfasından **RusDNS-VPN-apk** dosyasını indir, içindeki `app-debug.apk` dosyasını telefona kur.

### Yol 2: Android Studio
1. Klasörü Android Studio ile aç, Gradle senkronizasyonunun bitmesini bekle.
2. **Build > Build APK(s)**. APK `app/build/outputs/apk/debug/app-debug.apk` altında oluşur.

Komut satırından: `./gradlew assembleDebug` (JDK 17 ve Android SDK gerekir).

## Kurulum notları
- Telefonda "bilinmeyen kaynaklardan yükleme" izni istenebilir.
- İlk bağlanışta Android bir VPN izni sorar, onaylaman yeterli.
- Telefon ayarlarında **Özel DNS** (Private DNS) kapalı ya da "Otomatik" olmalı. Elle bir sağlayıcı yazılıysa VPN'in DNS'i yok sayılır.

## Ne yapar, ne yapmaz
- Yapar: DNS çözümlemesini Yandex DNS üzerinden yapar. DNS düzeyinde engellenen siteler açılabilir.
- Yapmaz: IP adresini veya konumunu değiştirmez. IP ya da SNI düzeyindeki engelleri aşmaz.
- DNS sorguları şifresiz gider ve Yandex'in sunucularına ulaşır.
