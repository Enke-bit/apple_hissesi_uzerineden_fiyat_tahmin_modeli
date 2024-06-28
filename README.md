# Apple Hisse Senedi Fiyat Tahmini LSTM ile
Bu proje, Apple Inc. hisse senedi fiyatlarını Long Short-Term Memory (LSTM) modeli kullanarak tahmin etmeyi amaçlamaktadır. Veri seti günlük hisse senedi fiyatlarını içermekte olup, model veri setindeki son tarihten itibaren 5 yıllık hisse senedi fiyatlarını tahmin etmek için eğitilmiştir.

## İçindekiler
- Giriş
- Veri Seti
- Ön İşleme
- Model Mimarisi
- Eğitim
- Sonuçlar
- Gelecek Tahminler
- Kullanım
- Bağımlılıklar
- Giriş

Bu proje, Apple Inc. hisse senedi fiyatlarının gelecekteki seyrini tahmin etmek amacıyla LSTM modelini kullanır. 
LSTM modelleri, zaman serisi verilerindeki uzun dönemli bağımlılıkları öğrenmede etkilidir ve bu nedenle finansal veri tahminlerinde yaygın olarak kullanılır.

## Veri Seti
Kullanılan veri seti, Apple Inc. hisse senetlerinin günlük açılış, yüksek, düşük, kapanış fiyatlarını ve işlem hacimlerini içermektedir. Veri seti AAPL_daily_update.csv dosyasından yüklenmiştir.

## Ön İşleme
Veri ön işleme adımları şunlardır:

- Tarih sütununun datetime formatına dönüştürülmesi.
- Tarih sütununun indeks olarak ayarlanması.
- Kapanış fiyatlarının ölçeklendirilmesi (normalize edilmesi).

## Model Mimarisi
Model, iki LSTM katmanı ve iki Dropout katmanından oluşmaktadır:

- İlk LSTM katmanı 50 birim ve return_sequences=True
- Dropout katmanı (0.2)
- İkinci LSTM katmanı 50 birim
- Dropout katmanı (0.2)
- Dense katmanı (1 birim)
- Model Adam optimizasyon algoritması ile derlenmiş ve kayıp fonksiyonu olarak Mean Squared Error (MSE) kullanılmıştır.

## Eğitim
Model, eğitim verileri ile 50 epoch boyunca eğitilmiştir. Eğitim ve doğrulama kayıpları görselleştirilmiş ve model performansı değerlendirilmiştir.

## Sonuçlar
Modelin tahminleri, test verileri üzerindeki gerçek değerler ile karşılaştırılarak görselleştirilmiştir.

## Gelecek Tahminler
Eğitilmiş model, veri setindeki son tarihten itibaren 5 yıl boyunca günlük hisse senedi fiyatlarını tahmin etmek için kullanılmıştır. Tahminler ve gelecekteki tarihler görselleştirilmiştir.

## Kullanım
Proje kodunu çalıştırmak için aşağıdaki adımları izleyin:

- Gerekli kütüphaneleri yükleyin.
- AAPL_daily_update.csv dosyasını aynı dizine yerleştirin.
- main.py dosyasını çalıştırın.
- Bağımlılıklar
- Python 3.x
- pandas
- numpy
- matplotlib
- scikit-learn
- tensorflow

## Yazar
Bu proje İbrahim Püsküllü tarafından oluşturulmuştur.

## Lisans için License.txt dosyasında detaylı yazılmıştır.
