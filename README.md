# Aşkım ve Hanım - A Love Story Game

Romantic 2D platform oyunu, Phaser 3 framework'ü ile yapılmış.

## Oyun Konsepti

Oyuncu, kız arkadaşını kurtarmak için 5 seviyeli bir yolculuğa çıkar. Bir robot tarafından kaçırılan sevgilisini bulmak için platformlar arasında atlayış yapacak, düşmanlarla savaşacak, power-up'lar toplayacaktır.

## Özellikler

- **5 Seviye**: Artan zorluk derecesi
- **Mini Bosslar**: Yanlış Anlama, Hata, Gurur, İnat
- **Final Boss**: Küslük-9000
- **Dialog Sistemi**: Karakterlerin hikâyesi ilerlerken konuşması
- **Power-up Sistemi**: 
  - Kalp (Can yenileme)
  - Roket Hız Güçlendirmesi
- **Checkpoint Sistemi**: Her levelde otomats kaydedilir
- **Mobil Uyumlu**: Dokunmatik kontroller ile çalışır
- **Responsive Design**: Tüm ekran boyutlarında çalışır

## Karakterler

### Ana Karakter - "Aşkım"
- Kırmızı renk
- Platform oyunundaki tipik hareketler
- Kılıç saldırısı yapabilir
- Normal hız + Roket boost modunda 2x hızlı

### Kurtarılacak - "Hanım"
- Pembe renk
- Sevgilisini teşvik eden diyaloglar
- Kontrol edilemeyen NPC karakter

### Final Boss - "Küslük-9000"
- Metal robot tasarımı
- Roket hareketi ve saldırı
- 2 seviyeli AI: Agresif + Zayıflayan

### Mini Bosslar
Her Mini Boss'un kendine ait karakter ve mesajı var

## Kontroller

### Bilgisayar
- **A/D veya Sol/Sağ Oklar**: Hareket
- **W/Yukarı Ok veya Boşluk**: Zıplama
- **X**: Saldırı

### Mobil
- Ekranın altında bulunan dokunmatik butonlar
- Sol/Sağ oklar: Hareket
- ZIPLA: Zıplama
- SALDIRI: Kılıç saldırısı

## Teknik Detaylar

### Stack
- **Frontend**: Phaser 3 (HTML5 Game Framework)
- **Rendering**: Canvas/WebGL
- **Physics**: Arcade Physics
- **Server**: HTTP Server (localhost:8000)

### Proje Yapısı

```
gaming/
├── index.html              # Entry point
├── styles/
│   └── style.css          # UI styling
├── src/
│   ├── main.js            # Game initialization
│   ├── utils/
│   │   ├── Constants.js   # Game constants
│   │   └── Config.js      # Phaser config
│   ├── scenes/
│   │   ├── BootScene.js           # Texture/Animation setup
│   │   ├── PreloadScene.js        # Intro screen
│   │   ├── MenuScene.js           # Main menu
│   │   ├── BaseLevelScene.js      # Base class for levels
│   │   ├── Level1Scene.js         # Level 1-5
│   │   ├── Level2Scene.js
│   │   ├── Level3Scene.js
│   │   ├── Level4Scene.js
│   │   ├── Level5Scene.js
│   │   └── FinalBossScene.js      # Final Boss battle
│   ├── sprites/
│   │   ├── Player.js      # Player character
│   │   ├── Princess.js    # Princess/Love interest
│   │   ├── Boss.js        # Final boss controller
│   │   └── MiniBoss.js    # Mini boss controller
│   ├── managers/
│   │   ├── DialogManager.js       # Conversation system
│   │   ├── AudioManager.js        # Sound effects (placeholder)
│   │   ├── CheckpointManager.js   # Save/Load system
│   │   └── PowerUpManager.js      # Item management
│   └── assets/
│       ├── images/        # (Placeholder for future assets)
│       └── audio/         # (Placeholder for future sounds)
```

## Seviyeler

### Level 1 - Tanışma Yolu
- Giriş niteliğinde seviye
- 2 Mini Boss (Yanlış Anlama, Hata)
- Basit platform atlama

### Level 2 - İlk Zorluklar
- Tırmanma platformları
- 2 Mini Boss (Gurur, İnat)
- Daha geniş açık alanlar

### Level 3 - Engeller ve Mini Boss
- Dağ tırmanması teması
- 3 Mini Boss
- Zorluk artar

### Level 4 - Kovalamaca
- Hızlı hareket gerektiren seviye
- Hızlı düşmanlar
- Kız arkadaşı yaklaşıyor

### Level 5 - Kurtarış Yolu
- Son hazırlık
- 4 Mini Bosstan tüm türler
- Final Boss'a gidişi açar

### Final Level - Küslük-9000 ile Savaş
- Boss arena
- 20 HP'lik boss
- İki fazlı savaş mekanikası
- Kurtarış ve final sahnesi

## Oyun Mekanikleri

### Can Sistemi
- 3 kalp (can) ile başlarsınız
- Kalp toplayarak canı yenileyebilirsiniz
- 0 kalpa düşmek = Level tekrarı

### Checkpoint Sistemi
- Browser localStorage kullanılır
- Her seviyenin başında otomatik kaydedilir
- Menüden "Devam Et" ile kaldığınız yerden devam edebilirsiniz

### Savaş Sistemi
- Saldırı: X tuşu/SALDIRI butonu
- Kılıç erişim mesafesi: ±30 piksel
- Düşmanlara çarpmak = Hasar
- Roket boost devamında çarpışmalara dayanıklı

### Power-up Sistemi
- **Kalp**: +1 can (max 3)
- **Roket Boost**: 5 saniye boyunca 2x hız

## Başlama

1. **HTTP Server Başlat**:
   ```bash
   cd gaming/
   npx http-server -p 8000
   ```

2. **Tarayıcıda Aç**:
   ```
   http://localhost:8000
   ```

3. **Oyuna Başla**:
   - Giriş ekranında yazı okuyun: "Bu oyun sadece bir kişi için yapıldı."
   - Tıklayın/tuş basın ve oyuna başlayın
   - Menüden "Oyunu Başlat" seçin

## Dialog Sistemi

Oyun, hikâyeyi anlatmak için aşağıdaki diyaloglar kullanır:

- **Aşkım**: Ana karakter, kendi düşüncelerini paylaşır
- **Hanım**: Sevgilisi, teşvik ve uyarılar verir
- **Küslük-9000**: Final Boss, kendini tanıtır
- **Mini Bosslar**: Bozulan duygular, kılıç çekildiğinde konuşur
- **Anlatıcı**: Genel bilgiler vermek için kullanılır

## Veriler

- Oyun durumu: localStorage'de saklanır
- Checkpoint bilgileri:
  - Player pozisyonu (x, y)
  - Can sayısı
  - Level numarası
  - Timestamp

## Mobil Uyumluluk

- Touch events fully supported
- Responsive canvas scaling
- Mobile-friendly UI buttons
- Dayanıklı kontrol sistemi

## Gelecek Geliştirmeler

- Gerçek ses efektleri
- Daha ayrıntılı grafikler
- Daha fazla mini boss türü
- Multiplayer desteği
- Leaderboard sistemi
- Mobil aplikasyon sürümü

## Lisans

Bu oyun özel olarak yapılmıştır. Saygı ile...

---

**Yapımcı**: AI Asistan  
**Motor**: Phaser 3  
**Tarih**: 2026  
**Dil**: Türkçe
