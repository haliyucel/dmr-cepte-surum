# DMR Cepte — Gizlilik Politikası

**Son güncelleme:** 28 Kasım 2026 (sürüm 5.18.22)
**Geliştirici:** TA6HY — Hasan Ali YÜCEL
**İletişim:** haliyucel@gmail.com
**Lisans:** Ücretsiz kullanım, tüm hakları saklıdır (5.17.1'den itibaren; üçüncü taraf bileşenler kendi lisanslarına tabidir)

---

## Özet

DMR Cepte bir **amatör telsiz** uygulamasıdır. Uygulamada reklam, analitik ya da
izleme servisi **yoktur**. Geliştiriciye **kendiliğinden hiçbir veri gitmez**;
yalnız **sizin onayınızla** üç şey gider: cihaz raporu ve resmî olmayan kopya bildirimi
(e-postayla) ve kullanım bildirimi (geliştiricinin Google E-Tablosuna; §2.4).

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
| EchoLink çağrı işareti, adı ve parolası; girdiyseniz EchoLink proxy adresi ve parolası | EchoLink ağına giriş için |
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
| BrandMeister master sunucusu | DMR ID ve parola doğrulaması (parolanın kendisi gönderilmez), uygulamanın adı ve sürümü, konuştuğunuzda **sesiniz**, gönderdiğiniz DMR SMS'leri. Bağlantı BrandMeister'ın terminal arayüzüyle (Open DMR Terminal Protocol) kurulur; çağrı işareti, konum ve yer adı gönderilmez. Sunucu bu arayüze hiç yanıt vermezse eski hotspot girişine dönülür; o durumda hotspot kimliği, çağrı işareti, konum (GPS konumu yaklaşık 1 km'ye yuvarlanır; elle girdiğiniz ya da "Ağlara tam konum gönder" açıkken tam) ve yer adı da gider | DMR bağlantısı. Hotspot girişindeki cihaz kaydı BrandMeister'da herkese açıktır |
| ADN Systems, FreeDMR, TGIF sunucuları (açtıysanız) | Hotspot kimliği ve parola, çağrı işareti, DMR ID, uygulamanın adı ve sürümü, konum (GPS konumu yaklaşık 1 km'ye yuvarlanır; elle girdiğiniz ya da "Ağlara tam konum gönder" açıkken tam), konuştuğunuzda **sesiniz** | DMR bağlantısı |
| NXDN, YSF, D-STAR, P25 ve M17 reflektörleri (açtıysanız) | Çağrı işareti (NXDN'de NXDN ID), konuştuğunuzda **sesiniz** | Bağlantı |
| EchoLink adresleme sunucuları, relay'ler ve node'lar | Çağrı işareti, EchoLink parolası, adınız ve EchoLink bilgi metniniz, konuştuğunuzda **sesiniz** | EchoLink bağlantısı |
| EchoLink proxy (EchoLink ayarında "Açık proxy" ya da "Belirli proxy" yolunu seçtiyseniz; "Otomatik" yolda yalnız hiçbir relay yanıt vermezse, bir kez açık proxy) | Çağrı işareti ve proxy parolası doğrulaması (parolanın kendisi gönderilmez). EchoLink trafiğinizin tamamı proxy'den geçer: dizin girişi (çağrı işareti, adınız, bilgi metniniz, EchoLink parolası doğrulaması) ve konuştuğunuzda **sesiniz**. Açık proxy'leri gönüllüler işletir | EchoLink bağlantısı (relay'in çalışmadığı ağlarda) |
| echolink.org açık proxy listesi (`proxyFind.jsp`; yalnız açık proxy yolu seçiliyken ya da Otomatik yol açık proxy'ye geçtiğinde) | Kimlik ve konum gönderilmez; sunucu listeyi isteğin IP adresine göre yakından uzağa sıralar | Yakındaki açık proxy'leri bulmak |
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
| `auth.dstargateway.org` | Çağrı işaretiniz (şifre gitmez) | D-STAR REF reflektörüne (DPlus) bağlanırken kimlik doğrulaması (en çok 30 dakikada bir) |
| M17 reflektörleri | (açtıysanız) M17 metniniz ve konumunuz (tam konum kapalıyken ~1 km'ye yuvarlı) | Her M17 yayınınızla birlikte; reflektördeki herkes görür |
| `radioid.net`, `database.radioid.net` | Sorguladığınız çağrı işareti ya da DMR ID | Rehber: kimin konuştuğunu ada çevirmek |
| `nominatim.openstreetmap.org` | **Enlem/boylam** (sizin konumunuz ya da deprem listesindeki yerler) | Yer adını bulmak |
| `api.open-meteo.com` | **Enlem/boylamınız** | Hava durumu |
| `www.seismicportal.eu` | Seçtiğiniz ülkenin sınır kutusu (kişisel konum değil) | Deprem listesi |
| `www.pistar.uk`, `adn.systems` ve ADN sunucuları, `freedmr.dvswitch.org`, `tgif.network`, `ysflive.com`, `live.ircddb.net` ve `live3.ircddb.net` (ircDDB canlı günlüğü), `openquad.net` (QuadNet son duyulanlar), `stream.oe3xor.at` (M17 durum akışı), seçili D-STAR, M17, YSF, NXDN ve P25 reflektörünün ve birkaç yoğun M17 reflektörünün kendi panosu (adresi DVRef listesinden, uygulamanın içinde) | Kişisel veri yok; Canlı ekranında izlediğiniz TG numaraları | Sunucu listeleri ve Canlı ekranı |
| `github.com`, `api.github.com`, `raw.githubusercontent.com`, `cdn.jsdelivr.net` | Kişisel veri yok | Güncelleme denetimi ve indirme, ses çözücü eklentisi, çeviri eklentisi (siz isteyince) |
| `md380.org`, `www.dudetronics.com` | Kişisel veri yok | MD-380 firmware'ini indirmek (onayınızla) |

Bu servislerin hiçbiri geliştiriciye ait değildir; her birinin kendi gizlilik
politikası vardır. Bağlandığınız her sunucu, internetin doğası gereği IP adresinizi görür.

**Sürüm denetimi (5.18.20'den beri):** Uygulama, güncelleme denetimiyle birlikte sürüm deposundaki
imzalı bir denetim dosyasını (`kontrol.json`) okur. Kurulu sürüm artık desteklenmiyorsa ya da ciddi
bir sorun nedeniyle durdurulduysa uygulama telsiz ağlarına bağlanmaz ve güncelleme ister; ayarlar ve
güncelleme çalışmaya devam eder. Aynı dosya tek bir özelliği (ör. canlı altyazı) de kapatabilir.
Lisans ihlali ya da kötüye kullanım durumunda geliştirici belirli çağrı işaretleri ya da DMR kimlikleri
için kullanımı da durdurabilir; bu liste dosyada yalnız özet (hash) olarak durur, karşılaştırma
cihazda yapılır. Bu denetimde cihazdan veri gönderilmez. Aynı dosya kullanım bildiriminin adresini de
taşır (§2.4). 5.18.22'den beri uygulama bu engel listesini (yalnız özetler) geliştiricinin Google Apps Script
adresinden de saatte bir okur; bu okumada da cihazdan veri gönderilmez (Google, her sunucu gibi IP adresini görür).

### 2.3 Sohbet (Nostr röleleri)

Sohbet açıksa (varsayılan açık) ve çağrı işaretiniz girilmişse uygulama, çalıştığı
sürece herkese açık Nostr rölelerine bağlanır: `nostr.data.haus`, `relay.primal.net`,
`purplerelay.com`, `nostr.sathoarder.com`. Merkezi bir sunucu yoktur; rölelerin hiçbiri
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

Cihaz raporu ve kopya bildirimi `api.web3forms.com` üzerinden geliştiricinin e-posta
adresine tek bir ileti olarak gider. Web3Forms geliştiriciye ait değildir.

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
- **Kullanım bildirimi (5.18.21'den beri):** Geliştirici açtıysa Konuşma ekranında bir
  kez sorulur; "Hayır" derseniz hiç gönderilmez ve bir daha sorulmaz. İzin verirseniz
  günde en çok bir kez (çağrı işareti ya da sürüm değişince bir sonraki denetimde)
  geliştiricinin Google E-Tablosuna (Google Apps Script, `script.google.com`) gider:
  çağrı işareti, DMR ID, uygulama sürümü, cihaz modeli, Android sürümü, rastgele bir
  kurulum numarası ve uygulamanın resmî imzalı olup olmadığı. Gitmeyen: konum,
  parolalar, rehber, ses, günlük. Amaç: hangi sürümlerin kullanıldığını görmek
  (zorunlu güncelleme kararları) ve izinsiz kullanımı fark edip durdurabilmek. Telsiz
  Ayarları'ndaki "Kullanım bildirimi gönder" anahtarıyla ya da web panelinden istediğiniz
  an kapatabilirsiniz. Tabloyu yalnız geliştirici görür; Google geliştiriciye ait
  değildir. 12 ay görülmeyen kayıt kendiliğinden silinir; engellenen bir kurulumun
  kaydı engel sürdükçe kalır.

### 2.5 Canlı altyazı ve çeviri eklentisi (isteğe bağlı, 5.18.18)

Canlı altyazı varsayılan olarak kapalıdır. Yalnız Android 13 ve üstü telefonlarda
Telsiz Ayarları'ndan açılır.

- **Konuşma tanıma telefonunuzda yapılır.** Hoparlörden çalan telsiz sesi, telefonun
  kendi cihaz içi konuşma tanıma hizmetine (Android'in sistem hizmeti) verilir. Ses ve
  yazı telefondan çıkmaz, uygulama hiçbir sunucuya göndermez. Mikrofon kullanılmaz.
- **Dil paketleri:** "Konuşma dili paketi indir" ile bir dil istediğinizde paketi
  telefonun sistem hizmeti kendi sunucusundan (Google) indirir.
- **Çeviri ayrı bir uygulamada yapılır.** "DMR Cepte Çeviri" eklentisini kurarsanız,
  yazıya dökülen metin telefonun içinde bu eklentiye verilir ve Google ML Kit ile cihazda
  çevrilir. Metin internete gönderilmez. Eklenti Telsiz Ayarları'ndaki düğmeyle sürüm
  deposundan (GitHub) indirilip kurulabilir; dosyanın özeti ve imzası denetlenir, kurulumu
  Android sizden onaylamanızı ister.
- **Eklentinin Google'a bağlantıları:** eklenti, çeviri dil modellerini ilk kullanımda
  Google sunucularından indirir. ML Kit ayrıca Google'ın Firebase hizmetine bir uygulama
  kurulum kimliği bildirir ve uzaktan ayar sorar. Bu bağlantılarda konuşma metni, çağrı
  işareti ya da konum gitmez; Google cihazın dili ve yazılım sürümü gibi teknik
  bilgileri görebilir.
- Eklenti kurulu değilse bu bağlantılar olmaz, altyazı çevrilmeden gösterilir.
  Altyazıyı kapatınca tanıma da durur. Altyazı metni kaydedilmez; uygulama çalıştığı
  sürece yalnız son birkaç konuşma bellekte tutulur.

---

## 3. Telsiz içi web paneli

Uygulama, ayarları bilgisayardan/telefondan girebilmeniz için telsizde küçük bir web
sunucusu açabilir (8080 portu).

- Sunucu **yalnızca sizin Wi-Fi ağınızda** çalışır; internete açılmaz. Web paneli
  ekranı açıkken çalışır; ayardan sürekli açık tutulabilir.
- Her açılışta **altı haneli yeni bir PIN** üretilir ve telsizin ekranında gösterilir.
  PIN'i bilmeyen giremez. 10 hatalı denemeden sonra sunucu kendini kapatır.
- Bağlantı düz HTTP'dir (sertifika gerektirmemesi için). Yedek dosyası parolaları
  yalnızca isterseniz ve sizin belirlediğiniz yedek parolasıyla şifreli içerir. Bu yüzden paneli **yalnızca güvendiğiniz bir ağda** açık tutun:
  aynı Wi-Fi'daki biri trafiği dinleyebilir ya da PIN'i bilirse ayarlarınızı görebilir.

---

## 4. İzinler ve niçin istendiği

| İzin | Niçin |
|---|---|
| Mikrofon (`RECORD_AUDIO`) | Konuşmanız (PTT) için. Ses yalnızca siz PTT'ye bastığınızda alınır ve yalnızca seçtiğiniz telsiz ağına gider; ses kaydını açmadıysanız kaydedilmez. |
| Konum (`ACCESS_FINE/COARSE_LOCATION`) | APRS konum bildirimi, DMR ağlarındaki cihaz kaydı, yer adı, hava durumu ve acil durum konumu için. İsteğe bağlıdır. |
| İnternet, ağ durumu ve ağ değiştirme | Telsiz ağlarına bağlanmak ve bağlantıyı Wi-Fi'ye sabitlemek için. |
| Ön plan servisi (mikrofon, medya), uyanık kalma, pil optimizasyonundan muafiyet | Ekran kapalıyken de bağlantının ve sesin sürmesi için. |
| Bildirimler, tam ekran bildirim | Bağlantı durumu, gelen çağrıda ekranı açmak ve acil durum geri sayımı için. |
| Açılışta başlat | "Telsiz açılınca başlat" ayarını açtıysanız. |
| Uygulama yükleme | Uygulama içi güncelleme ve (siz isterseniz) çeviri eklentisini kurmak için (indirilen APK'nın özeti ve imzası denetlenir). |
| Titreşim, ses ayarları | Uyarı ve ses seviyesi için. |

---

## 5. Çocuklar

Uygulama amatör telsiz lisansı sahiplerine yöneliktir ve çocuklara yönelik değildir.
Çocuklardan bilerek veri toplanmaz.

## 6. Veri saklama ve silme

Uygulamanın hesabı yoktur; geliştirici yalnız 2.4'teki verileri tutar (aşağıda). Cihazdaki
her şeyi silmek için uygulamayı kaldırmanız ya da Android ayarlarından uygulama verisini
temizlemeniz yeterlidir.

Amatör telsiz ağlarına (BrandMeister, ADN, FreeDMR, TGIF, APRS-IS, EchoLink vb.) gitmiş
yayınlarınız ve BrandMeister cihaz kaydınız o ağların kayıtlarındadır; silmek için ilgili
ağa başvurmanız gerekir. Sohbet rölelerindeki oda mesajlarını uygulama silemez. Onayınızla
gönderilen cihaz raporu ve kopya bildirimi geliştiricinin e-postasında durur. Kullanım
bildirimi kaydı geliştiricinin Google E-Tablosunda durur ve 12 ay görülmeyince kendiliğinden
silinir (engellenen kurulumunki engel sürdükçe kalır). Hepsinin silinmesini iletişim
adresinden isteyebilirsiniz.

## 7. Değişiklikler

Bu politika değişirse bu dosya güncellenir ve üstteki tarih değişir.

## 8. İletişim

Soru veya talepleriniz için: **haliyucel@gmail.com**

## 9. KVKK ve GDPR

- **Veri sorumlusu:** TA6HY — Hasan Ali YÜCEL (iletişim adresi 8. bölümde).
- **Geliştiricinin işlediği veri:** yalnız 2.4'teki veriler (cihaz raporu, kopya bildirimi,
  kullanım bildirimi). Hukuki sebep açık rızanızdır (KVKK md. 5/1; GDPR md. 6/1-a). Amaç:
  uygulamanın cihazınızda düzgün çalışması, hataların giderilmesi, sürüm desteği,
  değiştirilmiş kopyaların ve izinsiz kullanımın fark edilip durdurulması. Rızanızı istediğiniz
  an geri alabilir, daha önce gönderilenlerin silinmesini isteyebilirsiniz.
- **Yurt dışına aktarım:** Cihaz raporu ve kopya bildirimi Web3Forms üzerinden e-posta olarak
  gelir; kullanım bildirimi Google'ın (Google E-Tablolar) sunucularında tutulur. Web3Forms'un,
  e-posta sağlayıcısının ve Google'ın sunucuları yurt dışında olabilir. Bu aktarım da açık
  rızanıza dayanır (KVKK md. 9; GDPR md. 49/1-a).
- **Diğer veriler:** 2.1–2.3'teki veriler sizin isteğinizle doğrudan cihazınızdan ilgili ağa ya
  da servise gider; geliştirici bunları görmez ve saklamaz. O servislerin veri sorumlusu
  kendileridir.
- **Haklarınız:** KVKK md. 11 ve GDPR md. 15–21 kapsamında verinizin işlenip işlenmediğini
  öğrenme, bilgi isteme, düzeltme, silme, itiraz etme ve rızanızı geri alma hakkınız var.
  Talebinizi 8. bölümdeki adrese yazın; en geç 30 gün içinde yanıt verilir. Türkiye'de Kişisel
  Verileri Koruma Kurulu'na, AB'de kendi ülkenizin veri koruma makamına şikâyet edebilirsiniz.

---
---

# DMR Cepte — Privacy Policy (English)

**Last updated:** 28 November 2026 (version 5.18.22)
**Developer:** TA6HY — Hasan Ali YÜCEL · haliyucel@gmail.com
**License:** Free to use, all rights reserved (from version 5.17.1; third-party components keep their own licenses)

## Summary

DMR Cepte is an **amateur radio** application. There are no ads, no analytics and no
tracking services. **Nothing is sent to the developer automatically**; only **with your
consent** three things reach the developer: the device report and the unofficial copy notice
(by e-mail) and the usage report (to the developer's Google spreadsheet; see "Sent to the
developer"). The app contacts amateur radio
network servers, chat relays and a few public services, each listed below.

## Stored on your device only

Your callsign, DMR ID and NXDN ID; hotspot IDs and passwords for BrandMeister, ADN,
FreeDMR and TGIF, your BrandMeister API key and TGIF Static TG API token; EchoLink callsign, name and password
(and the EchoLink proxy address and password, if you enter them);
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

- **BrandMeister master:** DMR ID and a password check (the password itself is not sent),
  the app's name and version, **your voice while you transmit**, and the DMR SMS you send.
  The connection uses BrandMeister's terminal interface (Open DMR Terminal Protocol); callsign,
  location and place name are not sent. If the server never answers on that interface, the app
  falls back to the old hotspot login, which also sends the hotspot ID, callsign, location (a GPS
  location is rounded to about 1 km; a position you typed, or any position while "Send exact
  location to networks" is on, is sent as is) and place name. The device record of a hotspot
  login is public on BrandMeister.
- **ADN Systems, FreeDMR, TGIF** (if enabled): hotspot ID and password, callsign, DMR ID,
  the app's name and version, location (a GPS location is rounded to about 1 km; a typed or exact-location setting is sent
  as is), your voice.
- **NXDN, YSF, D-STAR, P25 and M17 reflectors** (if enabled): callsign (and NXDN ID), your voice.
- **EchoLink** directory servers, relays and nodes: callsign, EchoLink password, your name
  and EchoLink info text, your voice.
- **EchoLink proxy** (if you choose the "Public proxy" or "Specific proxy" path in the
  EchoLink settings, or once on the "Automatic" path when no relay answers): callsign and a proxy password check (the password itself is not sent).
  All your EchoLink traffic passes through the proxy: the directory login (callsign, your name,
  info text, EchoLink password check) and your voice. Public proxies are run by volunteers.
- **echolink.org public proxy list** (`proxyFind.jsp`, only while the public proxy path is
  selected, or when the Automatic path falls back to a public proxy): no identity or location is sent; the server sorts the list by the requester's IP
  address, nearest first.
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
settings screen opens) and to change them when you ask. `auth.dstargateway.org` receives your
callsign (no password) when you connect to a D-STAR REF reflector (DPlus), at most every 30 minutes.
M17 reflectors receive (if you enable them) your M17 text and your location (rounded to ~1 km unless
exact location is on) with every M17 transmission; everyone on the reflector can see them.
`radioid.net` receives the callsign or ID you look up.
`nominatim.openstreetmap.org` receives latitude/longitude (yours or the earthquake list's)
to show a place name; `api.open-meteo.com` receives **your latitude and longitude** for the
weather. `www.seismicportal.eu` receives the bounding box of the selected country.
`www.pistar.uk`, `adn.systems` and ADN servers, `freedmr.dvswitch.org`,
`tgif.network`, `ysflive.com`, `live.ircddb.net` and `live3.ircddb.net` (ircDDB live log),
`openquad.net` (QuadNet last heard), `stream.oe3xor.at` (M17 status feed) and the dashboards of
the selected D-STAR, M17, YSF, NXDN and P25 reflector and of a few busy M17 reflectors (address
from the DVRef list built into the app)
receive no personal data (only the TG numbers you watch on the Live screen). `github.com`, `api.github.com`, `raw.githubusercontent.com` and
`cdn.jsdelivr.net` serve updates, the vocoder plugin and (when you ask) the translation add-on; `md380.org` and
`www.dudetronics.com` serve the MD-380 firmware. None of these belong to the developer;
every server you connect to sees your IP address.

**Version check (since 5.18.20):** together with the update check, the app reads a signed control file
(`kontrol.json`) from the release repository. If the installed version is no longer supported or has
been stopped because of a serious problem, the app does not connect to radio networks and asks you to
update; settings and updating keep working. The same file can also turn off a single feature (e.g. live
subtitles). In case of a licence violation or misuse, the developer can also stop use for specific
callsigns or DMR IDs; this list is stored in the file only as hashes and the comparison is made on the
device. No data is sent from the device for this check. The same file also carries the address of the
usage report (see "Sent to the developer"). Since 5.18.22 the app also reads this block list (hashes only) once an
hour from the developer's Google Apps Script address; no data is sent from the device for this either (Google, like
any server, sees the IP address).

## Chat (Nostr relays)

If chat is on (the default) and a callsign is set, the app connects to public Nostr relays
while it runs: `nostr.data.haus`, `relay.primal.net`, `purplerelay.com`,
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

The device report and the copy notice go through `api.web3forms.com` as a single e-mail to
the developer; Web3Forms does not belong to the developer.

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
- **Usage report (since 5.18.21):** if the developer has turned it on, you are asked once on
  the Talk screen; after "No" nothing is sent and you are not asked again. With your consent,
  at most once a day (and at the next check after your callsign or version changes) it goes
  to the developer's Google spreadsheet (Google Apps Script, `script.google.com`): callsign,
  DMR ID, app version, device model, Android version, a random installation number and
  whether the app has the official signature. Not sent: location, passwords, contacts,
  audio, logs. Purpose: seeing which versions are in use (mandatory update decisions) and
  spotting and stopping unauthorised use. You can turn it off at any time with "Send usage
  report" in Radio Settings or in the web panel. Only the developer sees the spreadsheet;
  Google does not belong to the developer. A record not seen for 12 months is deleted
  automatically; the record of a blocked installation stays while the block lasts.

## Live subtitles and the translation add-on (optional, 5.18.18)

Live subtitles are off by default and can only be turned on in Radio Settings on phones
with Android 13 or later.

- **Speech recognition runs on your phone.** The radio audio playing from the speaker is
  passed to the phone's own on-device speech recognition service (an Android system
  service). Audio and text stay on the phone; the app sends them to no server. The
  microphone is not used.
- **Language packs:** when you request a language with "Download a speech language pack",
  the phone's system service downloads it from its own servers (Google).
- **Translation runs in a separate app.** If you install the "DMR Cepte Translate" add-on,
  the recognised text is handed to it inside the phone and translated on the device with
  Google ML Kit. The text is not sent over the internet. The add-on can be downloaded from the
  release repository (GitHub) with the button in Radio Settings; its hash and signature are
  checked and Android asks you to approve the installation.
- **The add-on's connections to Google:** on first use the add-on downloads translation
  language models from Google servers. ML Kit also registers an app installation ID with
  Google's Firebase service and asks for remote configuration. No speech text, callsign or
  location is sent in these connections; Google may see technical details such as the
  device language and software version.
- Without the add-on these connections do not happen and subtitles are shown untranslated.
  Turning subtitles off stops recognition. Subtitle text is not saved; only the last few
  transmissions are kept in memory while the app runs.

## On-radio web panel

The app can run a small web server on the radio (port 8080) so you can enter settings from
a computer. It is reachable **only on your own Wi-Fi**, runs while the web panel screen is
open (or always, if you enable that), is protected by a **six-digit PIN regenerated at
every start and shown on the radio screen**, and shuts itself down after 10 failed
attempts. The connection is plain HTTP and the backup file includes passwords only if you
choose, encrypted with a backup password you set, so only keep the panel open on a network you trust.

## Permissions

Microphone — only while you press PTT, sent only to the radio network you selected,
recorded only if you enable voice recording. Location — for APRS position, the device
record on DMR networks, place name, weather and the emergency position; optional.
Internet, network state and network change — to connect to radio networks and keep the
connection on Wi-Fi. Foreground service (microphone, media), wake lock and battery
optimization exemption — to keep the connection and audio alive with the screen off.
Notifications and full-screen notifications — connection status, waking the screen for an
incoming call and the emergency countdown. Boot completed — only if you enable "start when
the radio turns on". Install packages — for in-app updates and, if you ask, installing the translation add-on (the
downloaded APK's hash and signature are checked). Vibrate and audio settings — for alerts and volume.

## Children

The app is intended for licensed amateur radio operators and is not directed at children.
No data is knowingly collected from children.

## Retention and deletion

There is no account; the developer keeps only the data described in "Sent to the developer"
(below). Uninstalling the app, or clearing its data in Android settings, removes everything
held on the device.
Transmissions already sent to amateur radio networks and your BrandMeister device record
are held by those networks; contact the network to request removal. The app cannot delete
room messages stored on chat relays. Device reports and copy notices sent with your
consent stay in the developer's e-mail. The usage report record stays in the developer's
Google spreadsheet and is deleted automatically after 12 months without being seen (a
blocked installation's record stays while the block lasts). You can ask for the deletion
of any of them at the contact address.

## Legal basis and your rights (KVKK / GDPR)

- **Data controller:** TA6HY — Hasan Ali YÜCEL (contact below).
- **Data the developer processes:** only the data sent with your consent (device report, copy
  notice, usage report). Legal basis: your explicit consent (KVKK art. 5(1); GDPR art. 6(1)(a)).
  Purpose: making the app work on your device, fixing bugs, version support, and spotting and
  stopping modified copies and unauthorised use. You can withdraw consent at any time and ask
  for earlier data to be deleted.
- **Transfer abroad:** the device report and the copy notice reach the developer by e-mail
  through Web3Forms; the usage report is stored on Google's (Google Sheets) servers. The servers
  of Web3Forms, of the e-mail provider and of Google may be outside Türkiye and the EU. This
  transfer also rests on your explicit consent (KVKK art. 9; GDPR art. 49(1)(a)).
- **Other data:** everything else goes directly from your device to the network or service you
  use; the developer does not see or store it. Those services are the controllers of their own
  data.
- **Your rights:** under KVKK art. 11 and GDPR arts. 15–21 you can learn whether your data is
  processed, request information, rectification or erasure, object, and withdraw consent. Write
  to the contact address; you will get an answer within 30 days. You can complain to Türkiye's
  Personal Data Protection Authority or to your EU data protection authority.

## Changes and contact

Changes update this file and the date above. Questions: **haliyucel@gmail.com**
