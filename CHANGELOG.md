# DMR Cepte — sürüm geçmişi / release history

## 5.12.5 (105) — 2026-10-31

NXDN'e bağlıyken arka planda saniyede onlarca paketin gidip geldiği bir hata giderildi; bu trafik mobil veri ve pil harcıyordu. Wi-Fi henüz hazır değilken açılan NXDN, YSF, D-STAR, P25 ve EchoLink bağlantıları Wi-Fi gelince ona geçiyor; böylece cihaz Wi-Fi ile mobil veri arasında gidip gelse de bu bağlantılar Wi-Fi'de kalıyor. Canlı ekranında ADN verisi yedek sunucudan geliyorsa kaynağı yazıyor.

*English:*

Fixed a bug where an NXDN connection kept dozens of packets per second flowing in the background, wasting mobile data and battery. NXDN, YSF, D-STAR, P25 and EchoLink connections opened before Wi-Fi was ready now move to Wi-Fi once it is available, so they stay on Wi-Fi even when the device switches between Wi-Fi and mobile data. The Live screen shows the source when ADN data comes from a backup server.

## 5.12.4 (104) — 2026-10-30

BrandMeister ayarları (eski adıyla Sunucu Ayarları) artık ana menüde diğer ağların yanında, "BrandMeister" adıyla duruyor. Sohbet ekranına "Geçmişi temizle" düğmesi eklendi; geçmiş yalnız o cihazdan silinir, başkalarının cihazlarındaki mesajlar yerinde kalır. En uzun konuşma süresi Telsiz Ayarları'ndan seçilebiliyor (1, 2, 3, 5 ya da 10 dakika; varsayılan 2 dakika); süre dolup yayın kesilince nedeni ekranda yazıyor. BrandMeister'a bağlanırken konum ve yer adı bilgileri sunucunun beklediği biçimde gönderiliyor; sunucu bağlantıyı yine reddederse uygulama nötr konumla yeniden deniyor.

*English:*

BrandMeister settings (formerly Server Settings) now appear in the main menu next to the other networks, under the name "BrandMeister". The chat screen has a new "Clear history" button; it deletes the history only on that device, and messages on other people's devices stay. The maximum transmission time can be chosen in Radio Settings (1, 2, 3, 5 or 10 minutes; default 2 minutes), and when a transmission is stopped at the limit the reason is shown on screen. When connecting to BrandMeister, location and place-name fields are sent in the format the server expects; if the server still rejects the connection, the app retries with a neutral location.

## 5.12.3 (103) — 2026-10-29

Sohbet sunucularından biri boşta bekleyen bağlantıları 30 saniyede kestiği için değiştirildi; sohbet artık dört sunucuya kopmadan bağlı kalıyor. Uygulama değiştirilmiş (resmi olmayan) bir kopyada çalıştığını fark ederse kullanıcıyı bir kez uyarıyor ve izin verilirse geliştiriciye bildiriyor. Web panelindeki ayar yedeği artık parolaları ve BrandMeister anahtarını içermiyor; istenirse kutu işaretlenerek dosyaya eklenebiliyor, parolasız yedek geri yüklenince cihazdaki parolalar korunuyor. Arka plan PTT için Android 13 ve sonrasında gereken "kısıtlanmış ayarlar" izni ekranda açıklanıyor. Yalnız 64 bit çalışan telefonlarda yerleşik dijital ses çözücünün neden kullanılamadığı yazıyor; ses eklentiyle çalışıyor.

*English:*

One of the chat servers dropped idle connections after 30 seconds and was replaced; chat now stays connected to all four servers. If the app detects that it is running as a modified (unofficial) copy, it warns the user once and, with permission, reports it to the developer. The settings backup in the web panel no longer includes passwords or the BrandMeister token; they can be added to the file by ticking a box, and restoring a backup without passwords keeps the passwords on the device. The "restricted settings" permission needed for background PTT on Android 13 and later is explained on screen. On phones that can only run 64-bit code, the app explains why the built-in digital voice decoder cannot be used; audio works with the plug-in.

## 5.12.2 (102) — 2026-10-29

