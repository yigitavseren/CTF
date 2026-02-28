# 🛡️ Siber Operasyon Günlüğü: Linux Temelleri (Bölüm 3)

Bu doküman, sistemdeki süreçleri (process) yönetme, ağ üzerinden dosya transferi, servis kontrolü, görev otomasyonu ve taktiksel terminal araçları gibi ileri düzey Linux operasyonlarını içermektedir.

## 1. Süreç (Process) Yönetimi ve Avcılığı
* **`top`**: Sistemde anlık olarak çalışan tüm işlemleri, CPU ve RAM tüketimlerini canlı olarak listeler. İşletim sisteminin görev yöneticisidir. Ekranda akıp giden bu listeden çıkmak için `q` tuşu kullanılır.
* **`ps`** *(Process Status)*: Çalışan süreçlerin anlık fotoğrafını (snapshot) çeker. Genellikle `ps aux` parametreleriyle kullanılarak arka planda gizlenen her şey deşifre edilir.
* **`kill`**: Kontrolden çıkan veya durdurulması gereken bir sürecin fişini çekmek için kullanılır. Her sürecin bir kimlik numarası (PID) vardır. İşlemi acımasızca sonlandırmak için `kill -9 <PID>` balyozu fırlatılır.

## 2. Ağ Üzerinden Dosya İndirme ve Transfer
* **`wget`**: İnternetteki veya başka bir sunucudaki bir dosyayı (örneğin bir zafiyet sömürücüyü veya siber güvenlik aracını) terminal üzerinden doğrudan bulunduğumuz dizine çekmek için kullanılır.
* **`scp`** *(Secure Copy)*: SSH protokolünün gücünü kullanarak, kendi bilgisayarımız ile uzaktaki hedef makine arasında şifreli ve güvenli dosya transferi yapmamızı sağlar.

## 3. Servisler ve Zamanlanmış Görevler (Otomasyon)
* **`systemctl`**: İşletim sisteminin arka plan servislerini (örneğin bir web sunucusunu veya ağ hizmetini) başlatmak, durdurmak veya durumunu denetlemek için kullanılır. (Örn: `systemctl start apache2`, `systemctl status ssh`).
* **`crontab`**: Zamanlanmış görevler (Cron jobs) listesidir. Siber güvenlik operasyonlarında, sisteme sızdıktan sonra kalıcılık (persistence) sağlamak için "her saat başı bana bağlantı yolla" gibi otomatik çalışacak arka plan emirleri buraya yazılır.

## 4. Taktiksel Araçlar ve İşlem Yönetimi
* **`vim` / `vi`**: Gelişmiş, terminal tabanlı efsanevi metin editörü. Komut modunda çalışır. (Acil çıkış kodu: `:q!`).
* **`python3 -m http.server`**: Bulunulan dizini saniyeler içinde geçici bir web sunucusuna dönüştürür. Hedef makineye sızdıktan sonra dosya (payload) transferi yapmak için ağdaki en pratik yöntemdir.
* **`Ctrl + Z`**: Terminali kilitleyen uzun soluklu bir işlemi dondurup arka plana atar.
* **`fg` / `bg`**: Arka plana atılan işlemleri tekrar öne (foreground) çağırmak veya arka planda (background) sessizce çalışmaya devam etmelerini sağlamak için kullanılır.
