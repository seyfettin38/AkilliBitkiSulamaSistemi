# Akıllı Bitki Sulama Sistemi - Ara Rapor

## 1. Proje Konusu

Bu proje, bir bitkinin sulama ihtiyacını otomatik olarak algılayıp yönetebilen ve belirli saatlerde ışıklandırma sağlayabilen akıllı bir sistem tasarlamayı amaçlamaktadır. Projede su seviyesi, toprak nemi ölçümü ve ışık kontrolü entegre şekilde yapılmaktadır.

---

## 2. Özet

Projenin ilk aşamasında, ESP8266 mikrodenetleyicisi kullanılarak LCD ekran üzerinden bilgi görüntüleme sağlanmıştır. Toprak nem sensörü ve su seviye sensörü başarıyla entegre edilmiştir. Ayrıca, su motoru kontrolü gerçekleştirilmiştir. İlerleyen aşamalarda bitki için zaman ayarlı ışıklandırma sistemi de projeye eklenecektir.

---

## 3. Kullanılan Yöntemler

- **Mikrodenetleyici:** ESP8266  
- **Ekran:** I2C protokolü ile LCD 1602A ekran  
- **Sensörler:** Toprak nem sensörü, su seviye sensörü  
- **Aktüatör:** Su motoru  
- **Programlama Dili:** C++ (Arduino IDE kullanılarak)  
- **Bağlantı Türleri:** Dijital ve analog girişler  
- **Yöntemler:**  
  - Analog okuma (`analogRead`) ve dijital okuma (`digitalRead`) işlemleri  
  - I2C iletişim protokolü ile LCD kontrolü  
  - Basit zamanlayıcı simülasyonu ile ışık yönetimi  

---

## 4. Yapılan Çalışmalar ve Görselleri

- ESP8266'ya LCD 1602A ekran doğru şekilde bağlandı ve "Toprak nemi ve su seviyesi" gibi temel yazılar başarıyla görüntülendi.  
- Toprak nem sensörü ESP8266'nın A0 ve D0 pinlerine bağlanarak hem analog hem dijital veri okuma yöntemleri test edildi.  
- Su seviye sensörü A0 pini kullanılarak detaylı (analog) su seviyesi ölçümü sağlandı.  
- Su motoru, su eksikliğinde devreye girecek şekilde sisteme dahil edildi.  
- Işıklandırma sistemi için dijital çıkış üzerinden LED veya röle ile lamba kontrolü planlandı.  
- Her bileşen ayrı ayrı test edilip doğru çalıştığı onaylandı, ardından bütün sistem tek bir kod dosyasında entegre edildi.  

**Görseller:**  
- ![Fotoğraf 1](./figures/foto1.jpeg)  
- ![Fotoğraf 2](./figures/foto2.jpeg)  
- ![Fotoğraf 3](./figures/foto3.jpeg)  

---

## 5. Elde Edilen Sonuçlar

- LCD ekran, sensörlerden gelen verileri başarıyla ekrana yansıtabiliyor.  
- Toprak nem seviyesi ve su seviyesi doğru şekilde ölçülüp yorumlanabiliyor.  
- Su motoru manuel kontrol yerine sensör verilerine bağlı olarak otomatik çalışacak altyapıya hazır hale getirildi.  
- Işıklandırma modülü için temel kontrol kodları hazırlanmış ve test edilmiştir.  
- Sistem bileşenleri temel seviyede entegre edilmiş durumdadır.  

---

## 6. Karşılaşılan Sorunlar ve Çözümler

| **Sorun**                                   | **Çözüm**                                                                 |
|---------------------------------------------|---------------------------------------------------------------------------|
| ESP8266 için doğru kart sürücüsü bulunamaması | ESP8266 kart paketleri Arduino IDE'ye manuel olarak eklendi.              |
| LCD ekranın adres hatası ve görüntü sorunları | LCD I2C adresi (0x27/0x3F) doğru ayarlanarak çözüm sağlandı.              |
| Sensörlerin aynı pinlere bağlanması sonucu okuma hataları | Her sensör farklı pinlere atanarak ve doğru `analogRead` yapılacak şekilde kablolama düzenlendi. |
| Dijital çıkıştan analog veri beklenmesi      | Dijital ve analog veri okuma farkı anlaşılarak, doğru kullanım yöntemleri uygulandı. |
| Sensör verilerinin sabit kalması             | Kablolama ve pin seçimleri yeniden optimize edilerek doğru veri alınması sağlandı. |

---

## 7. Projenin Devamında Yapılacaklar

- Gerçek zamanlı saat (RTC modülü veya NTP ile) kullanılarak ışıklandırma saatlerinin tam kontrolü yapılacak.  
- Su motorunun çalışmasını daha optimize etmek için su seviyesi ve nem sensörü verileri daha akıllı algoritmalarla değerlendirilecek.  
- Toprak nem sensörü ve su seviye sensörünün analog girişlerde daha doğru veri alınabilmesi için bir analog çoklayıcı (multiplexer) entegre edilmesi planlanmaktadır.  
- Röle modülü entegre edilerek gerçek bir lamba üzerinden ışıklandırma sağlanacak.  
- Sistem güç kaynağı ve kutulama işlemleri tamamlanarak taşınabilir, uzun süreli çalışabilir bir ürün haline getirilecek.  
- Nihai sunum için projenin tüm fonksiyonları gösterilecek bir demo hazırlanacak.  

---

## 8. Proje GitHub Linki
🔗 [Proje GitHub Deposu](https://github.com/seyfettin38/AkilliBitkiSulamaSistemi)
