# DMR Cepte — sürüm geçmişi / release history

## 5.8.9 (79) — 2026-10-25

• LED: HIROYASU HI-B10 gibi LED'i doğrudan sürülebilen telsizlerde kırmızı/yeşil ışık artık yanar. • Telsiz Ayarları → Cihaz raporu gönder: cihaz bilgisi istendiğinde yeniden gönderilebilir.

*English:*

• LED: red/green light now works on radios whose LED can be driven directly, such as HIROYASU HI-B10. • Radio settings → Send device report: device information can be sent again on demand.

## 5.8.8 (78) — 2026-10-25

• Güncelleme denetimi yeni sürümü yayından hemen sonra görür (5 dakikalık önbellek beklenmez). • Sürüm notları seçili uygulama dilinde gösterilir.

*English:*

• Update check sees a new version right after release (no 5-minute cache wait). • Release notes are shown in the selected app language.

## 5.8.7 (77) — 2026-10-25

• Cihaz bilgisi: bir kez sorulur, onaylarsanız cihaz bilgisi geliştiriciye e-postayla gider (konum, rehber, kayıt, parola gitmez). • LED: Zello uyumlu telsizlerde yayın sırası Zello'nunkiyle aynı yapıldı.

*English:*

• Device info: asked once; if you agree, device information is e-mailed to the developer (no location, contacts, recordings or passwords). • LED: broadcast order on Zello-compatible radios now matches Zello.

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

• PTT tuşu uygulamaya gelmeyen Zello destekli POC telsizlerde PTT, telsizin Zello'ya gönderdiği mesajdan da çalışır.

*English:*

• On Zello-capable POC radios whose PTT key does not reach apps, PTT also works from the radio's Zello PTT message.

## 5.8.1 (71) — 2026-10-24

• HIROYASU HI-B10 gibi Zello destekli POC telsizlerinde LED: ses gelirken yeşil, konuşurken kırmızı (Zello'nun kullandığı yöntemle).

*English:*

• LED on Zello-capable POC radios such as HIROYASU HI-B10: green on receive, red on transmit (the same method Zello uses).

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
• Ana menüde ve Son Depremler'de dokunmatik geri (‹): geri tuşu olmayan yerde (BlueStacks) de çıkılır.
• Canlı: TG numarasını yazıp statik yapmadan geçici bağlanma.
• BrandMeister ekranında API token'ı panodan yapıştırma.

*English:*

• Release history: Updates → Release history.
• Touch back (‹) in the main menu and Recent earthquakes, for devices without a back key (BlueStacks).
• Live: type a TG number to join it temporarily, without making it static.
• BrandMeister screen: paste the API token from the clipboard.

## 5.6.6 (62) — 2026-10-24

• Güncellemeler artık ana menüde (Telsiz Ayarları'nın altında); yeni sürüm varsa alt yazıda görünür.
• Android 9 cihazlarda (BlueStacks 5) güncellemenin "imza taşımıyor" hatasıyla kurulmaması düzeltildi.

*English:*

• Updates are now in the main menu (below Radio settings); a new version shows in the subtitle.
• Fixed updates being rejected with a signature error on Android 9 (BlueStacks 5).

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
• BlueStacks gibi ARM olmayan cihazda MD-380 denenmez, eklenti önerilir.

*English:*

• My contacts: name, callsign (DMR IDs from radioid), phone, e-mail; tap for direct call, DMR SMS, APRS message, e-mail and WhatsApp over APRS. Also editable on the web panel.
• In-app updates: at start and manually, from GitHub.
• APRS: delivery tracking with retries for outgoing messages; e-mail (EMAIL-2) and WhatsApp (WTSAPP) shortcuts.
• RadioID download continues in the background with a progress bar and notification; Turkey downloads fast too.
• MD-380 is not tried on non-ARM devices such as BlueStacks; the plugin is suggested.

## 5.5.0 (55) — 2026-10-15

• FreeDMR ve TGIF: ADN gibi ayrı, BrandMeister ile aynı anda çalışan ağlar.
• Canlı: şu an kim konuşuyor (BrandMeister tüm ağ, ek ağlar).
• DMR SMS gönderme (teslim onaylı); Motorola TMS alma; mesajlarda "Gruptan çık".
• Bluetooth PTT düğmesi ve kulaklık mikrofonu; Talker Alias gönderme (isteğe bağlı).
• Web panelinde tüm ağlar tek "Ağlar" sayfasında.
• Ses: tampon ve kayıp dolgusu iyileştirmeleri; Bluetooth'ta ilk hecenin kırpılması düzeltildi.
• Papağan (9990) Bitir'e kadar özel çağrı; cevap çağıran cihaza gelir.
• Statik TG'lere ve TG'ler arasında gezinirken kısa yayın gönderilmiyor.

*English:*

• FreeDMR and TGIF: separate networks running alongside BrandMeister, like ADN.
• Live: who is talking right now (whole BrandMeister network, extra networks).
• Sending DMR SMS (with delivery receipt); Motorola TMS receive; "Leave group" in messages.
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
• Telefonda gerçek AMBE+2 ses (MD-380 firmware'i).
• DMR SMS alma (Gelen Mesajlar) ve "aldım" yanıtı.
• Almanca, İspanyolca, İtalyanca, Fransızca: 6 dil.
• Çağrı gelince kapalı ekran açılır; kilitliyken Konuşma ekranı kilidin üstünde (yalnız görüntü).
• Direkt Çağrı'da birden fazla ID seçimi; gelen özel çağrıya cevap verilememesi düzeltildi.
• Telefonda Konuşma ekranı büyüdü; EchoLink node araması tuşla çalışıyor.

*English:*

• ADN Systems network support.
• Real AMBE+2 audio on phones (MD-380 firmware).
• Receiving DMR SMS (Incoming messages) with a "received" reply.
• German, Spanish, Italian, French: 6 languages.
• The screen wakes on a call; when locked the Talk screen shows above the lock (view only).
• Choosing among several IDs in Direct call; fixed answering an incoming private call.
• Larger Talk screen on phones; EchoLink node search works with keys.
