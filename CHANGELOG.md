# DMR Cepte — sürüm geçmişi / release history

## 5.16.11 (134) — 2026-11-14

Web paneline Telsiz Ayarları'ndaki eksik ayarlar eklendi: en uzun konuşma süresi, roger beep ve türü (kendi ses dosyanızı panelden yükleyebilirsiniz), sohbet, Talker Alias, Bluetooth ve dış PTT, uygulama dili, SOS (tuş, SMS alıcısı, APRS acil konumu) ve APRS çağrı işareti.

*English:*

The web panel now has the settings that were missing from Radio Settings: longest transmission time, roger beep and its type (you can upload your own sound file from the panel), chat, Talker Alias, Bluetooth and external PTT, app language, SOS (key, SMS recipient, APRS emergency position) and APRS callsign.

## 5.16.10 (133) — 2026-11-14

EchoLink: Bazı node'larda görülen "Node yanıt vermedi" uyarısına karşı, bağlanırken node'a kimlik bilgisi saniyede bir gönderiliyor. Relay bir node'a yol bulamazsa ekranda gerçek sebep yazıyor ve bir kez başka bir relay deneniyor. Bağlıyken EchoLink istasyon listesindeki kaydınız 5 dakikada bir tazeleniyor; önceden yaklaşık 10 dakika sonra listeden düşüyordu.

*English:*

EchoLink: to address the "Node did not respond" warning seen on some nodes, the app now sends its identity to the node every second while connecting. If the relay has no route to a node, the screen shows the real reason and another relay is tried once. While connected, your entry in the EchoLink station list is refreshed every 5 minutes; before, it dropped off the list after about 10 minutes.

## 5.16.8 (131) — 2026-11-14

Pil ömrü uzadı: ekran kapalıyken uygulamanın işlemci kullanımı yaklaşık yarıya indi. Listelerdeki kayan yazılar ekran kapalıyken durur, ekran açılınca yeniden kayar; ağ bağlantılarının bakım döngüleri boştayken daha seyrek uyanır. Uygulamanın değiştirilip yeniden paketlenmesine karşı koruma güçlendirildi.

*English:*

Longer battery life: with the screen off, the app's CPU use dropped by about half. Scrolling text in lists stops while the screen is off and resumes when it turns on; network link maintenance wakes up less often when idle. Stronger protection against the app being modified and repackaged.

## 5.16.6 (129) — 2026-11-13

Wi-Fi ile mobil veri arasındaki geçişler düzeltildi: telsiz açılınca ya da Wi-Fi geri gelince bütün bağlantılar (APRS ve sohbet dahil) Wi-Fi'ye geçer, mobil veri gereksiz yere açık kalıp pili tüketmez. Reflector bağlantıları geçiş sırasında kopmaz. Wi-Fi gidince bağlantılar beklemeden mobil veride yeniden kurulur.

*English:*

Wi-Fi / mobile data switching fixed: at startup or when Wi-Fi comes back, all connections (including APRS and chat) move to Wi-Fi, so mobile data no longer stays active and drains the battery. Reflector links no longer drop during the switch. When Wi-Fi is lost, connections are re-established on mobile data right away.

## 5.16.5 (128) — 2026-11-13

Özel çağrı gelince Konuşma ekranında koyu kırmızı bir panel açılıyor: yanıp sönen ÖZEL ÇAĞRI yazısı, büyük harfle çağrı işareti, altında ağ, ID ve ad. Çağrıyı bitirince normal ekrana dönülür. TGIF: parola reddedilirse uygulama 3 denemeden sonra durur ve ayarı değiştirene kadar yeniden denemez (TGIF tekrarlanan hatalı girişleri kısıtlayabiliyor). TGIF ayarlarındaki alanın adı artık 'TGIF hotspot anahtarı': buraya TGIF Self Care'deki 16 karakterlik anahtar yazılır, site parolası değil.

*English:*

