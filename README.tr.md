## Türkçe Metinler İçin Özetleme API

---

**For english, go below.** Bu API verilen metni özetleyen, Türkçe için özelleştirilmiş bir özetleyicidir. Servisi kullanmak için token alınması gerekli olup geçerlilik süresi **1 saattir**. Her login yeni bir token yaratacaktır.

### Kayıt Ol
##### Gönderilecek İstek

	HTTP POST
	URL: http://ozetle.htkibar.com/register
    {
	    "mail": "example_mail@example.com",
	    "password": "example_password"
    }

##### Alınacak Cevap

	HTTP 200 OK
    {
	    "message": "You have successfully registered. You can now login."
    }

### Giriş Yap
##### Gönderilecek İstek

	HTTP POST
	URL: http://ozetle.htkibar.com/login
    {
	    "mail": "example_mail@example.com",
	    "password": "example_password"
    }

##### Alınacak Cevap

    HTTP 200 OK
    {
	    "token": "API TOKENINIZ"
    }

### Token Doğrulama
##### Gönderilecek İstek

		HTTP GET
    	URL: http://ozetle.htkibar.com/API TOKENINIZ

##### Alınacak Cevap

		HTTP 200 OK
		{
			"isValid": true
		}
### Özetleyici
##### Gönderilecek İstek
		
		HTTP POST
		URL: http://ozetle.htkibar.com/summarize
		{
			"text": "Özetlenecek metin.",
			"clusterCount": "Özetlenen metnin değerinin belirler ne kadar yüksek o kadar uzun. Tırnaksız sayı olması gerekmektedir.",
			"token": "API TOKENINIZ"
		}
##### Alınacak Cevap
		
		HTTP 200 OK
		{
			"summary": "Özetlenmiş metin."
		}
