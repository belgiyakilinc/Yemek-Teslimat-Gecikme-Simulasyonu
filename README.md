# Yemek Teslimat Süresi ve Gecikme Simülasyonu (Monte Carlo)

Bu proje, yemek teslimat sürelerini etkileyen faktörleri (mesafe, trafik yoğunluğu, hava durumu vb.) incelemek ve olasılıksal simülasyon yöntemleri kullanarak olası gecikme senaryolarını analiz etmek amacıyla Python ile hazırlanmıştır.

## 📌 Problem ve Amaç
Kargo ve yemek teslimat süreçlerinde süreler birçok rassal faktörden etkilenmektedir. Bu çalışmanın temel amacı:
* Gerçek bir teslimat veri setini analiz ederek mevcut teslimat süresi dağılımlarını belirlemek.
* **Monte Carlo Simülasyonu** kullanarak rastgele senaryolar (farklı mesafe ve trafik yoğunlukları) oluşturmak.
* Lojistik gecikmelerini analiz edip, gerçek veriler ile simüle edilen verilerin performans karşılaştırmasını yapmaktır.

## 📊 Veri Seti
Çalışmada `Food_Delivery_Times.csv` veri seti kullanılmıştır. Analize dahil edilen temel değişkenler:
* **Sürekli Değişkenler:** Mesafe (Distance_km), Teslimat Süresi (Delivery_Time_min)
* **Kategorik Değişkenler:** Trafik Yoğunluğu (Traffic_Level), Hava Durumu (Weather), Restoran Tipi
* *Not: Eksik veya hatalı veriler ön işleme aşamasında temizlenmiştir.*

## 🛠 Kullanılan Yöntemler ve Kütüphaneler
Projede Python programlama dili ve veri bilimi kütüphaneleri (`pandas`, `numpy`, `matplotlib`, `seaborn`) kullanılmıştır. Geliştirilen modelin temel aşamaları:
1. **Keşifsel Veri Analizi (EDA):** Teslimat sürelerinin temel istatistikleri ve yoğunluk dağılımlarının görselleştirilmesi.
2. **Olasılık Dağılımları:** Mesafenin Normal Dağılım ve Gamma dağılımı gibi istatistiksel dağılımlara oturtulması.
3. **Monte Carlo Simülasyonu:** 1000 farklı sipariş için rassal mesafe ve ağırlıklandırılmış trafik yoğunluğu (Low, Medium, High, Jam) olasılıklarıyla tahmini teslimat sürelerinin hesaplanması.
4. **Doğrulama (Validation):** Simülasyon sonucunda elde edilen ortalama teslimat süreleri ile gerçek veri setindeki ortalamaların karşılaştırılarak modelin geçerliliğinin test edilmesi.

## 🚀 Öne Çıkan Bulgular
* Trafik durumunun ('Jam', 'High' vb.) teslimat süresi üzerinde lineer olmayan bir artış (çarpan) yarattığı modellenmiştir.
* Simülasyon sonucunda üretilen ortalama teslimat süresi, gerçek verideki teslimat süresine oldukça yakınsayarak modelin pratik lojistik planlamalarında kullanılabileceğini göstermiştir.
* Gecikmelerin eşik değerleri (örn: 30 dakikayı aşan siparişler) belirlenerek sistemin dar boğazları tespit edilebilir.

## 💻 Kullanım
Projenin tüm adımları, kodları ve çıktıları `simulasyon.ipynb` (Jupyter Notebook) dosyasında adım adım açıklanmıştır. İlgili kütüphaneleri yükledikten sonra (örn: `pip install pandas numpy matplotlib seaborn`) notebook'u kendi lokal ortamınızda çalıştırabilirsiniz.