On a private call the Talk screen now shows a dark red panel: a blinking PRIVATE CALL label, the callsign in large letters, and the network, ID and name below. Ending the call returns to the normal screen. TGIF: if the password is rejected, the app stops after 3 attempts and does not retry until you change the setting (TGIF may restrict repeated failed logins). The field in TGIF settings is now called 'TGIF hotspot key': enter the 16-character key from TGIF Self Care there, not your website password.

## 5.16.4 (127) — 2026-11-10

Ekran kapalıyken PTT'ye ilk basışta yayın başlıyor (eskiden ilk basış yalnızca ekranı açıyordu). Çağrı gelince ekran 1 sn sonra açılıyor; çağrı başındaki ses takılmasını azaltması için deneniyor.

*English:*

With the screen off, the first PTT press now starts transmitting (before, the first press only woke the screen). On an incoming call the screen now turns on after 1 s; this is being tried to reduce stutter at the start of calls.

## 5.16.3 (126) — 2026-11-10

Çağrı sürerken ekran artık kapanmıyor; kapanma süresi çağrı bitince başlıyor. Uzun çağrılarda ekran kapanırken oluşan ses takılmaları azalır. ('Çağrıda ekranı aç' kapalıysa değişiklik yok.)

*English:*

The screen no longer turns off while a call is playing; the screen timeout starts when the call ends. This reduces audio stutter that happened when the screen turned off during long calls. (No change if 'Wake screen on call' is off.)

## 5.16.2 (125) — 2026-11-08

Mikrofon seviyesi artık her ağ için ayrı ayarlanabiliyor (Telsiz Ayarları > Ses kazancı ve web paneli). M17'de başlangıç −12 dB: M17'de ses karşıya fazla yüksek gidiyordu. D-STAR: bağlanıp hemen kopan reflector giderek daha seyrek deneniyor; bağlantıyı reddeden reflector/modül, ayar değişene kadar yeniden denenmiyor. Web paneli yedeğinde parola işlenirken 'bekleyin' notu gösteriliyor.

*English:*

Microphone level can now be set separately for each network (Radio Settings > Audio gain and the web panel). M17 starts at −12 dB: audio was going out too loud on M17. D-STAR: a reflector that connects and drops right away is retried less and less often; a reflector/module that rejects the connection is not retried until the setting changes. The web panel backup shows a 'please wait' note while the password is processed.

## 5.16.1 (124) — 2026-11-08

Web paneli yedeği: parolalar ve API anahtarları dosyaya artık düz metin girmez. Kutuyu işaretleyip bir yedek parolası girerseniz şifrelenerek eklenir; geri yüklerken aynı parola sorulur. Gizlilik politikası güncellendi.

*English:*

Web panel backup: passwords and API keys are no longer written to the file in plain text. If you tick the box and enter a backup password, they are added encrypted; the same password is asked when restoring. Privacy policy updated.

## 5.16.0 (123) — 2026-11-08

