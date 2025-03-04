# Titanic Veri Analizi Raporu

##  Giriş
Titanic kazası, tarihin en trajik deniz felaketlerinden biri olarak bilinir. Bu çalışma, yolcuların hayatta kalma oranlarını etkileyen faktörleri anlamak için Titanic veri setini analiz etmeyi amaçlamaktadır. Çalışma kapsamında veri temizleme, analiz ve görselleştirme adımları uygulanmıştır.

##  Veri Temizleme
Veri setinde eksik ve uç değerlerin olduğu gözlemlendi. Bu veriler aşağıdaki yöntemlerle temizlendi:

- **Yaş sütunundaki eksik değerler** → Medyan ile dolduruldu.
- **Embarked sütunundaki eksik değerler** → En sık görülen değer (mod) ile dolduruldu.
- **Fare sütunundaki uç değerler** → IQR yöntemi kullanılarak temizlendi.
- **Cinsiyet sütunu** → Sayısal hale getirildi (Kadın: 0, Erkek: 1).
- **Embarked sütunu** → One-hot encoding yöntemiyle dönüştürüldü.
- **Aile büyüklüğü sütunu** oluşturularak SibSp ve Parch sütunları birleştirildi.

##  Analiz Sonuçları

### 📌 Yaş Dağılımı
- Yolcuların büyük kısmı **20-40 yaş** aralığında bulunuyor.
- **En sık görülen yaş 28**, eksik değerlerin medyan ile doldurulmasının etkisiyle öne çıkmış olabilir.
- **Bebekler ve yaşlı yolcular oldukça az.**  

### 📌 Fare Ücret Dağılımı
- Titanic yolcularının büyük kısmı düşük ücretli bilet satın almış.
- **Bazı biletler çok pahalı**, bu da muhtemelen 1. sınıf yolculara ait.
- Log dönüşümü, **uç değerleri daha iyi analiz etmemizi sağladı.**  

### 📌 Cinsiyete Göre Hayatta Kalma Oranı
- **Kadınların hayatta kalma oranı (%75), erkeklere göre çok daha yüksek (%20).**  
- Bu sonuç, **"Önce kadınlar ve çocuklar" kuralını doğruluyor.**  

### 📌 Pclass’a Göre Hayatta Kalma Oranı
- **1. sınıfta yolculuk edenler %65 oranında hayatta kaldı.**  
- **3. sınıftakiler en düşük hayatta kalma oranına sahip (%25).**  
- **Sınıfsal farkların büyük rol oynadığı görülüyor.**  

### 📌 Aile Büyüklüğüne Göre Hayatta Kalma Oranı
- **Tek başına seyahat eden yolcuların hayatta kalma oranı daha yüksek.**  
- **5 veya daha fazla aile üyesi olan yolcuların hayatta kalma oranı düşüktü.**  
- **Büyük aileler için kurtulma şansı daha az olabilir, çünkü gruplar halinde kaçmak daha zor.**  

##  Sonuç
Bu analiz, Titanic kazasında hayatta kalma oranını etkileyen ana faktörleri göstermektedir:

- **Kadın yolcuların hayatta kalma şansı daha yüksektir.**
- **1. sınıf yolcuların hayatta kalma oranı daha yüksektir.**
- **Tek başına seyahat eden yolcular daha avantajlıdır.**
