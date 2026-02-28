# 🛡️ Siber Operasyon Günlüğü: Linux Temelleri (Bölüm 1)

Bu doküman, siber güvenlik laboratuvarlarında ve Linux sunucularında keşif, dosya manipülasyonu ve sistem analizi yaparken kullandığım temel operasyonel komutları içermektedir.

## 1. Sisteme Sızma ve Keşif (Reconnaissance)
* **`whoami`**: Sisteme hangi yetkiyle/kullanıcıyla giriş yaptığımızı teyit eder.
* **`pwd`**: *(Print Working Directory)* Sunucu hiyerarşisinde tam olarak hangi dizinin (klasörün) içinde pusuya yattığımızı gösterir.
* **`ls`**: Bulunduğumuz dizindeki tüm dosya ve klasörlerin haritasını çıkarır.
* **`-R` (Recursive)**: Özyinelemeli arama parametresidir. Örneğin `ls -R` kullanıldığında, sadece bulunduğumuz klasörü değil, iç içe geçmiş tüm alt klasörleri de en dibine kadar deşifre eder.
* **`cd`**: *(Change Directory)* Hedef klasörler arasında gezinmemizi ve sistemin derinliklerine inmemizi sağlar.

## 2. Dosya Okuma ve Veri Manipülasyonu
* **`cat`**: Hedef dosyanın içeriğini (örneğin yapılandırma dosyaları veya gizli bayraklar) anında terminal ekranına basar.
* **`echo`**: Ekrana spesifik bir metin yazdırmak veya dışarıdan dosyalara veri enjekte etmek için kullanılır.

## 3. Sistemde İz Sürme ve Analiz
* **`find`**: Sunucu içinde kaybolmuş veya gizlenmiş dosyaları ismine, boyutuna, uzantısına veya yetkilerine göre milimetrik olarak avlamak için kullanılır.
* **`grep`**: Siber güvenlikteki en güçlü arama motorudur. Binlerce satırlık log dosyalarının veya kodların içinde sadece aradığımız spesifik kelimeyi (örn: hatalar, şifreler) süzüp önümüze getirir.

## 4. İleri Düzey Operatörler (Terminal Zincirleri)
* **`&`**: Bir komutun sonuna eklendiğinde o işlemi arka plana (background) atar. Böylece işlem sunucuyu yormaya devam ederken biz terminali kullanmaya devam edebiliriz.
* **`&&`**: Mantıksal VE operatörüdür. Komutları birbirine zincirler. *"Birinci komut BAŞARILI olursa, hiç beklemeden ikinci komutu ateşle"* anlamına gelir. (Örn: `cd klasor && ls`)
* **`>`**: Bir komutun çıktısını alır ve bir dosyanın içine yazar. **Dikkat:** Dosyanın eski içeriğini acımasızca siler ve tamamen üstüne yazar (Overwrite).
* **`>>`**: Çıktıyı dosyanın sonuna **ekler** (Append). Eski veriyi korur, sistem logları tutarken veri kaybını önlemek için hayat kurtarır.