M17: gelen yayınlardaki metin mesajı, konum ve asıl konuşan Konuşma ekranında görünür. M17 ayarlarından kendi metninizi ve isteğe bağlı olarak konumunuzu (yaklaşık 1 km'ye yuvarlanır) gönderebilirsiniz. Gizlilik politikası güncellendi.

*English:*

M17: text messages, location and the original talker from incoming transmissions are shown on the Talk screen. In M17 settings you can send your own text and, optionally, your location (rounded to about 1 km). Privacy policy updated.

## 5.15.3 (122) — 2026-11-08

Kişisel hotspot'tan konuşan bazı istasyonlar röle sanılıp Konuşma ekranında ve Çağrı Geçmişi'nde gösterilmiyordu (sesleri geliyordu). Artık kişi kimlikleri hiç gizlenmez; daha önce yanlış gizlenenler kendiliğinden düzelir.

*English:*

Some stations talking through a personal hotspot were mistaken for repeaters and not shown on the Talk screen or in Call History (their audio still played). Personal IDs are no longer hidden; earlier mistakes fix themselves.

## 5.15.2 (121) — 2026-11-07

D-STAR: DCS reflector'larına da bağlanılabilir (yalnız DCS kullanan sunucular dahil). Canlı'da DCS satırına dokununca bağlanır. Ayar listesinde REF ve DCS kapıları doğru gösterilir.

*English:*

D-STAR: DCS reflectors can now be used too (including DCS-only servers). Tapping a DCS row on the Live screen connects to it. The settings list shows the correct port for REF and DCS.

## 5.15.1 (120) — 2026-11-07

D-STAR: REF reflector'larına bağlanılabilir. Konuşmak için çağrı işaretinin D-STAR kaydında onaylı olması ve terminal eklenmiş olması gerekir; değilse yalnız dinlenir. Canlı'da DCS satırı aynı sunucudaki XRF'e, REF satırı doğrudan bağlanır. Gizlilik politikası güncellendi.

*English:*

D-STAR: REF reflectors can be used. Transmitting requires your callsign to be approved in the D-STAR registration with terminals added; otherwise listen only. On the Live screen a DCS row connects through the XRF on the same server, a REF row connects directly. Privacy policy updated.

## 5.15.0 (119) — 2026-11-07

Canlı TG Yayınları: M17'de seçili reflector'un yanında en yoğun M17 reflector'ları ve anlık bir durum akışı; D-STAR'da ağ genelinde konuşanlar (ircDDB ve QuadNet). Satıra dokununca o reflector'a geçilir (D-STAR'da XRF/XLX); geçilemeyen satırda uyarı çıkar. Gizlilik politikası güncellendi.

*English:*

Live TG Traffic: M17 now also shows the busiest M17 reflectors and a live status feed next to the selected reflector; D-STAR shows network-wide traffic (ircDDB and QuadNet). Tapping a row switches to that reflector (XRF/XLX on D-STAR); rows that can't be selected show a notice. Privacy policy updated.

## 5.14.2 (118) — 2026-11-07

M17: bazı istasyonların yayını kısa parçalar halinde geldiğinde her parça ayrı yayın sayılıyordu: araya roger beep giriyor, ses seviyesi her parçada yeniden ayarlanıyor, geçmişe ve ses kayıtlarına parça başına ayrı satır açılıyordu. Artık aynı istasyonun art arda gelen parçaları tek yayın sayılır.

*English:*

M17: when a station's transmission arrived in short pieces, each piece was treated as a separate transmission: a roger beep was inserted, the audio level was readjusted for every piece, and history and recordings got a separate entry per piece. Consecutive pieces from the same station are now treated as one transmission.

## 5.14.1 (117) — 2026-11-07

TGIF statik TG: TGIF'in statik TG anahtarıyla statik gruplarınızı uygulamadan okuyup yazabilirsiniz (Menü > TGIF; anahtar web panelinden de yapıştırılabilir). TGIF'te statik olan TG'ye katılmak için kısa yayın gönderilmez. Canlı TG Yayınları: M17, YSF, NXDN ve P25'te seçili reflector'un kendi panosu okunur (panosu olanlarda). M17: modül listesi yalnız reflector'un modüllerini gösterir; reflector'da olmayan modül seçiliyse ilk geçerli modüle geçilir. Gizlilik politikası güncellendi.

*English:*

TGIF static talkgroups: read and set your TGIF static TGs from the app with TGIF's static TG token (Menu > TGIF; the token can also be pasted in the web panel). No short transmission is sent to join a TG that is static on TGIF. Live TG Traffic: for M17, YSF, NXDN and P25 the selected reflector's own dashboard is read (where it has one). M17: the module list shows only the reflector's modules; if the selected module doesn't exist there, the first valid one is used. Privacy policy updated.

## 5.14.0 (116) — 2026-11-07

