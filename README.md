# LED Kontrolcüsü | WS2812B LED Controller Desktop App for ESP32

[🇹🇷 Türkçe Dokümantasyon İçin Tıklayın](#türkçe-dokümantasyon) | [🇬🇧 Click here for English Documentation](#english-documentation)

![OS](https://img.shields.io/badge/OS-Windows_10%20|%2011-blue)
![Version](https://img.shields.io/badge/Version-v1.0.0-success)
![Downloads](https://img.shields.io/github/downloads/TunahanD/WS2812B_LED_Controller/total?color=brightgreen)
![License](https://img.shields.io/badge/License-All_Rights_Reserved-red)

**📥 [Uygulamayı İndir (Download Latest Release)](https://github.com/TunahanD/WS2812B_LED_Controller/releases/tag/Versiyon_1)**

Windows üzerinde çalışan bu masaüstü uygulama, ESP32 tabanlı bir WS2812B LED kontrol sistemini kullanıcı dostu bir arayüzle yönetmek için hazırlanmıştır. Bu GitHub deposu, yalnızca son kullanıcı kurulumu ve ürün dokümantasyonu için kullanılmaktadır.

---

## İçindekiler / Table of Contents

- [Türkçe Dokümantasyon](#türkçe-dokümantasyon)
  - [WS2812B LED Kontrolcüsü Nedir?](#ws2812b-led-kontrolcüsü-nedir)
  - [Projenin Genel Amacı ve Hedef Kitlesi](#projenin-genel-amacı-ve-hedef-kitlesi)
  - [Uygulamanın Çözümlediği Temel Problem](#uygulamanın-çözümlediği-temel-problem)
  - [Teknik Özellikler ve Öne Çıkan Yetenekler](#teknik-özellikler-ve-öne-çıkan-yetenekler)
  - [Sistem Gereksinimleri ve Uyumluluk Bilgileri](#sistem-gereksinimleri-ve-uyumluluk-bilgileri)
  - [Kurulum Rehberi](#kurulum-rehberi)
  - [Hızlı Başlangıç Rehberi](#hızlı-başlangıç-rehberi)
  - [Detaylı Kullanım Kılavuzu](#detaylı-kullanım-kılavuzu)
  - [Arayüz Ekranları ve Ekran Görüntüleri](#arayüz-ekranları-ve-ekran-görüntüleri)
  - [Sık Karşılaşılan Sorunlar ve Çözüm Önerileri](#sık-karşılaşılan-sorunlar-ve-çözüm-önerileri)
  - [Sürüm Geçmişi ve Güncelleme Notları](#sürüm-geçmişi-ve-güncelleme-notları)
  - [Lisans Bilgileri](#lisans-bilgileri)
  - [İletişim Bilgileri](#iletişim-bilgileri)
- [English Documentation](#english-documentation)
  - [What Is the WS2812B LED Controller Desktop App?](#what-is-the-ws2812b-led-controller-desktop-app)
  - [Project Purpose and Target Audience](#project-purpose-and-target-audience)
  - [Core Problem Solved by the Application](#core-problem-solved-by-the-application)
  - [Technical Features and Key Capabilities](#technical-features-and-key-capabilities)
  - [System Requirements and Compatibility](#system-requirements-and-compatibility)
  - [Installation Guide](#installation-guide)
  - [Quick Start Guide](#quick-start-guide)
  - [Detailed User Guide](#detailed-user-guide)
  - [Interface Screens and Screenshots](#interface-screens-and-screenshots)
  - [Troubleshooting Guide](#troubleshooting-guide)
  - [Version History and Release Notes](#version-history-and-release-notes)
  - [License Information](#license-information)
  - [Contact Information](#contact-information)

---

## Türkçe Dokümantasyon

### WS2812B LED Kontrolcüsü Nedir?

LED Kontrolcüsü, ESP32 tabanlı bir denetleyici ile çalışan WS2812B adreslenebilir LED şeritleri masaüstünden yönetmek için geliştirilmiş bir Windows uygulamasıdır. Uygulama; tek tek LED seçimi, toplu renk atama, parlaklık ayarı, animasyon yönetimi, profil kaydetme, cihaz keşfi ve ilk kurulum için BLE tabanlı Wi-Fi yapılandırması gibi son kullanıcı odaklı özellikler sunar.

Bu yapı özellikle kaynak kod paylaşmadan, sadece çalışır durumdaki masaüstü uygulamasını dağıtmak isteyen ürünleştirilmiş projeler için uygundur.

### Projenin Genel Amacı ve Hedef Kitlesi

Bu projenin temel amacı, ESP32 ile sürülen WS2812B LED kurulumlarını teknik bilgi gerektirmeden yönetilebilir hale getirmektir.

Hedef kitlemiz:
- Kendi LED donanımını geliştiren maker ve DIY kullanıcıları.
- Masa, oda, vitrin, TV arkası veya dekoratif aydınlatma projeleri hazırlayan kullanıcılar.
- ESP32 tabanlı LED sistemini müşterilerine veya son kullanıcılara daha profesyonel bir arayüzle sunmak isteyen geliştiriciler.
- Animasyon, renk sahnesi ve profil yönetimini tek bir masaüstü uygulamasında toplamak isteyen kullanıcılar.

### Uygulamanın Çözümlediği Temel Problem

Adreslenebilir LED projelerinde en büyük zorluklardan biri, donanımın kurulmuş olsa bile günlük kullanımın teknik detaylara bağımlı kalmasıdır. Pek çok sistemde kullanıcı;
- Wi-Fi yapılandırmasını seri port veya manuel araçlarla yapmak zorunda kalır.
- Cihazın ağdaki IP adresini bulmakta zorlanır.
- Tek tek LED kontrolü ile animasyon kontrolü arasında farklı araçlar kullanır.
- Profil ve sahne kayıtlarını merkezi olarak yönetemez.
- Bağlantı kopmalarında sistemi yeniden başlatmak zorunda kalır.

LED Kontrolcüsü bu problemi şu şekilde çözer:
- BLE üzerinden ilk Wi-Fi kurulumunu doğrudan uygulama içinde tamamlar.
- mDNS ile cihazı ağda otomatik olarak keşfeder.
- Son başarılı IP adresini hatırlayarak hızlı tekrar bağlantı kurar.
- Tek tek LED düzenleme ile animasyon yönetimini aynı arayüzde sunar.
- Profil sistemi ile renk, parlaklık ve şerit yapılandırmasını yerel olarak saklar.
- Heartbeat ve otomatik yeniden bağlanma mantığı ile bağlantı sürekliliğini artırır.

### Teknik Özellikler ve Öne Çıkan Yetenekler

#### Uygulama Özellikleri
- Windows masaüstü arayüzü ile akıcı kullanım deneyimi.
- Yüksek performanslı görsel LED tuvali.
- Tekil LED seçimi ve şerit bazlı toplu seçim imkanı.
- Seçili LED'lere veya tüm şeride hızlı renk uygulama.
- Seçili LED'leri kapatma veya tüm sistemi tek tuşla kapatma.
- Hızlı parlaklık ön ayarları ve hassas parlaklık kaydırıcısı.
- Profil oluşturma, kaydetme, silme ve son profili otomatik yükleme işlevleri.
- Anlık cihaz durumu ve bağlantı göstergesi.
- Otomatik bağlanma ve bağlantıyı manuel kesme seçenekleri.
- BLE üzerinden sorunsuz ilk cihaz kurulumu.

#### Animasyon Özellikleri
- 30 adet yerleşik, özelleştirilebilir animasyon seçeneği.
- Birleşik mod ve bağımsız şerit modu desteği.
- Her şerit için tamamen ayrı animasyon oynatma desteği.
- Oynat, duraklat, devam ettir ve durdur kontrolleri.
- Animasyon hız ayarı ve akış yönü belirleme.
- Animasyonlara özel parlaklık seviyesi seçimi.
- Renk destekleyen animasyonlarda özel renk paleti kullanımı.
- Sekmeler arasında geçiş yapıldığında animasyon durumunu koruyan akıllı akış.

#### Ağ ve Cihaz İletişimi
- Gecikmesiz UDP tabanlı haberleşme protokolü.
- Otomatik cihaz keşfi için entegre mDNS desteği.
- BLE (Bluetooth Low Energy) üzerinden Wi-Fi provisioning.
- Bağlantı kararlılığı için 5 saniyelik heartbeat (kalp atışı) kontrolü.
- Kayıp bağlantı durumunda hızlı yeniden bağlanma denemeleri.
- Uzun süreli ağ kopmalarında arka planda sessiz yeniden arama.
- Telemetri tabanlı bağlantı durumu ve sinyal kalitesi takibi.

#### Donanım ve Uyumlu Cihaz Profili
Mevcut masaüstü uygulaması ve uyumlu firmware yapısı aşağıdaki donanım profiliyle çalışacak şekilde tasarlanmıştır:
- **Denetleyici:** ESP32
- **LED Tipi:** WS2812B
- **Haberleşme Portu:** UDP 4210
- **mDNS Servis Adı:** `_ledcontrol._udp.local`
- **Varsayılan mDNS Host Adı:** `ledcontroller.local`
- **BLE Kurulum Adı:** `LEDController-Setup`
- **Mimari:** Tek veri hattı üzerinden seri bağlı şerit yapısı.
- **Veri Pini:** GPIO 13 (Firmware tarafında)
- **Fiziksel LED Kapasitesi:** Sol 32, Orta 70, Sağ 32.
- **Varsayılan Aktif LED Sayıları:** Sol 30, Orta 30, Sağ 30.

#### Animasyon Listesi
Rainbow Cycle, Breathing, Color Wipe, Meteor Rain, Theater Chase, Fire Effect, Ocean Wave, Sparkle, Color Fade, Strobe, Running Lights, Bouncing Ball, Twinkle, Police Lights, Plasma, Gradient Sweep, Pulse, Snow Sparkle, Heartbeat, Ripple, Lightning, Candy Cane, Aurora Borealis, Waterfall, Ankaragücü Energy, Fireworks, Color Bounce, Lava Lamp, Chase Rainbow, Comet.

### Sistem Gereksinimleri ve Uyumluluk Bilgileri

| Başlık | Gereksinim / Durum |
| --- | --- |
| Desteklenen İşletim Sistemi | Windows 10 64-bit veya Windows 11 64-bit. |
| Kurulum Paketi | `mysetup.exe` |
| Varsayılan Kurulum Konumu | `C:\Program Files\LED Kontrolcüsü` |
| Uygulama Mimarisi | 64-bit Windows masaüstü uygulaması. |
| İlk Cihaz Kurulumu İçin | Bluetooth Low Energy (BLE) destekli bir Windows cihazı. |
| Günlük Kullanım İçin | Uygulama ile ESP32'nin aynı yerel ağda (Wi-Fi) olması. |
| Uyumlu Kontrol Cihazı | ESP32 üzerinde bu uygulamayla uyumlu firmware çalıştıran sistem. |
| LED Altyapısı | WS2812B veya eşdeğer adreslenebilir LED şerit. |
| İnternet Gereksinimi | Zorunlu değil, yalnızca yerel ağ bağlantısı yeterlidir. |
| Linux / macOS Desteği | Yerel ve resmi destek bulunmamaktadır. |

**Ek Bilgiler:**
- Uygulama tamamen Windows odaklıdır ve yayın çıktısı bu platform için hazırlanmıştır.
- Kurulumdan sonra gerekli tüm çalışma dosyaları uygulama klasörüne yerleşir.
- Kullanıcıya ait profil dosyaları güvenli bir şekilde yerel kullanıcı dizininde tutulur.
- Uygulama, cihazı tekrar bulmayı hızlandırmak için son bağlı IP bilgisini yerelde saklar.

### Kurulum Rehberi

#### Windows Kurulumu
1. GitHub deposundan veya Yayınlar (Releases) sayfasından `mysetup.exe` dosyasını indirin.
2. İndirdiğiniz dosyaya çift tıklayarak kurulum sihirbazını başlatın.
3. Windows SmartScreen uyarısı görürseniz `Ek bilgi (More info)` ardından `Yine de çalıştır (Run anyway)` seçeneğine tıklayın.
4. Gerekirse yönetici izni vererek kuruluma devam edin.
5. Kurulum klasörü olarak varsayılan yolu (`C:\Program Files\LED Kontrolcüsü`) kullanabilir veya kendi tercihinize göre değiştirebilirsiniz.
6. Kurulum tamamlandıktan sonra uygulamayı Başlat menüsünden veya masaüstü kısayolundan açabilirsiniz.
7. İlk açılışta ağ veya Bluetooth erişimiyle ilgili Windows güvenlik duvarı uyarıları gelirse onay verin.

#### Uygulamayı Kaldırma
- Windows "Ayarlar > Uygulamalar" bölümünden standart şekilde kaldırabilirsiniz.
- Alternatif olarak kurulum klasöründeki kaldırıcıyı (`unins000.exe`) çalıştırabilirsiniz.

### Hızlı Başlangıç Rehberi

Sistemi sorunsuz bir şekilde kullanmaya başlamak için önerilen akış şu şekildedir:

1. ESP32 tabanlı LED denetleyicinize güç verin.
2. **İlk kurulum için, uygulamayı açmadan önce Windows Ayarları > Bluetooth ve Cihazlar menüsüne giderek ESP32 cihazınızı bilgisayarınızla eşleştirmeniz gerekmektedir.** Eşleştirme işlemi tamamlandıktan sonra uygulamayı başlatın.
3. Cihaz ilk kez kuruluyorsa arayüzden `BLE Kurulum` düğmesine tıklayın.
4. Açılan listeden `LEDController-Setup` cihazını seçin.
5. Bağlanmasını istediğiniz Wi-Fi ağının SSID (isim) ve şifresini girip cihaza gönderin. *(Bu işlem yalnızca ilk kurulum için geçerlidir, sonraki kullanımlarda cihazınız ağ üzerinden otomatik olarak algılanacak ve bağlanacaktır.)*
6. Kurulum tamamlandığında uygulama cihazın IP adresini alır ve bağlantıyı kurar.
7. Sonraki kullanımlarda uygulamayı açtığınızda çoğu zaman sadece `Otomatik Bağlan` düğmesine basmanız yeterlidir.
8. `Renk` sekmesinde tekil LED düzenlemelerinizi, `Animasyon` sekmesinde dinamik efekt yönetiminizi yapabilirsiniz.
9. Beğendiğiniz ayarları daha sonra kullanmak üzere profil olarak kaydedin.

### Detaylı Kullanım Kılavuzu

#### 1. Profil Yönetimi
Profil bölümü statik LED düzenlerinizi ve temel yapılandırmanızı saklamak için kullanılır.
- **Yeni:** Yeni ve boş bir profil oluşturur.
- **Kaydet:** Mevcut profilin LED renklerini, parlaklık değerlerini ve şerit yapılandırmasını saklar.
- **Sil:** Seçili profili sistemden siler.
- Profil sistemi sayesinde farklı kullanım senaryoları (çalışma modu, ambiyans, vitrin vb.) için ayrı sahneler oluşturabilirsiniz.

#### 2. Şerit Ayarları
Şerit ayarları bölümünde sol, orta ve sağ şerit için aktif LED sayısını donanımınıza göre belirleyebilirsiniz. (Sol: maks 32, Orta: maks 70, Sağ: maks 32). `LED Numaralarını Göster` seçeneği, tuval üzerinde LED indekslerini görünür hale getirerek eşleme ve test işlemlerini kolaylaştırır.

#### 3. LED Seçimi ve Renk Düzenleme
Arayüz üzerinden tüm LED'leri, belirli bir şeridi veya tekil LED'leri seçebilirsiniz. `Renk Düzenleme` kilidi açıkken, renk paleti üzerinden seçili LED'lere anında renk atayabilirsiniz. Bu özellik marka renkleri veya bölgesel aydınlatma oluşturmak için idealdir.

#### 4. Parlaklık Kontrolü
Parlaklık paneli, düşük/orta/yüksek şeklinde hızlı ön ayarlar ve yüzde bazlı hassas kaydırıcı sunar. İsteğe bağlı olarak sadece seçili LED'lerin veya tüm sistemin parlaklığı ayarlanabilir.

#### 5. Animasyon Sekmesi
- **Birleşik Mod:** Tüm şeritler tek bir animasyon mantığıyla senkronize çalışır.
- **Bağımsız Mod:** Sol, orta ve sağ şerit tamamen ayrı yönetilir. Her şeride farklı bir animasyon, hız veya renk atanabilir.
- Animasyonlar üzerinde oynat, duraklat, yön değiştir ve hızı ayarla gibi kapsamlı kontroller mevcuttur.

### Arayüz Ekranları ve Ekran Görüntüleri

Uygulamanın genel görünümü ve sunduğu özelliklerin arayüz üzerindeki dağılımı aşağıda yer almaktadır.

**1. Ana Ekran (Uygulama Açılışı)**
*(Uygulama ilk başlatıldığında karşılaşılan temel arayüz.)*
![Ana Ekran](<img width="1920" height="1040" alt="1" src="https://github.com/user-attachments/assets/791ec382-fd2c-4d33-999b-f0ba246b35bd" />)

**2. Renk Sekmesi Genel Görünümü**
*(LED kontrolü, parlaklık paneli, renk seçici ve cihaz durum kartları bir arada.)*
![Renk Sekmesi](<img width="294" height="881" alt="2" src="https://github.com/user-attachments/assets/a275d806-26a4-440c-b134-b5c5994e4ad9" />)

**3. Animasyon Sekmesi (Oynatım Anı)**
*(Animasyon sekmesine geçildiğinde ve rastgele bir animasyon oynatıldığındaki genel görünüm.)*
![Animasyon Genel](<img width="1920" height="1040" alt="3" src="https://github.com/user-attachments/assets/ea27b861-be37-4a0d-84d8-95b73acceb5c" />)

**4. Animasyon Kartları (Bölüm 1)**
*(Uygulama içerisinde yer alan yerleşik animasyon seçenekleri.)*
![Animasyon Kartları 1](<img width="277" height="960" alt="4" src="https://github.com/user-attachments/assets/74cd6951-d173-402d-b80f-f7b84a8b0f7e" />)

**5. Animasyon Kartları (Bölüm 2), Kontroller ve Cihaz Durumu**
*(Diğer animasyon seçenekleri, detaylı oynatma kontrolleri ve anlık cihaz bilgisi.)*
![Animasyon Kartları 2 ve Kontroller](<img width="281" height="962" alt="5" src="https://github.com/user-attachments/assets/fb3cd138-982a-4100-9a2f-6a9adcd169e7" />)

**6. LED Detay Görünümü (Yakınlaştırma)**
*(Tuval üzerindeki LED'lere yakınlaştırma yapıldığındaki numaralandırma ve detay görünümü.)*
![LED Zoom](<img width="360" height="859" alt="6" src="https://github.com/user-attachments/assets/4185c79b-6431-47b7-ae8a-02d9e7f436ad" />)

**7. Yeni Profil Oluşturma Penceresi**
*(Kullanıcının kendi sahne ayarlarını kaydedebildiği profil oluşturma ekranı.)*
![Yeni Profil](<img width="386" height="213" alt="7" src="https://github.com/user-attachments/assets/eb6e20c7-4d92-4d29-ac6b-f0b175271621" />)

### Sık Karşılaşılan Sorunlar ve Çözüm Önerileri

**Cihaz otomatik bulunmuyor:**
ESP32'nin açık ve bilgisayarınızla aynı yerel ağda olduğundan emin olun. Gerekirse `BLE Kurulum` ile cihazı ağa yeniden dahil edin ve Windows güvenlik duvarından uygulamaya izin verildiğini doğrulayın.

**BLE cihazı listede görünmüyor:**
Bilgisayarınızın Bluetooth özelliğinin açık olduğundan ve cihazın çok uzakta olmadığından emin olun. ESP32 cihazını yeniden başlatarak tekrar `Tara` işlemini deneyin.

**Wi-Fi bilgileri gönderildi ama bağlantı kurulmadı:**
Girdiğiniz SSID veya şifrenin doğru olduğundan emin olun. ESP32, 5GHz ağları desteklemez; 2.4GHz frekanslı bir ağ kullandığınızı doğrulayın.

**Renk değişikliği veya animasyon uygulanmıyor:**
Cihaza aktif bir bağlantınızın olduğunu Cihaz Durumu panelinden kontrol edin. Renk sekmesindeyseniz `Renk Düzenleme` kilidinin açık olduğundan emin olun.

### Sürüm Geçmişi ve Güncelleme Notları

**v1.0.0**
- İlk dağıtılabilir Windows masaüstü sürümü yayınlandı.
- Statik LED renk düzenleme ve profil kaydetme sistemi entegre edildi.
- BLE tabanlı ilk Wi-Fi kurulum desteği eklendi.
- mDNS tabanlı otomatik cihaz keşfi sağlandı.
- Bağlantı kopmalarına karşı heartbeat ve otomatik yeniden bağlanma mantığı kuruldu.
- 30 adet yerleşik animasyon ve bağımsız animasyon kontrol modları sisteme dahil edildi.

### Lisans Bilgileri

**Tüm Hakları Saklıdır (All Rights Reserved)**

Bu GitHub deposu, kaynak kod dağıtımı yerine yalnızca son kullanıcı kurulumu ve ürün tanıtımı amacıyla hazırlanmıştır. Aksi açıkça belirtilmedikçe; bu depoda paylaşılan kurulum paketinin (.exe dosyaları), dokümantasyonun ve tasarımların kopyalanması, dağıtılması, tersine mühendislik (reverse engineering) işlemlerine tabi tutulması veya izinsiz ticari amaçlarla kullanılması kesinlikle yasaktır. Kaynak kodlar bu depoya dahil değildir ve tüm fikri mülkiyet hakları geliştiriciye aittir.

### İletişim Bilgileri

- **Geliştirici:** Tunahan D.
- **İletişim E-Posta:** [t.doner06@gmail.com](mailto:t.doner06@gmail.com)
- **Dağıtım Kanalı:** GitHub deposu ve GitHub Releases
- **Uygulama Türü:** Binary-only Windows dağıtımı (Kapalı Kaynak)

---

## English Documentation

### What Is the WS2812B LED Controller Desktop App?

The LED Controller is a Windows desktop application developed to manage WS2812B addressable LED strips running on an ESP32-based controller. The application offers end-user-focused features such as individual LED selection, bulk color assignment, brightness adjustment, animation management, profile saving, device discovery, and BLE-based Wi-Fi provisioning for initial setup.

This structure is specifically suited for productized projects that aim to distribute a working desktop application without sharing the source code.

### Project Purpose and Target Audience

The main purpose of this project is to make ESP32-driven WS2812B LED setups manageable without requiring technical knowledge.

Our target audience includes:
- Makers and DIY users developing their own LED hardware.
- Users creating ambient lighting for desks, rooms, showcases, or TVs.
- Developers who want to offer their ESP32-based LED systems to customers with a professional interface.
- Users looking to consolidate animation, color scenes, and profile management into a single desktop application.

### Core Problem Solved by the Application

One of the biggest challenges in addressable LED projects is that daily usage remains dependent on technical details, even after the hardware is set up. In many systems, the user;
- Has to perform Wi-Fi configuration via serial port or manual tools.
- Struggles to find the device's IP address on the network.
- Uses different tools for individual LED control versus animation control.
- Cannot manage profiles and scene presets centrally.
- Has to restart the system during connection drops.

The LED Controller solves these problems by:
- Completing the initial Wi-Fi setup directly within the app via BLE.
- Automatically discovering the device on the network using mDNS.
- Remembering the last successful IP address for fast reconnection.
- Offering both individual LED editing and animation management in the same interface.
- Storing color, brightness, and strip configurations locally via the profile system.
- Improving connection continuity with a heartbeat and auto-reconnect logic.

### Technical Features and Key Capabilities

#### Application Features
- Fluid Windows desktop interface.
- High-performance visual LED canvas.
- Individual LED selection and strip-based bulk selection.
- Quick color application to selected LEDs or the entire strip.
- Turning off selected LEDs or the entire system with one click.
- Quick brightness presets and a precise brightness slider.
- Profile creation, saving, deletion, and auto-loading of the last profile.
- Real-time device status and connection indicator.
- Auto-connect and manual disconnect options.
- Seamless initial device setup via BLE.

#### Animation Features
- 30 built-in, customizable animation options.
- Support for unified mode and independent strip mode.
- Completely separate animation playback support for each strip.
- Play, pause, resume, and stop controls.
- Animation speed adjustment and flow direction setting.
- Specific brightness level selection for animations.
- Custom color palette usage in color-supported animations.
- Smart flow that preserves animation state when switching between tabs.

#### Network and Device Communication
- Latency-free UDP-based communication protocol.
- Integrated mDNS support for automatic device discovery.
- Wi-Fi provisioning over BLE (Bluetooth Low Energy).
- 5-second heartbeat check for connection stability.
- Fast reconnection attempts in case of lost connection.
- Silent background searching during long-term network disconnections.
- Telemetry-based connection status and signal quality tracking.

#### Hardware and Compatible Device Profile
The current desktop application and compatible firmware structure are designed to work with the following hardware profile:
- **Controller:** ESP32
- **LED Type:** WS2812B
- **Communication Port:** UDP 4210
- **mDNS Service Name:** `_ledcontrol._udp.local`
- **Default mDNS Hostname:** `ledcontroller.local`
- **BLE Setup Name:** `LEDController-Setup`
- **Architecture:** Series-connected strip structure over a single data line.
- **Data Pin:** GPIO 13 (Firmware side)
- **Physical LED Capacity:** Left 32, Middle 70, Right 32.
- **Default Active LEDs:** Left 30, Middle 30, Right 30.

### System Requirements and Compatibility

| Feature | Requirement / Status |
| --- | --- |
| Supported OS | Windows 10 64-bit or Windows 11 64-bit. |
| Installation Package | `mysetup.exe` |
| Default Install Location | `C:\Program Files\LED Kontrolcüsü` |
| Application Architecture | 64-bit Windows desktop application. |
| For Initial Device Setup | A Windows device with Bluetooth Low Energy (BLE) support. |
| For Daily Use | The application and ESP32 must be on the same local network (Wi-Fi). |
| Compatible Controller | A system running compatible firmware on an ESP32. |
| LED Infrastructure | WS2812B or equivalent addressable LED strip. |
| Internet Requirement | Not mandatory, only a local network connection is sufficient. |
| Linux / macOS Support | No native or official support. |

### Installation Guide

#### Windows Installation
1. Download the `mysetup.exe` file from the GitHub repository or the Releases page.
2. Double-click the downloaded file to start the installation wizard.
3. If you see a Windows SmartScreen warning, click `More info` and then `Run anyway`.
4. Grant administrator permissions if prompted to continue the installation.
5. You can use the default installation path (`C:\Program Files\LED Kontrolcüsü`) or change it to your preference.
6. Once the installation is complete, you can open the application from the Start menu or desktop shortcut.
7. Allow network or Bluetooth access if prompted by the Windows firewall upon initial startup.

#### Uninstalling the Application
- You can uninstall it via Windows "Settings > Apps" normally.
- Alternatively, you can run the uninstaller (`unins000.exe`) located in the installation folder.

### Quick Start Guide

The recommended workflow for a smooth start is as follows:

1. Power on your ESP32-based LED controller.
2. **For the initial setup, before opening the application, you must pair your ESP32 device with your computer by going to Windows Settings > Bluetooth & Devices.** Once paired, launch the application.
3. If setting up the device for the first time, click the `BLE Setup` button on the interface.
4. Select the `LEDController-Setup` device from the list.
5. Enter the SSID (name) and password of the Wi-Fi network you want to connect to and send it to the device. *(This process is only valid for the initial setup; for subsequent uses, your device will be automatically detected and connected over the network.)*
6. Once the setup is complete, the application receives the device's IP address and establishes the connection.
7. For future uses, simply pressing the `Auto Connect` button upon opening the application is usually sufficient.
8. You can make individual LED adjustments in the `Color` tab and manage dynamic effects in the `Animation` tab.
9. Save your preferred settings as a profile for later use.

### Detailed User Guide

#### 1. Profile Management
The Profile section is used to store your static LED layouts and basic configurations.
- **New:** Creates a new, empty profile.
- **Save:** Stores the LED colors, brightness values, and strip configuration of the current profile.
- **Delete:** Removes the selected profile from the system.
- Thanks to the profile system, you can create separate scenes for different usage scenarios (work mode, ambient, showcase, etc.).

#### 2. Strip Settings
In the strip settings section, you can define the number of active LEDs for the left, middle, and right strips according to your hardware (Left: max 32, Middle: max 70, Right: max 32). The `Show LED Numbers` option makes LED indices visible on the canvas, facilitating mapping and testing processes.

#### 3. LED Selection and Color Editing
You can select all LEDs, a specific strip, or individual LEDs via the interface. When the `Color Editing` lock is open, you can instantly assign colors to selected LEDs via the color palette. This feature is ideal for creating brand colors or regional lighting.

#### 4. Brightness Control
The brightness panel offers quick presets (low/medium/high) and a percentage-based precise slider. Optionally, brightness can be adjusted for only the selected LEDs or the entire system.

#### 5. Animation Tab
- **Unified Mode:** All strips run synchronously with a single animation logic.
- **Independent Mode:** Left, middle, and right strips are managed completely separately. Different animations, speeds, or colors can be assigned to each strip.
- Comprehensive controls such as play, pause, change direction, and adjust speed are available for animations.

### Interface Screens and Screenshots

The general overview of the application and the distribution of its features across the interface are provided below.

**1. Main Screen (Application Launch)**
*(The primary interface encountered when the app is first launched.)*
![Main Screen](<img width="1920" height="1040" alt="1" src="https://github.com/user-attachments/assets/9096950a-f993-4546-9e4e-d09afa52dc93" />)

**2. Color Tab Overview**
*(LED control, brightness panel, color picker, and device status cards together.)*
![Color Tab](<img width="294" height="881" alt="2" src="https://github.com/user-attachments/assets/10f74408-3501-4161-ac4f-d59069836852" />)

**3. Animation Tab (Playback View)**
*(General view when switched to the animation tab and a random animation is playing.)*
![Animation General](<img width="1920" height="1040" alt="3" src="https://github.com/user-attachments/assets/7ffa8a06-a5f4-447f-96a5-5f535b4eba2e" />)

**4. Animation Cards (Part 1)**
*(Built-in animation options available within the application.)*
![Animation Cards 1](<img width="277" height="960" alt="4" src="https://github.com/user-attachments/assets/91956d1f-b9b3-4596-a75d-cd3ae4db45eb" />)

**5. Animation Cards (Part 2), Controls, and Device Status**
*(Remaining animation options, detailed playback controls, and real-time device info.)*
![Animation Cards 2 and Controls](<img width="281" height="962" alt="5" src="https://github.com/user-attachments/assets/87f8daf1-cfbd-4cb2-9f5f-631213d6423f" />)

**6. LED Detail View (Zoom In)**
*(Numbering and detail view when zooming into the LEDs on the canvas.)*
![LED Zoom](<img width="360" height="859" alt="6" src="https://github.com/user-attachments/assets/e4372468-2953-429d-8a7b-f7a7bb4ae76a" />)

**7. Create New Profile Window**
*(The profile creation screen where the user can save their custom scene settings.)*
![New Profile](<img width="386" height="213" alt="7" src="https://github.com/user-attachments/assets/1116124f-f3d0-4d4b-8e50-5f5256ac6416" />)

### Troubleshooting Guide

**Device is not found automatically:**
Make sure the ESP32 is powered on and on the same local network as your computer. If necessary, re-include the device in the network using `BLE Setup` and verify that the application is allowed through the Windows firewall.

**BLE device does not appear in the list:**
Ensure your computer's Bluetooth is turned on and the device is not too far away. Restart the ESP32 device and try the `Scan` process again.

**Wi-Fi credentials sent but no connection established:**
Make sure the SSID and password you entered are correct. ESP32 does not support 5GHz networks; verify you are using a 2.4GHz network.

**Color change or animation not applied:**
Check the Device Status panel to ensure you have an active connection to the device. If you are in the color tab, make sure the `Color Editing` lock is open.

### Version History and Release Notes

**v1.0.0**
- Initial distributable Windows desktop version released.
- Integrated static LED color editing and profile saving system.
- Added initial Wi-Fi setup support via BLE.
- Achieved automatic device discovery based on mDNS.
- Implemented heartbeat and auto-reconnect logic against connection drops.
- Included 30 built-in animations and independent animation control modes into the system.

### License Information

**All Rights Reserved**

This GitHub repository is prepared solely for end-user installation and product presentation, not for source code distribution. Unless explicitly stated otherwise; copying, distributing, reverse engineering, or unauthorized commercial use of the installation package (.exe files), documentation, and designs shared in this repository is strictly prohibited. Source codes are not included in this repository, and all intellectual property rights belong to the developer.

### Contact Information

- **Developer:** Tunahan D.
- **Contact E-Mail:** [t.doner06@gmail.com](mailto:t.doner06@gmail.com)
- **Distribution Channel:** GitHub Repository and GitHub Releases
- **Application Type:** Binary-only Windows distribution (Closed Source)
