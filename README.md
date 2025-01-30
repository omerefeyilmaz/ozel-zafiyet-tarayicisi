Ağ Taraması ve Zafiyet Testi API ProjesiProjenin Amacı ve Genel İşleyişi:

Bu proje, bir hedef IP adresine karşı port taramaları ve güvenlik zafiyetlerinin kontrolünü sağlayan bir API sunmaktadır. Kullanıcılar, belirli bir IP adresine karşı port taraması yaparak açık ve kapalı portlar hakkında bilgi alabilir ve aynı zamanda belirli zafiyetleri tespit etmek için bir zafiyet veritabanı üzerinden tarama yapabilir. Bu API, güvenlik analistleri ve ağ yöneticileri için faydalı olabilir.

Ana İşleyiş:
Port Tarama: Verilen IP adresi üzerinde belirli bir port aralığında tarama yapar ve açık/kapalı durumunu bildirir.
Zafiyet Tarama: Zafiyet veritabanı kullanılarak tespit edilen güvenlik açıkları ve risk seviyesi hakkında bilgi verir.
API Yapısı: API, tarama sonuçlarını JSON formatında döner ve kullanıcıya başarılı ya da başarısız durumu bildirir.


Bu projede kullanılan ana kütüphaneler:

Flask (Web framework)
POSTMAN (API istemcisi, isteklere veri gönderme)

Flask ve POSTMAN Yükleme:
Projenin çalışabilmesi için gerekli kütüphaneleri yüklemek için aşağıdaki komutu kullanabilirsiniz:

bash
pip install flask requests
Gerekli Araçlar ve Kurulum Gereksinimleri
Python 3.6+ - Python, Flask framework'ü ile çalışmak için gereklidir.

Flask Kütüphanesi - Web sunucusunu çalıştırmak için kullanılır.

POSTMAN - API ile iletişim kurmak için kullanılır (test için).

Kurulum:
Python 3.6 veya daha yeni bir sürümünün yüklü olduğundan emin olun.
Flask yüklemek için:
bash
pip install flask
Proje dosyasını bir dizine indirip, app.py dosyasını çalıştırarak Flask sunucusunu başlatın.
POSTMAN yüklemek için:
https://www.postman.com/downloads/

Zorunlu Çalışma Parametreleri
API'yi kullanabilmek için gerekli olan parametreler şunlardır:

hedef_ip (str): Tarama yapılacak IP adresi.

port_araligi (str): Tarama yapılacak port aralığı (örn. 80-443).

Örnek JSON İsteği:
json
{
    "hedef_ip": "192.168.1.100",
    "port_araligi": "80-443"
}
Opsiyonel Parametreler ve Kullanımları
Bu parametreler isteğe bağlı olup, varsayılan değerlerle çalıştırılabilir. Ancak, isteğe bağlı parametreleri belirtmek, taramanın özelleştirilmesine olanak sağlar.

zafiyet_veritabani (str, opsiyonel): Kullanılacak zafiyet veritabanı. Varsayılan: "CVE".

Değerler: "CVE" veya başka bir zafiyet veritabanı adı (veritabanı entegrasyonu yapılabilir).
ozelleştirilmis_modul (bool, opsiyonel): Özelleştirilmiş bir modül kullanılıp kullanılmayacağını belirtir. Varsayılan: False.

detay_seviyesi (str, opsiyonel): Taramanın detay seviyesini belirtir. Varsayılan: "orta".

Değerler: "düşük", "orta", "yüksek".
Örnek JSON İsteği (Opsiyonel Parametrelerle):
json
{
    "hedef_ip": "192.168.1.100",
    "port_araligi": "80-443",
    "zafiyet_veritabani": "CVE",
    "ozelleştirilmis_modul": false,
    "detay_seviyesi": "yüksek"
}
Kurulum ve Çalıştırma Talimatları
Proje Dosyasını İndirin: Projeyi GitHub'dan indirerek bir dizine kaydedin.

Gerekli Kütüphaneleri Yükleyin: Flask ve Requests kütüphanelerini yüklemek için aşağıdaki komutu kullanın:

bash:
pip install flask requests
Flask Sunucusunu Başlatın: Flask uygulamasını başlatmak için terminal veya komut istemcisine şu komutu yazın:

bash:
python app.py
Uygulama çalışmaya başladığında, terminalde şu mesajı görmelisiniz:


CMD:
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
API'yi Test Edin: Postman veya bir API istemcisi kullanarak şu URL'ye POST isteği gönderebilirsiniz:

POSTMAN:
http://127.0.0.1:5000/tarama
İstek verisi:

json
{
    "hedef_ip": "192.168.1.100",
    "port_araligi": "80-443"
}
Sonuçları Görüntüleyin: API isteği başarılı bir şekilde tamamlandığında, JSON formatında tarama sonucu ve olası zafiyet bilgileri size geri dönecektir.