Yeni ağ: M17. Menü > M17'den bir reflector ve modül seçin (Türkiye'nin M17-286'sı dahil); ses çözücü uygulamanın içinde, ayrıca indirme gerekmez. Konuşma ekranında M17 yuvası, Canlı'da M17 sekmesi ve web panelinde M17 ayarları var. Gizlilik: DMR ağlarına giden GPS konumu artık yaklaşık 1 km'ye yuvarlanıyor (tam konum Telsiz Ayarları'ndan açılabilir). Konum izni ilk kez sorulmadan önce neye kullanıldığı anlatılıyor; gizlilik politikası uygulamanın içinden okunabiliyor.

*English:*

New network: M17. Pick a reflector and module under Menu > M17 (including Turkey's M17-286); the audio decoder is built in, nothing extra to download. M17 has its own slot on the Talk screen, a tab on the Live screen and settings in the web panel. Privacy: the GPS location sent to DMR networks is now rounded to about 1 km (exact location can be turned on in Radio Settings). Before the location permission is first requested, the app explains what it is used for; the privacy policy can be read inside the app.

## 5.13.9 (115) — 2026-11-05

Arka planda PTT özelliği kaldırıldı. Bu özellik bir erişilebilirlik servisi kullanıyordu; bazı cihazlarda Android'in güvenlik koruması bu yüzden DMR Cepte'nin kurulumunu "Uygulama, cihazınızı korumak için engellendi" diyerek durduruyordu. Konuşma ekranındaki PTT ve uygulama açıkken PTT tuşu eskisi gibi çalışıyor. Özelliği açmış olanların bir şey yapmasına gerek yok.

*English:*

Background PTT has been removed. It used an accessibility service, and because of that, Android's security protection on some devices blocked installing DMR Cepte with the message "App blocked to protect your device". PTT on the Talk screen and the PTT key while the app is open work as before. If you had turned the feature on, there is nothing you need to do.

## 5.13.8 (114) — 2026-11-02

Cihaz raporunun izin sorusu artık gönderilen her bilgiyi tek tek sayıyor; bu yüzden soru herkese bir kez daha soruluyor. Ses çözücü eklentisi yalnız tanınan dosyalardan kuruluyor: indirilen ya da elle konan dosya bilinen DMR Cepte eklentilerinden biri değilse güvenlik için kurulmuyor. İndirme sabit bir eklenti sürümünden yapılıyor, ilk adres açılmazsa yedeği deneniyor; kurulu eklentiler olduğu gibi çalışmaya devam ediyor. Sohbette bir çağrı işareti, bu cihazda onunla ilk görülen anahtara bağlanıyor. Aynı adı başka bir anahtar kullanırsa adın yanında ? görünüyor (taklit ya da kişinin başka bir cihazı olabilir) ve özel mesajlar bağlı anahtara gidiyor; bağlı anahtar 30 gün görülmezse ad yenisine geçiyor.

*English:*

The device report consent question now lists every piece of information that is sent, so it is asked once more for everyone. The voice decoder plugin is now installed only from recognized files: if a downloaded or manually placed file is not one of the known DMR Cepte plugins, it is not installed, for safety. Downloads come from a fixed plugin version, and a backup address is tried if the first one fails; plugins already installed keep working. In chat, a callsign is now bound to the first key seen with it on this device. If another key uses the same name, a ? appears next to the name (it may be an impersonator or the person's other device), and private messages go to the bound key; if the bound key is not seen for 30 days, the name moves to the new key.

## 5.13.5 (111) — 2026-11-02

Kod incelemesinde bulunan hatalar giderildi. BrandMeister çağrısında LED ekran kapalıyken de yanıyor ve çağrı bitince sönüyor; LED denemesinden sonra da sönüyor. Özel çağrı sürerken PTT artık "önce TG seçin" demiyor. EchoLink'te konuşan istasyonun adı her bağlantı türünde görünüyor, bağlantı kurulamazsa ekranda gerçek sebep yazıyor. Sunucunun adresi değişirse yeniden bağlanma eski adrese takılmıyor. TGIF Canlı akışını açık tutan paket artık gerçekten gidiyor. Çağrı geçmişi, APRS kayıtları ve kişiler, yazma yarıda kesilse ya da aynı anda iki değişiklik olsa da kaybolmuyor. NXDN'de anlık bir ağ hatası istasyonu kalıcı olarak "kayıtlı değil" göstermiyor. Konum kapalıyken APRS konum ekranına dönünce GPS açılmıyor. Deprem listesi yalnız ekranda görünen satırların yer adını soruyor. Cihaz raporu gönderilemezse en çok 6 saatte bir yeniden deneniyor ve izin sorusu kilit ekranının üstünde açılmıyor. Web panelinde hotspot kimliği değişince BrandMeister işlemleri eski cihaza gitmiyor, adres boşsa ses çözücü eklentisi bilinen adreslerden sırayla deneniyor; oturum açmadan gönderilen isteklerin boyutu ve sayısı sınırlandı. Sohbet ayarındaki not, oda mesajlarının herkese açık rölelerde de kaldığını belirtiyor.

*English:*

Fixed the bugs found in a thorough code review. During BrandMeister calls the LED now also lights with the screen off and goes out when the call ends; it also goes out after the LED test. PTT no longer says "select a TG first" during a private call. EchoLink shows the talking station's name on every connection type, and when a connection fails the screen shows the real reason. If a server's address changes, reconnecting no longer sticks to the old address. The packet that keeps the TGIF Live feed open is now actually sent. Call history, APRS records and contacts are no longer lost when a write is interrupted or two changes happen at once. A momentary network error on NXDN no longer marks a station as "not registered" for good. With location off, returning to the APRS location screen no longer turns on GPS. The earthquake list only looks up place names for the rows on screen. If the device report cannot be sent, it is retried at most every 6 hours, and the consent question no longer opens over the lock screen. In the web panel, BrandMeister actions no longer go to the old device after the hotspot ID changes, and with an empty address the decoder plugin is tried from the known addresses in turn; requests sent without logging in are now limited in size and number. The note in chat settings now says room messages also stay on the public relays.

## 5.13.2 (108) — 2026-11-02

#APRSThursday katılım mesajı gönderildikten 1 dakika sonra uygulama HOTG grubundan kendiliğinden çıkıyor. Mesajınız etkinliğe yine düşüyor, ama grubun sonraki mesajları cihaza SMS olarak gelip hattı meşgul etmiyor. Uygulama bu arada kapanırsa çıkış bir sonraki açılışta tamamlanıyor.

*English:*

One minute after the #APRSThursday participation message is sent, the app now leaves the HOTG group automatically. Your message still counts for the event, but later group messages no longer arrive on the device as SMS and occupy the slot. If the app is closed in the meantime, it completes the leave the next time it starts.

## 5.13.1 (107) — 2026-11-02

Seçili BrandMeister TG'sinde konuşmaların kaybolması giderildi. Hotspot tek hatlı olduğu için, abone olunan başka bir TG'deki konuşma ya da size gelen bir SMS hattı tutarken seçili TG'deki yayın cihaza hiç gelmiyor ya da başı kesik geliyordu. Uygulama artık böyle anlarda aynı yayını BrandMeister'ın kendi web dinleme akışından çalıyor. Hotspot yayını verebiliyorsa her zamanki gibi hotspot'tan çalar ve hiçbir yayın iki kez çalmaz. Bu özellik ağa hiçbir şey göndermez; Wi-Fi'de seçili TG'yi sürekli dinler, mobil veride yalnız hat meşgulken (konuşma sırasında saniyede yaklaşık 8 KB).

*English:*

Fixed lost transmissions on the selected BrandMeister talkgroup. Because a hotspot has a single slot, transmissions on the selected talkgroup never reached the device, or arrived with their beginning cut off, while another subscribed talkgroup or an incoming SMS was holding the slot. At such moments the app now plays the same transmission from BrandMeister's own web listening stream. When the hotspot can deliver a transmission, it still plays from the hotspot, and nothing plays twice. This feature sends nothing to the network; on Wi-Fi it follows the selected talkgroup continuously, on mobile data only while the slot is busy (about 8 KB/s while someone is talking).

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