Sohbet daha sağlam: yeni cihazların mesajlarını saklamayan iki sohbet sunucusu, mesajları sakladığı doğrulanan iki sunucuyla değiştirildi. Artık mesajlar ve geçmiş dört sunucunun dördünde de tutuluyor; biri kapansa da sohbet ve geçmiş sürüyor.

*English:*

More reliable chat: two chat servers that did not keep messages from new devices were replaced with two servers verified to keep them. Messages and history are now kept on all four servers, so chat and history continue even if one goes down.

## 5.12.1 (101) — 2026-10-29

İçerik 5.12.0 ile aynı: yeni ücretsiz ve merkeziyetsiz sohbet (Nostr), internetsiz Wi-Fi'de mobil veriyle devam ve diğer düzeltmeler (ayrıntı: Sürüm geçmişi → 5.12.0). Sürüm numarası, 5.12.0'ın ön sürümünü kurmuş cihazların da güncellemeyi alabilmesi için yükseltildi.

*English:*

Same content as 5.12.0: the new free, decentralized chat (Nostr), keeping working over mobile data on a Wi-Fi network without internet, and other fixes (details: Release history → 5.12.0). The version number was raised so that devices that installed a 5.12.0 pre-release also receive the update.

## 5.12.0 (100) — 2026-10-29

Sohbet yenilendi: eski sohbet sunucusu yerine ücretsiz ve merkeziyetsiz Nostr ağı kullanılıyor. Mesajlar dört ayrı sunucuya birden gidiyor, biri kapansa da sohbet sürüyor. Geçmiş cihazda saklanıyor; uygulama açılınca kaçırılan mesajlar (en çok 7 gün) tamamlanıyor. Eski sürümü kullananlar yeni sohbeti görmez, herkesin güncellemesi gerekir. İnternetsiz bir Wi-Fi'ye bağlıyken uygulama artık mobil veriyle çalışmayı sürdürüyor. Web panelinden yedek geri yükledikten sonra Telsiz Ayarları'nın bazı durumlarda kapanması düzeltildi. EchoLink'te bir node'dan hemen başka birine geçince "Bağlanıyor"da takılma giderildi; Canlı'dan seçim yapınca bağlantı beklemeden kuruluyor. Listede olmayan bir BrandMeister TG'sini dinlerken ağa giden kısa yayın 2 dakikada bir yerine 10 dakikada bir yapılıyor. Hiçbir TG seçili değilken BrandMeister TG'lerinin sesi artık çalmıyor. YSF, D-STAR ve P25'te bağlantı koptuğunda roger beep çalmıyor.

*English:*

Chat renewed: instead of the old chat server it now uses the free, decentralized Nostr network. Messages go to four separate servers at once, so chat keeps working if one goes down. History is kept on the device, and messages missed while the app was closed (up to 7 days) are fetched when it opens. Users on older versions will not see the new chat, so everyone needs to update. On a Wi-Fi network without internet the app now keeps working over mobile data. Fixed Radio Settings closing in some cases after restoring a backup from the web panel. EchoLink no longer gets stuck on "Connecting" when switching quickly from one node to another; picking a row in Live TG Traffic connects right away. While listening to a BrandMeister talkgroup that is not in your list, the short transmission sent to the network now happens every 10 minutes instead of every 2. When no talkgroup is selected, BrandMeister talkgroups no longer play. Roger beep no longer plays when a YSF, D-STAR or P25 connection drops.

## 5.11.2 (99) — 2026-10-28

Ağlar artık sürekli bağlı: EchoLink, NXDN, YSF, D-STAR ve P25 bağlantıları Konuşma ekranından bağımsız olarak arka planda kurulur ve koparsa kendiliğinden geri gelir; ekran kapalıyken de ses çalar. ADN ve FreeDMR'de listede olmayan bir TG'ye geçmek artık bağlantıyı yeniden kurmuyor, oturum açıkken TG eklenip çıkarılıyor. Kopmuş bağlantının 'bağlı' görünmesi düzeltildi. Roger beep, dinlemediğiniz bir yayının sonunda artık çalmıyor. Canlı TG Yayınları'nda YSF için ABD reflector'larındaki canlı trafik ve EchoLink konferans/link node'ları görünür; bir satır seçilince o reflector'a ya da node'a geçilir.

