# 🏢 Remax Now - AI Satış Stratejisti ve Makroekonomi Asistanı

Bu proje, gayrimenkul sektöründeki operasyonel süreçleri hızlandırmak ve veriye dayalı karar alma mekanizmalarını güçlendirmek amacıyla geliştirilmiş, **Yapay Zeka (AI) destekli bir Telegram botu ve Makroekonomik Veri Analiz** sistemidir.

Proje, ofis yöneticilerine ve sahadaki gayrimenkul danışmanlarına gerçek zamanlı, uygulanabilir satış stratejileri sunmayı hedefler.

## 🌟 Öne Çıkan Özellikler

* **🤖 İnteraktif Telegram Asistanı (`ai_strategist.py`):** Yöneticiler ve çalışanlar, Telegram üzerinden tek bir butona tıklayarak güncel portföy verisini yapay zekaya analiz ettirebilir.
* **🧠 Gemini AI Entegrasyonu:** Google'ın en güncel *Gemini 3.0 Flash* modeli kullanılarak, portföydeki ilanların durumu saniyeler içinde yorumlanır ve 3 maddelik eyleme geçirilebilir bir aksiyon/pazarlama planı oluşturulur.
* **📈 Makroekonomik Vizyon (`tcmb_macro.py`):** Türkiye Cumhuriyet Merkez Bankası (TCMB) EVDS API'si üzerinden Türkiye geneli Konut Fiyat Endeksi verileri çekilir. Bu sayede müşterilere bilimsel verilere dayalı yatırım tavsiyeleri verilebilir.
* **📁 Otomatik Raporlama:** Üretilen yapay zeka strateji raporları, ofis arşivlemesi için otomatik olarak `remax_raporlar` klasöründe `.txt` formatında yedeklenir.

## 📂 Proje Yapısı

\`\`\`text
remaxnow_goodwill/
├── remax_raporlar/            # Üretilen strateji raporlarının tutulduğu arşiv klasörü
├── ai_strategist.py           # Telegram botunu ve Gemini AI entegrasyonunu çalıştıran ana modül
├── tcmb_macro.py              # TCMB EVDS sisteminden makroekonomik verileri çeken modül
└── keys.py                    # (Git'ten gizlenmiştir) API anahtarlarının tutulduğu güvenli dosya
\`\`\`

## ⚙️ Kurulum ve Çalıştırma

**1. Gereksinimler**
Sistemi çalıştırmak için aşağıdaki Python kütüphanelerinin kurulu olması gerekmektedir:
\`\`\`bash
pip install pandas requests google-genai pyTelegramBotAPI
\`\`\`

**2. Ortam Değişkenleri (API Keys)**
Projenin kök dizininde bir `keys.py` dosyası oluşturun ve aşağıdaki değişkenleri kendi API bilgilerinizle doldurun *(Güvenlik için bu dosyayı asla GitHub'a yüklemeyin)*:
\`\`\`python
# keys.py
gemini_api_key = "Sizin_Google_Gemini_API_Anahtarınız"
telegram_bot_token = "Sizin_Telegram_Bot_Tokenınız"
evds_api_key = "Sizin_TCMB_EVDS_API_Anahtarınız"
\`\`\`

**3. Başlatma**
Telegram AI Asistanını aktif hale getirmek için terminalde aşağıdaki komutu çalıştırın:
\`\`\`bash
python ai_strategist.py
\`\`\`
*Bot çalışmaya başladığında konsolda `🤖 Remax Now AI Telegram Botu Çalışıyor...` mesajını göreceksiniz. Ardından Telegram üzerinden botunuza `/start` yazarak etkileşime geçebilirsiniz.*

## 🚀 Gelecek Vizyonu

Bu proje bir Konsept Kanıtlama (Proof of Concept) niteliğindedir. Sistemin şirket veritabanına tam entegre edilmesi durumunda:
1.  **Canlı Veri Akışı:** Sentetik veriler yerine şirketin CRM yazılımından çekilen anlık ilan verilerinin analiz edilmesi.
2.  **Müşteri Eşleştirme Sistemi:** "Hangi müşteri tipine, hangi ilan SMS olarak atılmalı?" sorusunun otomatik olarak yanıtlanması.
3.  **Makro-Mikro Sentezi:** TCMB verileri ile lokal portföy verilerinin birleştirilerek "Gelecek 6 Ay İçin Bölgesel Fiyat Tahminlemesi" yapılması.
