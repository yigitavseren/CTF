# 🛡️ Siber Operasyon Günlüğü: Linux Temelleri (Bölüm 2)

Bu dokümanda, Linux sistemlerinde yetki yükseltme, dosya izinleri yönetimi, uzaktan bağlantı (SSH) ve işletim sisteminin kök hiyerarşisi üzerine kritik notlar yer almaktadır.

## 1. Kimlik ve Yetki Yönetimi (Privilege Escalation)
* **`sudo`** *(SuperUser DO)*: Normal bir kullanıcıyken, sadece yazılan tek bir komutu "Root" (Süper Yönetici) yetkisiyle çalıştırmamızı sağlar. Sistemin kapılarını bir kereliğine açar.
* **`su`** *(Switch User)*: Sistemde tamamen başka bir kullanıcının kimliğine bürünmeyi sağlar. `sudo su` kombosu ile kalıcı olarak Root kullanıcısına geçiş yapılır. (Çıkış yapmak için `exit` kullanılır).

## 2. Dosya İzinleri ve Sahiplik
* **`chmod`**: Dosya veya klasörlerin okuma (r), yazma (w) ve çalıştırma (x) izinlerini manipüle eder. 
  * *Güvenli Kullanım:* `chmod +x script.sh` (Sadece çalıştırma izni ekler)
  * *Tehlikeli Kullanım:* `chmod 777 dosya.txt` (Tüm okuma/yazma/çalıştırma yetkilerini herkese sonuna kadar açar. Siber güvenlikte zafiyet yaratır, dikkatli kullanılmalıdır.)
* **`chown`** *(Change Owner)*: Bir dosyanın veya dizinin yasal sahibini (owner) başka bir kullanıcıya devretmek/değiştirmek için kullanılır.

## 3. Uzaktan Sızma ve Bağlantı
* **`ssh`** *(Secure Shell)*: Uzaktaki bir Linux sunucusuna terminal üzerinden şifreli ve güvenli bir şekilde sızmayı/bağlanmayı sağlar. 
  * *Komut Formatı:* `ssh kullanici_adi@hedef_ip_adresi`

## 4. Sistem Hiyerarşisi (Kritik Hedef Dizinler)
* **`/` (Root Dizini)**: Dosya sisteminin en tepe noktasıdır, her şey buradan dallanır.
* **`/etc`**: Sistemin beynidir. Tüm yapılandırma ve ayar dosyaları (örneğin kullanıcı şifrelerinin hash'lenmiş hali olan `shadow` dosyası) burada saklanır. Siber saldırılarda ilk hedeflerden biridir.
* **`/var`**: Sistem loglarının (kayıtlarının) tutulduğu dizindir. İz sürmek veya kendi izini silmek isteyen bir güvenlik uzmanı buraya odaklanır.
* **`/tmp`**: Geçici dosyaların tutulduğu dizindir. Sistem yeniden başlatıldığında içi temizlenir. Hızlı çalıştırılacak scriptler veya zararlı yazılımlar (malware) genellikle ilk buraya indirilir.
* **`/bin`**: Terminalde kullandığımız `ls`, `cat`, `rm` gibi temel sistem komutlarının çalıştırılabilir asıl dosyalarının bulunduğu yerdir.

## 5. Mühendislik ve Kılavuz Komutları
* **`man`** *(Manual)*: İşletim sisteminin dahili kullanım kılavuzudur. Bir komutun tam olarak ne işe yaradığını ve hangi parametreleri aldığını gösterir. (Örn: `man grep`). Kılavuzdan çıkmak için `q` tuşu kullanılır.