*English:*

Networks now stay connected: EchoLink, NXDN, YSF, D-STAR and P25 connect in the background independently of the Talk screen and come back by themselves if dropped; audio plays with the screen closed. On ADN and FreeDMR, switching to a talkgroup that is not in your list no longer reconnects; talkgroups are added and removed while the session stays open. A dropped connection no longer shows as connected. Roger beep no longer plays at the end of a transmission you were not listening to. Live TG Traffic shows live traffic on US YSF reflectors and EchoLink conference/link nodes; picking a row switches to that reflector or node.

## 5.11.1 (98) — 2026-10-28

Düzeltme: Roger beep açıkken bip, konuşma sürerken araya girebiliyordu (arka planda dinlenen başka bir ağın yayını bitince ya da başka bir yayın araya girince). Artık yalnız duyduğunuz konuşma gerçekten bittiğinde, sesin hemen arkasından çalar.

*English:*

Fix: with Roger beep on, the beep could cut into a call in progress (when a transmission ended on another network listened in the background, or another stream interrupted). It now plays only when the call you hear has really ended, right behind the audio.

## 5.11.0 (97) — 2026-10-27

D-STAR ve P25 reflector desteği: Ana menü → D-STAR (reflector + modül) ve P25'ten seçin; Konuşma ekranında YSF'den sonra kendi yuvaları açılır (dinleme ve PTT). Seçilmedikçe kapalıdır. Bu iki ağın sesi için ses çözücü eklentisi gerekir; yoksa durum satırı bildirir. Tüm ağlarda (YSF, NXDN, D-STAR, P25, EchoLink) çağrılar Çağrı Geçmişi'ne çağrı işaretiyle yazılır ve ses kaydı alınır (gelen ve giden). Roger beep artık karşı taraf bırakır bırakmaz, sesin hemen arkasından çalar. Canlı TG Yayınları'nda D-STAR, seçili reflector'un panosundan tüm modülleri gösterir; satır seçilince o modüle geçilir. NXDN'de PTT başlangıç/bitiş paketlerinin gitmemesi düzeltildi.

*English:*

D-STAR and P25 reflector support: pick them in Main menu → D-STAR (reflector + module) and P25; their own slots appear on the Talk screen after YSF (listen and PTT). They stay off until chosen. Audio on these two networks needs the voice decoder add-on; the status line tells you if it is missing. On every network (YSF, NXDN, D-STAR, P25, EchoLink) calls are written to Call History with the callsign and recorded (incoming and outgoing). Roger beep now plays right after the other station releases, directly behind the audio. In Live TG Traffic, D-STAR shows all modules from the selected reflector's dashboard; picking a row switches to that module. Fixed NXDN PTT start/end packets not being sent.

## 5.10.0 (95) — 2026-10-26

YSF reflector desteği: Ana menü → YSF'den bir reflector seçin; Konuşma ekranında NXDN'den sonra YSF yuvası açılır (dinleme ve PTT). Reflector seçilmedikçe YSF kapalıdır. Canlı TG Yayınları'nda YSF'de duyulanlar görünür; Telsiz Ayarları'nda ve web panelinde YSF ses kazancı ve otomatik seviye ayarı var. Liste boş aramada önce kendi ülkenizin reflector'larını gösterir.

*English:*

YSF reflector support: pick a reflector in Main menu → YSF; a YSF slot appears on the Talk screen after NXDN (listen and PTT). YSF stays off until a reflector is chosen. Live TG Traffic shows what is heard on YSF; Radio Settings and the web panel have YSF gain and automatic level. An empty search lists your own country's reflectors first.

## 5.9.13 (94) — 2026-10-26

Ses çözücü eklentisi için DMR Cepte'nin kendi indirme adresi eklendi (ilk sırada); ulaşılamazsa eski adres kullanılıyor. Elle kurulumda dosya artık uygulamanın kendi klasöründe aranıyor (Android/data/com.dmrcepte.app/files); önceden depolama izni olmadığı için kurulamıyordu. Ses Çözücü ekranı ve bağlantı günlüğü hangi eklentinin çalıştığını gösteriyor.

