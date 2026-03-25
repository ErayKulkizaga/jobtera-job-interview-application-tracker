# Jobtera

![Electron](https://img.shields.io/badge/Electron-28-47848F?logo=electron&logoColor=white)
![Platform](https://img.shields.io/badge/platform-Windows-0078D6?logo=windows&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)

**Jobtera**, iş başvurularınızı bilgisayarınızda **çevrimdışı** tutmanız için tasarlanmış, Türkçe arayüzlü bir **masaüstü takip uygulamasıdır**. [Electron](https://www.electronjs.org/) ile yazılmıştır; verileriniz bulutta değil, kendi kullanıcı dizininizde saklanır.

> Bu depo GitHub üzerinde **TrackJoB** adıyla yayınlanabilir; uygulama adı **Jobtera**dır.

---

## İçindekiler

- [Özellikler](#özellikler)
- [Kurulum](#kurulum)
- [Geliştirme](#geliştirme)
- [Windows’ta derleme](#windowsta-derleme)
- [Veri, ayarlar ve yedekler](#veri-ayarlar-ve-yedekler)
- [Klavye kısayolları](#klavye-kısayolları)
- [Proje yapısı](#proje-yapısı)
- [Katkıda bulunma](#katkıda-bulunma)
- [Lisans](#lisans)

---

## Özellikler

### Başvuru yönetimi

- Şirket, pozisyon, konum, başvuru / mülakat tarihi, ilan URL’si, notlar, etiketler
- Çalışma şekli (uzaktan / hibrit / ofis), öncelik, isteklilik skoru (yıldız)
- Durum: *Başvuruldu*, *İncelemede*, *Mülakat*, *Teklif*, *Reddedildi*, *Vazgeçildi*
- Rozet üzerinden hızlı durum değişimi; toplu silme / durum güncelleme

### Görünümler

| Görünüm | Açıklama |
|--------|----------|
| **Liste** | Filtrelenebilir tablo, sıralama, arama, istatistik kartları |
| **Kanban** | Sürükle-bırak ile durum güncelleme; pencere boyutuna uyumlu sütun düzeni |
| **Takvim** | Mülakat ve tarih odaklı aylık görünüm |
| **Analiz** | Grafikler, KPI’lar; PDF / yazdırma desteği |

### Verimlilik

- **Global arama** (`Ctrl+K`) — başvurular arasında hızlı bul ve düzenle
- **Şablonlar** — hazır şablonlardan yeni başvuru başlat
- **Şirket / şehir / pozisyon** alanlarında akıllı öneriler (özellikle Türkiye odaklı şirket listesi)
- **CV sürümleri** — dosya ekleri ve sürüm takibi
- **Aylık hedef** çubuğu ve yaklaşan mülakat bandı
- **Otomatik günlük yedek** (son 7 gün)
- **İçe / dışa aktarım** (JSON / CSV)
- Açık / koyu tema, vurgu rengi seçenekleri
- İlk açılış **tanıtım** sihirbazı (isterseniz ayarlardan sıfırlanabilir)

---

## Kurulum

1. [Node.js](https://nodejs.org/) **18 veya üzeri** sürümünü kurun.
2. Depoyu klonlayın:

   ```bash
   git clone https://github.com/ErayKulkizaga/TrackJoB.git
   cd TrackJoB
   ```

3. Bağımlılıkları yükleyin:

   ```bash
   npm install
   ```

---

## Geliştirme

Geliştirme modunda uygulamayı başlatmak için:

```bash
npm start
```

---

## Windows’ta derleme

| Komut | Çıktı |
|--------|--------|
| `npm run build:portable` | Kurulum gerektirmeyen taşınabilir `.exe` |
| `npm run build:installer` | NSIS kurulum sihirbazı |
| `npm run build` | `electron-packager` ile `dist` klasörüne paket |

Oluşan dosyalar `dist/` altındadır.

---

## Veri, ayarlar ve yedekler

Uygulama verileri Windows’ta genelde şu klasöre yazılır:

`%APPDATA%\jobtera\`

| Dosya / klasör | İçerik |
|----------------|--------|
| `jobtera-applications.json` | Tüm başvuru kayıtları |
| `jobtera-settings.json` | Tema, hedef, tanıtım tamamlandı bayrağı vb. |
| `backups\` | Günlük otomatik yedekler |
| `cvs\` | CV dosyaları (uygulama tarafından yönetilen kopyalar) |

Ayarlar içinde **“Veri klasörünü aç”** ve **“Yedek klasörü”** ile bu konumlara hızlıca gidebilirsiniz.

---

## Klavye kısayolları

| Kısayol | İşlev |
|---------|--------|
| `Ctrl+N` | Yeni başvuru |
| `Ctrl+K` | Hızlı ara (spotlight) |
| `Ctrl+F` | Liste aramasına odaklan |
| `?` | Kısayol listesi |
| `Esc` | Modal / panel kapat |
| `Alt+1` … `Alt+4` | Liste / Kanban / Takvim / Analiz |

---

## Proje yapısı

```
TrackJoB/
├── main.js           # Electron ana süreç (pencere, IPC, dosya I/O)
├── preload.js        # Güvenli renderer köprüsü
├── package.json
└── renderer/
    ├── index.html    # Arayüz iskeleti
    ├── app.js        # Uygulama mantığı
    ├── styles.css    # Stiller
    ├── splash.html   # Açılış ekranı
    └── splash.css
```

---

## Katkıda bulunma

1. Bu depoyu fork edin.
2. Yeni bir dal oluşturun (`git checkout -b ozellik/yeni-ozellik`).
3. Değişikliklerinizi anlamlı commit mesajlarıyla işleyin.
4. Dalınızı gönderin ve bir Pull Request açın.

Hata bildirimi ve öneriler için [Issues](https://github.com/ErayKulkizaga/TrackJoB/issues) kullanabilirsiniz.

---

## Lisans

Bu proje [MIT](LICENSE) lisansı ile sunulmaktadır.
