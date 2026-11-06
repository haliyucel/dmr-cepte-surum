# DMR Cepte — Gizlilik Politikası

**Son güncelleme:** 7 Kasım 2026 (sürüm 5.14.1)
**Geliştirici:** TA6HY — Hasan Ali YÜCEL
**İletişim:** haliyucel@gmail.com
**Lisans:** GNU GPL v3

---

## Özet

DMR Cepte bir **amatör telsiz** uygulamasıdır. Uygulamada reklam, analitik ya da
izleme servisi **yoktur**. Geliştiriciye **kendiliğinden hiçbir veri gitmez**;
yalnız iki durumda ve **yalnız sizin onayınızla** geliştiriciye bir e-posta gider:
cihaz raporu ve resmî olmayan kopya bildirimi (§2.4).

Uygulamanın bağlandığı yerler amatör telsiz ağlarının sunucuları, sohbet röleleri
ve birkaç açık servistir; hepsi aşağıda tek tek yazılıdır.

---

## 1. Cihazınızda saklananlar

Aşağıdakiler **yalnızca telsizinizin/telefonunuzun kendi belleğinde** durur.
Uygulamayı kaldırdığınızda silinirler.

| Veri | Neden |
|---|---|
| Çağrı işaretiniz, DMR ID, NXDN ID | Ağlara kimliğinizi bildirmek için (amatör telsizde zorunlu) |
| BrandMeister, ADN, FreeDMR ve TGIF hotspot kimlikleri ve parolaları, BrandMeister API anahtarı, TGIF statik TG API anahtarı | Bu ağlara bağlanmak ve statik grupları yönetmek için |
| EchoLink çağrı işareti, adı ve parolası | EchoLink ağına giriş için |
| Sabit konum ya da son GPS konumu | APRS konum bildirimi, DMR ağlarındaki cihaz kaydı (varsayılan olarak yaklaşık 1 km'ye yuvarlanmış), yer adı ve hava durumu için |
| Çağrı geçmişi, gelen ve giden APRS mesajları, DMR SMS'leri | Listeler ve mesaj kutusu için |
| Rehberim (ad, çağrı işareti, telefon, e-posta, ID'ler) | Kişi seçerek mesaj ya da acil durum SMS'i göndermek için |
| Sohbet geçmişi, sohbet anahtarı ve çağrı işareti–anahtar bağları | Sohbet için (§2.3). Gizli anahtar cihazdan çıkmaz, yedeğe de girmez |
| Ses kayıtları (ses kaydını açtıysanız) | Duyulan çağrıları ve kendi yayınınızı sonra dinlemek için; seçtiğiniz günden sonra silinir |
| Bağlantı günlüğü ve çökme kaydı (`last_crash.txt`) | Bir arıza olduğunda nedenini görebilmek için |
| Ses çözücü eklentisi ve MD-380 firmware'i (onayınızla indirilir) | Telsiz sesini çözmek için |

Parolalar Android'in uygulamaya özel ayar deposunda tutulur ve yalnız ait oldukları
ağa giriş için kullanılır; **geliştiriciye ya da üçüncü bir tarafa gönderilmez.**
Günlük ve çökme kaydı kendiliğinden hiçbir yere gitmez (cihaz raporu için bkz. §2.4).

---

### Konum üzerinde denetiminiz

Konum izni ilk kez sorulmadan önce uygulama konumun nereye gittiğini bir ekranda anlatır;
orada konumu hiç açmamayı seçebilirsiniz. Sonradan Telsiz Ayarları'ndan konumu tamamen
kapatabilir, sabit bir konum girebilir ya da ağlara tam konum gönderimini açabilirsiniz
(varsayılan kapalı: yaklaşık 1 km). Bu politika uygulamanın içinden de okunabilir
(menünün en altındaki geliştirici ve sürüm satırı > Gizlilik politikası).

## 2. Dışarıya gönderilenler

Uygulama yalnızca aşağıdaki sunuculara bağlanır ve her birine yalnızca yazılan
bilgiyi gönderir.

### 2.1 Amatör telsiz ağları (uygulamanın asıl işi)

| Sunucu | Gönderilen | Neden |
|---|---|---|
| BrandMeister master sunucusu | Hotspot kimliği ve parola, çağrı işareti, DMR ID, konum (GPS konumu yaklaşık 1 km'ye yuvarlanır; elle girdiğiniz ya da "Ağlara tam konum gönder" açıkken tam) ve yer adı, konuştuğunuzda **sesiniz**, gönderdiğiniz DMR SMS'leri | DMR bağlantısı. Cihaz kaydı BrandMeister'da herkese açıktır |
| ADN Systems, FreeDMR, TGIF sunucuları (açtıysanız) | Hotspot kimliği ve parola, çağrı işareti, DMR ID, konum (BrandMeister'daki gibi yuvarlanır), konuştuğunuzda **sesiniz** | DMR bağlantısı |
| NXDN, YSF, D-STAR, P25 ve M17 reflektörleri (açtıysanız) | Çağrı işareti (NXDN'de NXDN ID), konuştuğunuzda **sesiniz** | Bağlantı |
| EchoLink adresleme sunucuları, relay'ler ve node'lar | Çağrı işareti, EchoLink parolası, adınız ve EchoLink bilgi metniniz, konuştuğunuzda **sesiniz** | EchoLink bağlantısı |
| APRS-IS sunucusu | Çağrı işareti, **konumunuz** (konum gönderimi açıksa), gönderdiğiniz APRS mesajları. SMS, e-posta ya da WhatsApp geçidine yazdığınız mesajda alıcının numarası/adresi de mesajla birlikte gider | APRS |
| BrandMeister Hoseline (`hose.brandmeister.network`) | Dinlediğiniz TG numarası; kimlik gönderilmez, ağa yayın yapılmaz | Hat meşgulken seçili TG'nin sesini BrandMeister'ın web dinleme akışından çalmak |

**Acil durum (SOS)**, Telsiz Ayarları'ndan açtıysanız ve 5 saniyelik geri sayımda
vazgeçmezseniz: Rehberim'den seçtiğiniz kişiye konumlu bir DMR SMS'i ve herkese açık
bir APRS acil durum konumu gönderir. Konum anahtarı kapalıysa konum gönderilmez.

> **Önemli — amatör telsiz yayını kamuya açıktır.** Çağrı işaretiniz, konumunuz ve
> sesiniz bu ağlarda **herkese açıktır** ve üçüncü taraf siteler (brandmeister.network,
> Hoseline, aprs.fi, aprsdirect vb.) tarafından kaydedilip yıllarca saklanabilir. Bu,
> uygulamanın bir özelliği değil amatör telsizin doğasıdır. Konumunuzun görünmesini
> istemiyorsanız konum gönderimini kapatın.

### 2.2 Yardımcı servisler

| Sunucu | Gönderilen | Neden |
|---|---|---|
| `api.brandmeister.network` | Hotspot kimliğiniz ve API anahtarınız (girdiyseniz) | Statik grupları okumak/değiştirmek, Canlı ekranı |
| `api.tgif.network` | TGIF hotspot kimliğiniz ve TGIF statik TG API anahtarınız (girdiyseniz) | TGIF statik gruplarını okumak (açılışta ve ayar ekranı açılınca bir kez) ve siz isteyince değiştirmek |
| `radioid.net`, `database.radioid.net` | Sorguladığınız çağrı işareti ya da DMR ID | Rehber: kimin konuştuğunu ada çevirmek |
| `nominatim.openstreetmap.org` | **Enlem/boylam** (sizin konumunuz ya da deprem listesindeki yerler) | Yer adını bulmak |
| `api.open-meteo.com` | **Enlem/boylamınız** | Hava durumu |
| `www.seismicportal.eu` | Seçtiğiniz ülkenin sınır kutusu (kişisel konum değil) | Deprem listesi |
| `www.pistar.uk`, `dmr.qso1.net`, `adn.systems` ve ADN sunucuları, `freedmr.dvswitch.org`, `tgif.network`, `ysflive.com`, seçili D-STAR, M17, YSF, NXDN ve P25 reflektörünün kendi panosu (adresi DVRef listesinden, uygulamanın içinde) | Kişisel veri yok; Canlı ekranında izlediğiniz TG numaraları | Sunucu listeleri ve Canlı ekranı |
| `github.com`, `api.github.com`, `raw.githubusercontent.com`, `cdn.jsdelivr.net` | Kişisel veri yok | Güncelleme denetimi ve indirme, ses çözücü eklentisi |
| `md380.org`, `www.dudetronics.com` | Kişisel veri yok | MD-380 firmware'ini indirmek (onayınızla) |

Bu servislerin hiçbiri geliştiriciye ait değildir; her birinin kendi gizlilik
politikası vardır. Bağlandığınız her sunucu, internetin doğası gereği IP adresinizi görür.

### 2.3 Sohbet (Nostr röleleri)

Sohbet açıksa (varsayılan açık) ve çağrı işaretiniz girilmişse uygulama, çalıştığı
sürece herkese açık Nostr rölelerine bağlanır: `nostr.data.haus`, `relay.primal.net`,
`nostr.oxtr.dev`, `nostr.sathoarder.com`. Merkezi bir sunucu yoktur; rölelerin hiçbiri
geliştiriciye ait değildir.

- **Kimlik:** cihaza özel bir anahtar çifti üretilir; her olay bu anahtarla imzalanır.
  Gizli anahtar cihazdan çıkmaz.
- **Varlık:** 5 dakikada bir "çevrimiçiyim" olayı: çağrı işaretiniz ve açık anahtarınız.
  Röleler bu olayı saklamaz.
- **Oda mesajları:** çağrı işaretiniz, açık anahtarınız ve mesaj metni. Röleler bunları
  **kalıcı ve herkese açık** saklar. "Geçmişi temizle" yalnız cihazınızdaki kopyayı siler.
- **Özel mesajlar:** içerik şifrelidir, yalnız alıcı çözer. Gönderenin ve alıcının açık
  anahtarı ve gönderenin çağrı işareti şifresiz görünür.
- **Çağrı işareti bağı (5.13.7'den beri):** bir çağrı işaretini cihazınızda ilk kullanan
  anahtar o ada bağlanır; aynı adı başka anahtar kullanırsa adın yanında "?" görünür. Bu
  bağlar yalnız cihazınızda tutulur, hiçbir yere gönderilmez.

Sohbeti Ayarlar'dan kapatabilirsiniz; kapalıyken rölelere bağlanılmaz.

### 2.4 Geliştiriciye giden (yalnız onayınızla)

İkisi de `api.web3forms.com` üzerinden geliştiricinin e-posta adresine tek bir ileti
olarak gider. Web3Forms geliştiriciye ait değildir.

- **Cihaz raporu:** Konuşma ekranında bir kez sorulur. "Hayır" derseniz bir daha
  sorulmaz; içerik değişince bir kez daha sorulur. Telsiz Ayarları'ndaki düğmeyle de
  gönderilebilir. Giden: çağrı işareti, DMR ID, ağlardaki cihaz kimlikleri ve bağlantı
  durumları, marka/model ve yazılım sürümü, ekran, bellek, dil, arka plan/izin/ses
  ayarları, LED ve tuş bilgisi, üreticinin sistem uygulamaları, son 5 çağrının ölçümleri
  (konuşan ve TG yazılmaz), bağlantı günlüğünün son 8 hata satırı (başka istasyonların
  çağrı işareti ya da sunucu adresi geçebilir), son çökmenin ilk 12 satırı. Gitmeyen:
  konum, rehber, ses kayıtları, parolalar, yüklediğiniz uygulamalar.
- **Kopya bildirimi:** Uygulamanın imzası resmî imza değilse (APK değiştirilip yeniden
  paketlenmişse) bir kez uyarı çıkar. İzin verirseniz giden: çağrı işareti, sürüm,
  paket adı, kopyanın imza özeti, uygulamayı kuran uygulama, cihaz modeli ve Android
  sürümü.

---

## 3. Telsiz içi web paneli

Uygulama, ayarları bilgisayardan/telefondan girebilmeniz için telsizde küçük bir web
sunucusu açabilir (8080 portu).

- Sunucu **yalnızca sizin Wi-Fi ağınızda** çalışır; internete açılmaz. Web paneli
  ekranı açıkken çalışır; ayardan sürekli açık tutulabilir.
- Her açılışta **altı haneli yeni bir PIN** üretilir ve telsizin ekranında gösterilir.
  PIN'i bilmeyen giremez. 10 hatalı denemeden sonra sunucu kendini kapatır.
- Bağlantı düz HTTP'dir (sertifika gerektirmemesi için). Yedek sayfası, isterseniz
  parolaları da içerir. Bu yüzden paneli **yalnızca güvendiğiniz bir ağda** açık tutun:
  aynı Wi-Fi'daki biri trafiği dinleyebilir ya da PIN'i bilirse ayarlarınızı görebilir.

---

## 4. İzinler ve niçin istendiği

| İzin | Niçin |
|---|---|
| Mikrofon (`RECORD_AUDIO`) | Konuşmanız (PTT) için. Ses yalnızca siz PTT'ye bastığınızda alınır ve yalnızca seçtiğiniz telsiz ağına gider; ses kaydını açmadıysanız kaydedilmez. |
| Konum (`ACCESS_FINE/COARSE_LOCATION`) | APRS konum bildirimi, BrandMeister cihaz kaydı, yer adı, hava durumu ve acil durum konumu için. İsteğe bağlıdır. |
| İnternet, ağ durumu ve ağ değiştirme | Telsiz ağlarına bağlanmak ve bağlantıyı Wi-Fi'ye sabitlemek için. |
| Ön plan servisi (mikrofon, medya), uyanık kalma, pil optimizasyonundan muafiyet | Ekran kapalıyken de bağlantının ve sesin sürmesi için. |
| Bildirimler, tam ekran bildirim | Bağlantı durumu, gelen çağrıda ekranı açmak ve acil durum geri sayımı için. |
| Açılışta başlat | "Telsiz açılınca başlat" ayarını açtıysanız. |
| Uygulama yükleme | Uygulama içi güncelleme için (indirilen APK'nın özeti ve imzası denetlenir). |
| Titreşim, ses ayarları | Uyarı ve ses seviyesi için. |

---

## 5. Çocuklar

Uygulama amatör telsiz lisansı sahiplerine yöneliktir ve çocuklara yönelik değildir.
Çocuklardan bilerek veri toplanmaz.

## 6. Veri saklama ve silme

Uygulama sizin verinizi bir sunucuda tutmaz; silinecek bir hesap yoktur. Cihazdaki her
şeyi silmek için uygulamayı kaldırmanız ya da Android ayarlarından uygulama verisini
temizlemeniz yeterlidir.

Amatör telsiz ağlarına (BrandMeister, ADN, FreeDMR, TGIF, APRS-IS, EchoLink vb.) gitmiş
yayınlarınız ve BrandMeister cihaz kaydınız o ağların kayıtlarındadır; silmek için ilgili
ağa başvurmanız gerekir. Sohbet rölelerindeki oda mesajlarını uygulama silemez. Onayınızla
gönderilen cihaz raporu ve kopya bildirimi geliştiricinin e-postasında durur; silinmesini
iletişim adresinden isteyebilirsiniz.

## 7. Değişiklikler

Bu politika değişirse bu dosya güncellenir ve üstteki tarih değişir.

## 8. İletişim

Soru veya talepleriniz için: **haliyucel@gmail.com**

---
---

# DMR Cepte — Privacy Policy (English)

**Last updated:** 7 November 2026 (version 5.14.1)
**Developer:** TA6HY — Hasan Ali YÜCEL · haliyucel@gmail.com
**License:** GNU GPL v3

## Summary

DMR Cepte is an **amateur radio** application. There are no ads, no analytics and no
tracking services. **Nothing is sent to the developer automatically**; an e-mail reaches
the developer only in two cases and **only with your consent**: the device report and the
unofficial copy notice (see "Sent to the developer"). The app contacts amateur radio
network servers, chat relays and a few public services, each listed below.

## Stored on your device only

Your callsign, DMR ID and NXDN ID; hotspot IDs and passwords for BrandMeister, ADN,
FreeDMR and TGIF, your BrandMeister API key and TGIF Static TG API token; EchoLink callsign, name and password;
fixed or last known location; call history, APRS messages and DMR SMS; your contacts
list (name, callsign, phone, e-mail, IDs); chat history, the chat key (the private key
never leaves the device and is not included in backups) and callsign–key bindings; voice recordings if you enable
recording (deleted after the number of days you choose); the connection log and
`last_crash.txt`; the vocoder plugin and MD-380 firmware, downloaded with your consent.
Passwords are only used to log in to their own network and are **never sent to the
developer or any third party**. Everything is removed when you uninstall the app.

### Your control over location

Before the location permission is first requested the app explains on a screen where the
location goes; there you can choose not to use location at all. Later, in Radio Settings,
you can turn location off completely, enter a fixed position or turn on sending the exact
location to networks (off by default: about 1 km). This policy can also be read inside
the app (the developer and version entry at the bottom of the menu > Privacy policy).

## Sent to amateur radio networks

- **BrandMeister master:** hotspot ID and password, callsign, DMR ID, location (a GPS
  location is rounded to about 1 km; a position you typed, or any position while "Send exact
  location to networks" is on, is sent as is) and place name, **your voice while you
  transmit**, and the DMR SMS you send. The BrandMeister device record is public.
- **ADN Systems, FreeDMR, TGIF** (if enabled): hotspot ID and password, callsign, DMR ID,
  location (rounded as for BrandMeister), your voice.
- **NXDN, YSF, D-STAR, P25 and M17 reflectors** (if enabled): callsign (and NXDN ID), your voice.
- **EchoLink** directory servers, relays and nodes: callsign, EchoLink password, your name
  and EchoLink info text, your voice.
- **APRS-IS:** callsign, **your location** if position sending is on, and the APRS
  messages you send. For SMS, e-mail or WhatsApp gateway messages the recipient's number
  or address travels with the message.
- **BrandMeister Hoseline** (`hose.brandmeister.network`): only the TG number you listen
  to; no identity is sent and nothing is transmitted to the network. It plays the selected
  TG from BrandMeister's web listening stream while the hotspot slot is busy.
- **Emergency (SOS)**, if enabled in Radio Settings and not cancelled during the 5-second
  countdown: a DMR SMS with your location to the contact you chose and a public APRS
  emergency position. No location is sent while the location switch is off.

> **Amateur radio transmissions are public.** Your callsign, location and voice are
> visible to everyone on these networks and may be logged and retained for years by
> third-party sites (brandmeister.network, Hoseline, aprs.fi and others). This is
> inherent to amateur radio, not a feature of this app.

## Sent to supporting services

`api.brandmeister.network` receives your hotspot ID and API key (if entered), for static
groups and the Live screen. `api.tgif.network` receives your TGIF hotspot ID and TGIF Static TG
API token (if entered), to read your TGIF static talkgroups (once at startup and when the
settings screen opens) and to change them when you ask. `radioid.net` receives the callsign or ID you look up.
`nominatim.openstreetmap.org` receives latitude/longitude (yours or the earthquake list's)
to show a place name; `api.open-meteo.com` receives **your latitude and longitude** for the
weather. `www.seismicportal.eu` receives the bounding box of the selected country.
`www.pistar.uk`, `dmr.qso1.net`, `adn.systems` and ADN servers, `freedmr.dvswitch.org`,
`tgif.network`, `ysflive.com` and the dashboard of the selected D-STAR, M17, YSF, NXDN and P25
reflector (address from the DVRef list built into the app)
receive no personal data (only the TG numbers you watch on the Live screen). `github.com`, `api.github.com`, `raw.githubusercontent.com` and
`cdn.jsdelivr.net` serve updates and the vocoder plugin; `md380.org` and
`www.dudetronics.com` serve the MD-380 firmware. None of these belong to the developer;
every server you connect to sees your IP address.

## Chat (Nostr relays)

If chat is on (the default) and a callsign is set, the app connects to public Nostr relays
while it runs: `nostr.data.haus`, `relay.primal.net`, `nostr.oxtr.dev`,
`nostr.sathoarder.com`. There is no central server and no relay belongs to the developer.
Each device has its own key pair; every event is signed and the private key never leaves
the device. Every 5 minutes a presence event carries your callsign and public key; relays
do not store it. Room messages carry the same fields plus the text and are stored
**permanently and publicly** on the relays; "Clear history" only removes the copy on your
device. Private messages are encrypted for the recipient, but both public keys and the
sender's callsign are visible. Since 5.13.7 the first key seen using a callsign on your
device is bound to that name, and a "?" marks other keys using it; these bindings stay on
your device and are never sent anywhere. Turning chat off stops the relay connections.

## Sent to the developer (only with your consent)

Both go through `api.web3forms.com` as a single e-mail to the developer; Web3Forms does not
belong to the developer.

- **Device report:** asked once on the Talk screen (never again after "No"; asked once more
  if its content changes), or sent with the button in Radio Settings. Sent: callsign, DMR
  ID, device IDs and connection states on each network, brand/model and software version,
  screen, memory, language, background/permission/audio settings, LED and key info,
  manufacturer system apps, measurements of the last 5 calls (without who spoke or the TG),
  the last 8 error lines of the connection log (may include other stations' callsigns or
  server addresses) and the first 12 lines of the last crash. Not sent: location, contacts,
  voice recordings, passwords, apps you installed.
- **Copy notice:** if the app is not signed with the official signature (the APK was
  modified and repackaged), you are warned once. With your consent it sends: callsign,
  version, package name, the copy's signature hash, the installing app, device model and
  Android version.

## On-radio web panel

The app can run a small web server on the radio (port 8080) so you can enter settings from
a computer. It is reachable **only on your own Wi-Fi**, runs while the web panel screen is
open (or always, if you enable that), is protected by a **six-digit PIN regenerated at
every start and shown on the radio screen**, and shuts itself down after 10 failed
attempts. The connection is plain HTTP and the backup page can include passwords if you
choose, so only keep the panel open on a network you trust.

## Permissions

Microphone — only while you press PTT, sent only to the radio network you selected,
recorded only if you enable voice recording. Location — for APRS position, the
BrandMeister device record, place name, weather and the emergency position; optional.
Internet, network state and network change — to connect to radio networks and keep the
connection on Wi-Fi. Foreground service (microphone, media), wake lock and battery
optimization exemption — to keep the connection and audio alive with the screen off.
Notifications and full-screen notifications — connection status, waking the screen for an
incoming call and the emergency countdown. Boot completed — only if you enable "start when
the radio turns on". Install packages — for in-app updates (the downloaded APK's hash and
signature are checked). Vibrate and audio settings — for alerts and volume.

## Children

The app is intended for licensed amateur radio operators and is not directed at children.
No data is knowingly collected from children.

## Retention and deletion

The app keeps no data on any server and there is no account to delete. Uninstalling the
app, or clearing its data in Android settings, removes everything held on the device.
Transmissions already sent to amateur radio networks and your BrandMeister device record
are held by those networks; contact the network to request removal. The app cannot delete
room messages stored on chat relays. Device reports and copy notices sent with your
consent stay in the developer's e-mail; you can ask for their deletion at the contact
address.

## Changes and contact

Changes update this file and the date above. Questions: **haliyucel@gmail.com**