*English:*

Added DMR Cepte's own download address for the vocoder plugin (tried first); if it is unreachable, the previous address is used. Manual install now looks in the app's own folder (Android/data/com.dmrcepte.app/files); before, it failed for lack of storage permission. The Vocoder screen and the connection log show which plugin is running.

## 5.9.12 (93) — 2026-10-26

• Canlı TG Yayınları (ADN): seçili sunucunun canlı listesi önce şifreli, olmazsa şifresiz bağlantıyla alınır; Bulgaristan gibi sunucularda liste artık kendi sunucusundan gelir. İkisi de olmazsa yanıt veren başka bir ADN sunucusu kullanılır.

*English:*

• Live TG Traffic (ADN): the selected server's live list is fetched over an encrypted connection first, then unencrypted; on servers like Bulgaria the list now comes from that server itself. If neither works, another ADN server that answers is used.

## 5.9.11 (92) — 2026-10-26

• Canlı TG Yayınları (ADN): seçili sunucunun canlı izleme sayfası yoksa liste artık boş kalmaz; yanıt veren başka bir ADN sunucusundan gösterilir.

*English:*

• Live TG Traffic (ADN): if the selected server has no live monitor, the list no longer stays empty; it is shown from another ADN server that answers.

## 5.9.10 (91) — 2026-10-26

• Sohbet: gönderilemeyen mesaj artık ekranda "Mesaj gitmedi" diye görünür. • SOS: geri sayım biterken yayın sürüyorsa yayın ışığı sönmez; "Dış PTT" değişince dış SOS komutu hemen dinlenir. • Roger beep: bozuk ses dosyası seçilince uygulama takılmaz.

*English:*

• Chat: a message that could not be sent is now shown as "Message not sent". • SOS: the transmit light stays on if a transmission is running when the countdown ends; the external SOS command follows the "External PTT" switch at once. • Roger beep: choosing a broken sound file no longer hangs.

## 5.9.9 (90) — 2026-10-26

• FreeDMR ve ADN sunucu listeleri kendiliğinden güncel kalır: günde bir yenilenir, seçili sunucunun adresi değişirse yeni adres otomatik yazılır.

*English:*

• FreeDMR and ADN server lists stay up to date by themselves: refreshed daily; if the selected server's address changes, the new address is written automatically.

## 5.9.8 (89) — 2026-10-26

• Güncelleme Google Play Protect tarafından durdurulursa ham hata kodu yerine anlaşılır bir açıklama gösterilir; tuşlu telsizlerde ayrı bir açıklama çıkar.

*English:*

• If Google Play Protect stops an update, a clear explanation is shown instead of the raw error code; keypad radios get their own explanation.

## 5.9.7 (87) — 2026-10-25

• Arka planda PTT: uygulama arkadayken PTT tuşu Konuşma ekranını açıp yayını başlatır (Telsiz Ayarları → Arka planda PTT; Android Erişilebilirlik ayarından açılır). • Daha çok POC telsizin PTT ve SOS tuşu tanınır. • Dış PTT komutları: tuş atama ve otomasyon uygulamaları PTT'ye basabilir (varsayılan kapalı). • SOS tuşu: 5 sn geri sayım ve Vazgeç; seçilen kişiye konumlu DMR SMS ve APRS acil durum konumu (varsayılan kapalı, göndermeden deneme düğmesi var). • Roger beep türü: iki ton, tek bip, çift bip ya da kendi ses dosyanız. • Ses kazancı Telsiz Ayarları'nda: ağ başına otomatik seviye ve hoparlör kazancı, mikrofon kazancı. • Ana menüde "Canlı" artık "Canlı TG Yayınları".

*English:*

