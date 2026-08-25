# bakim-proforma-apk

Sabit APK indirme sayfaları — [Bakım Proforma App](https://github.com/lahmacunor)
için. Her yeni build'de bu repodaki `panel.html` / `app.html` içindeki link
güncellenir, Berkay'a hep aynı GitHub Pages adresi gönderilir.

## Adresler (GitHub Pages üzerinden)

- Panel: `https://lahmacunor.github.io/bakim-proforma-apk/panel.html`
- App: `https://lahmacunor.github.io/bakim-proforma-apk/app.html`

**Not (2026-08-25):** İlk denemede jsDelivr kullanılmıştı ama jsDelivr
`.html` dosyalarını `Content-Type: text/plain` ile sunuyor —
tarayıcı sayfayı render etmek yerine kaynak kodu olarak gösteriyordu.
GitHub Pages doğru `text/html` content-type ile sunduğu için buna
geçildi (`gh api -X POST repos/lahmacunor/bakim-proforma-apk/pages`).

## Neden

Ham `expo.dev/artifacts/...apk` linki doğrudan SMS/iMessage'de gönderildiğinde
telefon tarafında birden fazla otomatik indirme tetikleniyordu (muhtemelen
mesaj önizlemesi binary'i kendisi de çekiyor). Bu sayfalar küçük bir HTML
önizlemesi taşıdığı için önizleme çekimi indirme tetiklemiyor, indirme sadece
kullanıcının "APK İNDİR" butonuna bilinçli dokunmasıyla oluyor. Ayrıca link
her zaman aynı olduğu için eski build'ler telefonda birikmiyor.

## Güncelleme

`panel.html` / `app.html` içindeki `<a class="btn" href="...">` satırındaki
linki ve "Son güncelleme" tarihini değiştir, commit+push et. GitHub Pages
genelde saniyeler içinde günceller, gecikirse birkaç dakika bekleyip
tekrar dene.
