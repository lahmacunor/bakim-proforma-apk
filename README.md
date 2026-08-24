# bakim-proforma-apk

Sabit APK indirme sayfaları — [Bakım Proforma App](https://github.com/lahmacunor)
için. Her yeni build'de bu repodaki `panel.html` / `app.html` içindeki link
güncellenir, Berkay'a hep aynı jsDelivr adresi gönderilir.

## Adresler (jsDelivr üzerinden)

- Panel: `https://cdn.jsdelivr.net/gh/lahmacunor/bakim-proforma-apk@main/panel.html`
- App: `https://cdn.jsdelivr.net/gh/lahmacunor/bakim-proforma-apk@main/app.html`

## Neden

Ham `expo.dev/artifacts/...apk` linki doğrudan SMS/iMessage'de gönderildiğinde
telefon tarafında birden fazla otomatik indirme tetikleniyordu (muhtemelen
mesaj önizlemesi binary'i kendisi de çekiyor). Bu sayfalar küçük bir HTML
önizlemesi taşıdığı için önizleme çekimi indirme tetiklemiyor, indirme sadece
kullanıcının "APK İNDİR" butonuna bilinçli dokunmasıyla oluyor. Ayrıca link
her zaman aynı olduğu için eski build'ler telefonda birikmiyor.

## Güncelleme

`panel.html` / `app.html` içindeki `<a class="btn" href="...">` satırındaki
linki ve "Son güncelleme" tarihini değiştir, commit+push et. jsDelivr cache
gecikmesi olursa `https://purge.jsdelivr.net/gh/lahmacunor/bakim-proforma-apk@main/panel.html`
adresine bir GET isteği at.