• Background PTT: while the app is in the background, the PTT key opens the Talk screen and starts transmitting (Radio settings → Background PTT; turned on in Android Accessibility settings). • PTT and SOS keys of more POC radios are recognised. • External PTT commands: key-mapping and automation apps can press PTT (off by default). • SOS key: 5 s countdown with Cancel; DMR SMS with position to a chosen contact and an APRS emergency position (off by default, with a test button that sends nothing). • Roger beep type: two tones, single beep, double beep or your own sound file. • Sound gain in Radio settings: auto level and speaker gain per network, microphone gain. • Main menu: "Live" is now "Live TG Traffic".

## 5.9.6 (86) — 2026-10-25

• Cihaz raporu daha ayrıntılı (Telsiz Ayarları → Cihaz raporu gönder): cihaz kimlikleri, bağlantı, arka plan ve izin durumu, ses çözücü, son çağrıların ses ölçümleri.

*English:*

• More detailed device report (Radio settings → Send device report): device IDs, connection, background and permission state, codec, audio measurements of recent calls.

## 5.9.5 (85) — 2026-10-25

• İlk kurulum: Sunucu Ayarları kaydedilince ses çözücü kurulu değilse doğrudan Ses Çözücü ekranı açılır.

*English:*

• First setup: after saving Server settings, the Codec screen opens directly if the codec is not installed.

## 5.9.4 (84) — 2026-10-25

• Güncelleme denetimi yeni sürümü yayından hemen sonra görür (GitHub önbelleği atlanır).

*English:*

• Update check sees a new version right after release (GitHub cache is bypassed).

## 5.9.3 (83) — 2026-10-25

• Roger Beep: karşı tarafın yayını bitince de çalar (yalnız bu cihazda). Ses düzeyi medyaya değil bildirim sesine bağlı; medya kısık olsa da duyulur.

*English:*

• Roger beep: also plays when the other side stops (on this device only). Its volume follows notification volume, not media, so it is heard even when media is low.

## 5.9.2 (82) — 2026-10-25

• Roger Beep: Telsiz Ayarları'ndan açılır (varsayılan kapalı). PTT bırakılınca karşı tarafa kısa iki ton gider (DMR, EchoLink, NXDN). • Sohbet: imleç hep yazma kutusunda kalır.

*English:*

• Roger beep: enable in Radio settings (off by default). A short two-tone beep is sent when you release PTT (DMR, EchoLink, NXDN). • Chat: the cursor stays in the message box.

## 5.9.1 (81) — 2026-10-25

