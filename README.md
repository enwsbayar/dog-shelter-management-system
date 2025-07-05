# Köpek Barınağı Yönetim Sistemi 🐕

Bu proje, köpek barınaklarının yönetimini kolaylaştırmak için geliştirilmiş web tabanlı bir uygulamadır. Flask framework'ü kullanılarak geliştirilmiş ve SQLite veritabanı ile entegre edilmiştir.

## 🚀 Özellikler

### Genel Kullanıcı Özellikleri
- **Hayvan Listesi**: Tüm barınaktaki hayvanları görüntüleme
- **Barınak Bilgileri**: Barınak detaylarını görüntüleme
- **ID ile Arama**: Hayvan ve barınak ID'si ile arama yapma
- **Personel Bilgileri**: Barınak personellerini görüntüleme

### Barınak Sahibi Özellikleri
- **Güvenli Giriş**: Barınak ID'si ile şifre kontrolü
- **Hayvan Yönetimi**: Yeni hayvan ekleme ve mevcut hayvanları listeleme
- **Personel Yönetimi**: Yeni personel ekleme ve mevcut personeli listeleme
- **Muayene Takibi**: Tedavi edilen hayvanların muayene kayıtlarını görüntüleme

## 📁 Proje Yapısı

```
dog-shelter-management/
├── Data/
│   └── data.xlsx              # Ana veri dosyası
├── static/                    # CSS
├── templates/                 # HTML şablonları
├── database.py               # Veritabanı bağlantı scripti
├── main.ipynb               # Ana Flask uygulaması
├── randomDataGenerator.py    # Test verisi üretici
├── veritabani.db            # SQLite veritabanı
└── README.md                # Bu dosya
```

## 🛠️ Kurulum

### Gereksinimler
```bash
pip install pandas
pip install pandasql
pip install flask
pip install openpyxl
pip install sqlite3
pip install webbrowser
```

### Adımlar
1. **Repoyu klonlayın**
   ```bash
   git clone https://github.com/enwsbayar/dog-shelter-management-system.git
   cd dog-shelter-management-system
   ```

2. **Bağımlılıkları yükleyin**
   ```bash
   pip install -r requirements.txt
   ```

3. **Test verisini oluşturun**
   ```bash
   python randomDataGenerator.py
   ```

4. **Veritabanını başlatın**
   ```bash
   python database.py
   ```

5. **Uygulamayı çalıştırın**
   ```bash
   python main.ipynb
   ```

6. **Tarayıcınızda açın**
   ```
   http://127.0.0.1:5000
   ```

## 📊 Veri Yapısı

### Hayvan Tablosu
- **HayvanId**: Benzersiz hayvan kimliği
- **Ad**: Hayvan adı
- **Tur**: Hayvan türü/ırkı
- **Cinsiyet**: Erkek/Dişi
- **Yas**: Yaş bilgisi
- **SaglikDurumu**: Sağlıklı/Hasta/Tedavi Ediliyor
- **GelisTarihi**: Barınağa geliş tarihi
- **BarinakId**: Bulunduğu barınak ID'si

### Barınak Tablosu
- **BarinakId**: Benzersiz barınak kimliği
- **Ad**: Barınak adı
- **Konum**: Barınak konumu
- **Kapasite**: Maksimum kapasite
- **Sifre**: Barınak giriş şifresi

### Personel Tablosu
- **PersonelId**: Benzersiz personel kimliği
- **Ad**: Personel adı
- **Soyad**: Personel soyadı
- **Gorev**: Görevi (Veteriner, Bakıcı, vb.)
- **CalismaTarihi**: İşe başlama tarihi
- **BarinakId**: Çalıştığı barınak ID'si

### Veteriner Tablosu
- **VetId**: Veteriner ID'si (PersonelId ile bağlantılı)
- **Ad**: Veteriner adı
- **Soyad**: Veteriner soyadı
- **Uzmanlik**: Uzmanlık alanı

### Muayene Tablosu
- **MuayeneId**: Benzersiz muayene kimliği
- **HayvanId**: Muayene edilen hayvan ID'si
- **VeterinerId**: Muayene yapan veteriner ID'si
- **Tarih**: Muayene tarihi
- **Teshis**: Konulan teşhis
- **Tedavi**: Uygulanan tedavi

## 🔧 Kullanım

### Barınak Sahibi Girişi
1. Ana sayfadan "Barınak Sahibi Girişi"ni seçin
2. Barınak ID'nizi girin (Şifre olarak da aynı ID kullanılır)
3. Başarılı girişten sonra yönetim paneline erişebilirsiniz

### Yeni Hayvan Ekleme
1. Barınak sahibi panelinden "Hayvan Ekle"yi seçin
2. Hayvan bilgilerini doldurun
3. Sağlık durumu "Tedavi Ediliyor" seçilirse otomatik muayene kaydı oluşturulur

### Yeni Personel Ekleme
1. Barınak sahibi panelinden "Personel Ekle"yi seçin
2. Personel bilgilerini doldurun
3. Görev "Veteriner" seçilirse otomatik veteriner kaydı oluşturulur

## 🎯 Test Verisi

`randomDataGenerator.py` scripti ile otomatik test verisi oluşturabilirsiniz:
- 28 barınak
- 500 hayvan
- Her barınak için 5 personel (Veteriner, Bakıcı, Temizlik Görevlisi, Yönetici, Gönüllü)
- Tedavi edilen hayvanlar için muayene kayıtları

## 📝 Geliştirici Notları

### Kullanılanlar
- **Backend**: Flask (Python)
- **Veritabanı**: SQLite
- **Veri İşleme**: Pandas, PandasQL
- **Excel İşlemleri**: OpenPyXL
- **Frontend**: HTML, CSS

### Önemli Dosyalar
- `main.ipynb`: Ana Flask uygulaması ve route tanımları
- `database.py`: Excel verilerini SQLite'a aktarma
- `randomDataGenerator.py`: Test verisi üretimi
- `Data/data.xlsx`: Tüm veri şeetlerini içeren Excel dosyası

**Not**: Bu sistem eğitim amaçlı geliştirilmiştir. Gerçek barınak ortamında kullanım öncesinde güvenlik ve performans testleri yapılması önerilir.
