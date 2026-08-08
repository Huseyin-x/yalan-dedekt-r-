# 🧠 Arduino GSR Stres Analiz Sistemi

Arduino UNO/Nano kullanılarak geliştirilmiş, GSR sensörü ile deri iletkenliği değişimlerini ölçen, IR kumanda kontrollü LCD ekranlı analiz sistemidir.

⚠️ **Uyarı:** Bu proje gerçek bir yalan dedektörü değildir. GSR sensörü sadece stres ve deri iletkenliği değişimlerini ölçer. Sonuçlar kesin bir yalan tespiti olarak kabul edilemez.

---

# 🚀 Özellikler

- ✅ GSR sensörü ile ölçüm
- ✅ IR kumanda kontrolü
- ✅ 16x2 I2C LCD ekran
- ✅ Otomatik kalibrasyon sistemi
- ✅ Stres yüzdesi hesaplama
- ✅ Tahmini BPM gösterimi
- ✅ EEPROM kayıt sistemi
- ✅ 30 adet geçmiş kayıt saklama
- ✅ Ayarlar menüsü
- ✅ PIN korumalı ayarlar
- ✅ Ekran koruyucu modu

---

# 📦 Kullanılan Malzemeler

| Malzeme | Adet |
|---|---|
| Arduino UNO / Nano | 1 |
| 16x2 I2C LCD | 1 |
| GSR Sensörü | 1 |
| IR Alıcı Modülü | 1 |
| IR Kumanda | 1 |
| Breadboard | 1 |
| Jumper Kablo | Yeteri kadar |

---

# 📚 Gerekli Kütüphaneler

Projede kullanılan kütüphaneler:

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <IRremote.h>
#include <EEPROM.h>
```

## Kurulum

### LiquidCrystal_I2C

Arduino IDE:

```
Araçlar
 └── Kütüphane Yönetimi
      └── LiquidCrystal I2C
```

Önerilen sürüm:

```
LiquidCrystal I2C by Frank de Brabander
```

---

### IRremote

Arduino IDE üzerinden:

```
IRremote by Armin Joachimsmeyer
```

kurulmalıdır.

---

### Hazır Gelen Kütüphaneler

Arduino ile birlikte gelir:

```
Wire
EEPROM
```

---

# 🔌 Bağlantı Şeması

## 📟 I2C LCD 16x2

| LCD | Arduino UNO |
|---|---|
| VCC | 5V |
| GND | GND |
| SDA | A4 |
| SCL | A5 |

---

## 🖐 GSR Sensörü

| GSR | Arduino UNO |
|---|---|
| VCC | 5V |
| GND | GND |
| SIG | A0 |

Kod bağlantısı:

```cpp
const int GSR_PIN = A0;
```

---

## 📡 IR Alıcı

| IR Alıcı | Arduino UNO |
|---|---|
| OUT | D11 |
| VCC | 5V |
| GND | GND |

Kod bağlantısı:

```cpp
const int IR_PIN = 11;
```

---

# 🔧 Genel Bağlantı Görünümü

```
              Arduino UNO

        +----------------+
        |                |
 LCD    |                |
 SDA ---| A4             |
 SCL ---| A5             |
 VCC ---| 5V             |
 GND ---| GND            |
        |                |
 GSR    |                |
 SIG ---| A0             |
 VCC ---| 5V             |
 GND ---| GND            |
        |                |
 IR     |                |
 OUT ---| D11            |
 VCC ---| 5V             |
 GND ---| GND            |
        +----------------+

```

---

# 🎮 Kumanda Kontrolleri

| Tuş | Görev |
|---|---|
| 1 | Sorguyu bitir / rapor göster |
| 2 | Ayarlar menüsü |
| OK | Kalibrasyon başlat |
| ↑ | Menü yukarı |
| ↓ | Menü aşağı |
| → | Değer artır |
| ← | Değer azalt |

---

# ⚙️ Çalışma Mantığı

1. Sistem açılır.
2. Kullanıcı OK tuşuna basarak kalibrasyon yapar.
3. GSR sensörü temel değerleri hesaplar.
4. Ölçüm sırasında stres değişimleri takip edilir.
5. LCD ekranda sonuçlar gösterilir.
6. Test sonunda sonuç EEPROM hafızasına kaydedilir.

---

# 📂 Dosya Yapısı

```
Arduino-GSR-Stres-Analiz
│
├── Yalan_Dedektoru.ino
│
├── README.md
│
└── images
    └── devre.png
```

---

# 🛠️ Kurulum

1. Arduino IDE yükleyin.
2. Gerekli kütüphaneleri kurun.
3. `Yalan_Dedektoru.ino` dosyasını açın.
4. Arduino kartınızı seçin.
5. Kodu yükleyin.
6. Sensör bağlantılarını yapın.

---

# 👨‍💻 Geliştirici

Arduino tabanlı açık kaynak GSR analiz projesi.

⭐ Projeyi beğendiyseniz GitHub üzerinden destek olabilirsiniz.