• Sohbet: ana menünün en üstünde IRC tarzı ortak oda (DALnet #DMRCepte). Uygulaması olan herkes çağrı işaretiyle girer ve yazar; bilgisayardan bir IRC programıyla da girilebilir. Telsiz Ayarları'ndan kapatılabilir.

*English:*

• Chat: a shared IRC-style room at the top of the main menu (DALnet #DMRCepte). Everyone with the app joins with their callsign; you can also join from a PC with an IRC client. Can be turned off in Radio settings.

## 5.9.0 (80) — 2026-10-25

• Ana menünün en altında Çıkış: arka planda çalışsın (bağlantı açık kalır) ya da tamamen kapat (bağlantı kesilir). • Kapatınca bildirim çubuğunda silinemeyen eski bildirim kalmıyor.

*English:*

• Exit at the bottom of the main menu: keep running in background (stays connected) or close completely (disconnects). • Closing no longer leaves a stale, undismissable notification.

## 5.8.9 (79) — 2026-10-25

• LED: LED'i doğrudan sürülebilen bazı telsizlerde kırmızı/yeşil ışık artık yanar. • Telsiz Ayarları → Cihaz raporu gönder: cihaz bilgisi istendiğinde yeniden gönderilebilir.

*English:*

• LED: red/green light now works on some radios whose LED can be driven directly. • Radio settings → Send device report: device information can be sent again on demand.

## 5.8.8 (78) — 2026-10-25

• Güncelleme denetimi yeni sürümü yayından hemen sonra görür (5 dakikalık önbellek beklenmez). • Sürüm notları seçili uygulama dilinde gösterilir.

*English:*

• Update check sees a new version right after release (no 5-minute cache wait). • Release notes are shown in the selected app language.

## 5.8.7 (77) — 2026-10-25

• Cihaz bilgisi: bir kez sorulur, onaylarsanız cihaz bilgisi geliştiriciye e-postayla gider (konum, rehber, kayıt, parola gitmez). • LED: bazı POC telsizlerde LED komutlarının sırası düzeltildi.

*English:*

• Device info: asked once; if you agree, device information is e-mailed to the developer (no location, contacts, recordings or passwords). • LED: LED command order fixed on some POC radios.

## 5.8.6 (76) — 2026-10-25

• Bilgisayardan Ayarla → Ses seviyesi: hoparlör yükseltmesi artık eksi de seçilebilir (-12, -9, -6, -3 dB); ses fazla gür gelen cihazlar için.

*English:*

• Set Up from PC → Audio level: speaker boost can now be negative (-12, -9, -6, -3 dB) for devices where audio is too loud.

## 5.8.5 (75) — 2026-10-25

• Telsiz Ayarları → Dil: uygulama dili seçilebilir (Sistem dili, Türkçe, English, Deutsch, Español, Français, Italiano).

*English:*

• Radio settings → Language: choose the app language (System, Türkçe, English, Deutsch, Español, Français, Italiano).

## 5.8.4 (74) — 2026-10-25

• Telsiz Ayarları → Konum: kapalıyken APRS konumu, hava durumu ve gerçek BrandMeister konumu durur, ilgili ekranlar uyarı verir.

*English:*

• Radio settings → Location: when off, APRS position, weather and the real BrandMeister position stop; related screens show a warning.

## 5.8.3 (73) — 2026-10-24

• Fikir: Hasan Ali YÜCEL (TA6HY) · kodlama: Claude (Anthropic) — menüde, Lisanslar'da ve web panelinde.

*English:*

• Idea: Hasan Ali YÜCEL (TA6HY) · coded by Claude (Anthropic) — in the menu, Licenses and the web panel.

## 5.8.2 (72) — 2026-10-24

• PTT tuşu uygulamaya gelmeyen bazı POC telsizlerde PTT, telsizin PTT uygulamalarına gönderdiği mesajdan da çalışır.

*English:*

• On some POC radios whose PTT key does not reach apps, PTT also works from the radio's PTT broadcast.

## 5.8.1 (71) — 2026-10-24

• Bazı POC telsizlerde LED: ses gelirken yeşil, konuşurken kırmızı.

*English:*

• LED on some POC radios: green on receive, red on transmit.

## 5.8.0 (70) — 2026-10-24

• Ses kaydı: duyulan çağrılar ve yayınınız kaydedilir, eskiler 7 gün sonra silinir (Telsiz Ayarları'ndan değişir).
• Ana menü → Ses Kayıtları: TG TG kayıtlar, tek tek ya da sırayla çalma. Çağrı Geçmişi'nde de ▶.
• Telsizde liste pencerelerinde OK artık ilk satırda da çalışıyor.

*English:*

• Audio recording: heard calls and your transmissions are recorded, old ones deleted after 7 days (Radio settings).
• Main menu → Recordings: by TG, play one or all in order. Also ▶ in Call History.
• On the radio, OK now works on the first row of list windows.

## 5.7.3 (69) — 2026-10-24

• 1 saniyeden kısa gelen özel çağrı (kısa yayın) artık özel çağrı kipine sokmaz.
• DMR SMS: alıcı çağrı işaretiyle görünür, ör. "TA5TX (2865427)".

*English:*

• An incoming private call shorter than 1 second (kerchunk) no longer switches to private call mode.
• DMR SMS: the recipient shows with callsign, e.g. "TA5TX (2865427)".

## 5.7.2 (68) — 2026-10-24

• Web paneli → Yedek: indirdiğiniz yedek dosyasını seçerek geri yükleme.

*English:*

• Web panel → Backup: restore by choosing the downloaded backup file.

## 5.7.1 (67) — 2026-10-24

• Bilgisayardan Ayarla: adrese ya da PIN'e dokununca panoya kopyalanır.

*English:*

• Set up from computer: tap the address or the PIN to copy it.

## 5.7.0 (66) — 2026-10-24

• Telefonda (Android 12+) güncelleme bundan sonra "Yükle" sormadan kurulur (ilk seferden sonra).
• Güncellemeden sonra uygulama kendiliğinden yeniden açılır, ağlara bağlanır.
• Telsizde kurulum penceresi sığmadığı için Güncellemeler'de uyarı: yan çevirin ya da kablo ile kurun.
• EchoLink ve mikrofon otomatik seviyesi varsayılan açık.

*English:*

• On phones (Android 12+) updates now install without asking (after the first one).
• After an update the app restarts by itself and reconnects.
• On the radio the install window does not fit: Updates shows a note (turn sideways or install by cable).
• EchoLink and microphone auto level are on by default.

## 5.6.9 (65) — 2026-10-24

• Canlı'da elle TG: telefonda kutunun yanında dokunmatik "Geç" düğmesi.

*English:*

• Live manual TG: a touch "Join" button next to the box on phones.

## 5.6.8 (64) — 2026-10-24

• Sürüm geçmişi: Güncellemeler → Sürüm geçmişi.
• Ana menüde ve Son Depremler'de dokunmatik geri (‹): geri tuşu olmayan cihazlarda da çıkılır.
• Canlı: TG numarasını yazıp statik yapmadan geçici bağlanma.
• BrandMeister ekranında API token'ı panodan yapıştırma.

*English:*

• Release history: Updates → Release history.
• Touch back (‹) in the main menu and Recent earthquakes, for devices without a back key.
• Live: type a TG number to join it temporarily, without making it static.
• BrandMeister screen: paste the API token from the clipboard.

## 5.6.6 (62) — 2026-10-24

• Güncellemeler artık ana menüde (Telsiz Ayarları'nın altında); yeni sürüm varsa alt yazıda görünür.
• Android 9 cihazlarda güncellemenin "imza taşımıyor" hatasıyla kurulmaması düzeltildi.

*English:*

• Updates are now in the main menu (below Radio settings); a new version shows in the subtitle.
• Fixed updates being rejected with a signature error on Android 9.

## 5.6.4 (60) — 2026-10-23

• Telsizde Çağrı Geçmişi'ndeki "rehbere ekle" seçenekleri alt alta liste (128 piksele sığmıyordu).
• Kişi düzenlemede kutuya gelince klavye açılmıyor, OK açar; kayıtlı değer ilk harfle silinmiyor.

*English:*

• On the radio the add-to-contacts options are a vertical list (they did not fit 128 pixels).
• Contact editor no longer opens the keyboard on arrival, OK opens it; the saved value is not wiped by the first key.

## 5.6.3 (59) — 2026-10-23

• Çağrı Geçmişi'nden Rehberim'e ekleme: satıra basılı tutun ya da sağ tıklayın (telsizde işaretli satırda OK) → Rehbere ekle / Ekle ve düzenle.

*English:*

• Add to My contacts from Call History: long-press or right-click a row (OK on the radio) → Add / Add and edit.

## 5.6.2 (58) — 2026-10-23

• Rehberim Excel ile dışarı/içeri aktarılıyor: web paneli → Rehberim (.xlsx dışarı; .xlsx ya da .csv içeri, hiçbir kişi silinmez).

*English:*

• My contacts can be exported/imported with Excel: web panel → My contacts (.xlsx out; .xlsx or .csv in, nobody is deleted).

## 5.6.1 (57) — 2026-10-22

• APRS hazır servislerden "WhatsApp (kısa ad)" kaldırıldı; WhatsApp için Rehberim'i kullanın.
• Rehberden e-posta/WhatsApp seçince adres sabit, yalnız mesajınızı yazarsınız.

*English:*

• Removed the "WhatsApp (alias)" APRS shortcut; use My contacts for WhatsApp.
• From contacts the e-mail/WhatsApp address is fixed, you only type your message.

## 5.6.0 (56) — 2026-10-22

• Rehberim: ad, çağrı işareti (DMR ID'leri radioid'den), telefon, e-posta; kişiye dokununca direkt çağrı, DMR SMS, APRS mesaj, APRS ile e-posta ve WhatsApp. Web panelinden de düzenlenir.
• Uygulama içi güncelleme: açılışta ve elle, GitHub'dan.
• APRS: giden mesajda teslim takibi ve yeniden gönderme; e-posta (EMAIL-2) ve WhatsApp (WTSAPP) kısayolları.
• RadioID rehber indirmesi ekrandan çıkınca da sürer; ilerleme çubuğu ve bildirim. Türkiye de hızlı iner.
• ARM olmayan cihazlarda (emülatörler) yerleşik ses çözücü denenmez, eklenti önerilir.

*English:*

• My contacts: name, callsign (DMR IDs from radioid), phone, e-mail; tap for direct call, DMR SMS, APRS message, e-mail and WhatsApp over APRS. Also editable on the web panel.
• In-app updates: at start and manually, from GitHub.
• APRS: delivery tracking with retries for outgoing messages; e-mail (EMAIL-2) and WhatsApp (WTSAPP) shortcuts.
• RadioID download continues in the background with a progress bar and notification; Turkey downloads fast too.
• The built-in codec is not tried on non-ARM devices (emulators); the plugin is suggested.

## 5.5.0 (55) — 2026-10-15

• FreeDMR ve TGIF: ADN gibi ayrı, BrandMeister ile aynı anda çalışan ağlar.
• Canlı: şu an kim konuşuyor (BrandMeister tüm ağ, ek ağlar).
• DMR SMS gönderme (teslim onaylı); TMS biçimli SMS alma; mesajlarda "Gruptan çık".
• Bluetooth PTT düğmesi ve kulaklık mikrofonu; Talker Alias gönderme (isteğe bağlı).
• Web panelinde tüm ağlar tek "Ağlar" sayfasında.
• Ses: tampon ve kayıp dolgusu iyileştirmeleri; Bluetooth'ta ilk hecenin kırpılması düzeltildi.
• Papağan (9990) Bitir'e kadar özel çağrı; cevap çağıran cihaza gelir.
• Statik TG'lere ve TG'ler arasında gezinirken kısa yayın gönderilmiyor.

*English:*

• FreeDMR and TGIF: separate networks running alongside BrandMeister, like ADN.
• Live: who is talking right now (whole BrandMeister network, extra networks).
• Sending DMR SMS (with delivery receipt); TMS-format SMS receive; "Leave group" in messages.
• Bluetooth PTT button and headset microphone; Talker Alias sending (optional).
• All networks on one "Networks" page in the web panel.
• Audio: buffer and loss-fill improvements; fixed the first syllable being clipped over Bluetooth.
• Parrot (9990) is a private call until End; the reply comes to the calling device.
• No kerchunk to static TGs or while stepping through TGs.

## 5.4.0 (54) — 2026-10-05

• ADN Systems ayrı yuva: BrandMeister ile aynı anda çalışır (5.3.0'daki BM/ADN anahtarı kaldırıldı).

*English:*

• ADN Systems as a separate slot running alongside BrandMeister (the 5.3.0 BM/ADN switch was removed).

## 5.3.0 (53) — 2026-10-04

• ADN Systems ağı desteği.
• Telefonda yerleşik dijital ses çözücü.
• DMR SMS alma (Gelen Mesajlar) ve "aldım" yanıtı.
• Almanca, İspanyolca, İtalyanca, Fransızca: 6 dil.
• Çağrı gelince kapalı ekran açılır; kilitliyken Konuşma ekranı kilidin üstünde (yalnız görüntü).
• Direkt Çağrı'da birden fazla ID seçimi; gelen özel çağrıya cevap verilememesi düzeltildi.
• Telefonda Konuşma ekranı büyüdü; EchoLink node araması tuşla çalışıyor.

*English:*

• ADN Systems network support.
• Built-in digital voice codec on phones.
• Receiving DMR SMS (Incoming messages) with a "received" reply.
• German, Spanish, Italian, French: 6 languages.
• The screen wakes on a call; when locked the Talk screen shows above the lock (view only).
• Choosing among several IDs in Direct call; fixed answering an incoming private call.
• Larger Talk screen on phones; EchoLink node search works with keys.
