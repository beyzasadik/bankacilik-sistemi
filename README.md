# bankacilik-sistemi

Basit bir bankacılık işlem takip sistemi geliştirecek. Bu sistemde müşteri işlemleri (transactions), terminaller ve müşteri bilgileri olacak.
🛠️ 1. Veritabanı Tasarımı
Aşağıdaki 4 tabloyu içeren ilişkisel bir veritabanı tasarlanacak:
Customer tablosu
customer_id (PK)
company_name (Müşteri adı)
citizen_number (valid kontrolü olmalı)
tax_number
email (E-posta)
phone_number (Telefon)
create_date (Kayıt tarihi)
update_date
status (Aktif/Pasif durumu)
terminal tablosu
customer_id (FK, customer tablosuna bağlı)
city_code (Bulunduğu yer)
status (Aktif/Pasif)
create_date (Kayıt tarihi)
update_date

transaction tablosu
transaction_id (PK)
customer_id (FK, customer tablosuna bağlı)
terminal_id (FK, terminal tablosuna bağlı)
amount (İşlem tutarı)
commission (işlemden alınacak komisyon)
transaction_type (Ödeme, İade vb.)
create_date (İşlem tarihi)
update_date
transaction_history tablosu (İşlem Geçmişi)
Güncellenen transaction kayıtlarını tutar.
Trigger kullanılarak transaction değiştiğinde buraya kayıt atılacak.
Her bir kolon değişiminde güncelleme ya da silme durumunda kayıt atılmalı
 
📌 2. Store Procedure ile Otomatik Veri Ekleme
Random veri oluşturup ekleyen bir Stored Procedure yazılacak. (Farklı amaç için de procedure ler yazılabilir)
Her müşterinin rastgele 1-3 terminali olacak.
Her terminalde rastgele 10-50 işlem oluşturulacak.
İşlemler farklı türlerde olacak (Ödeme, İade vb.)
İşlem tutarları 50-5000 arasında rastgele atanacak.

Hakim olduğun bir programlama dili ile  aşağıdaki sorguların cevaplarını JSON formatta dönen servisler geliştirilecek:
•	http://localhost:8080/customer şeklinde sorguladığımızda customer listesini dönmesi gibi aşağıdaki işlemler için de sonuçları verecek methodlar eklenmeli.
•	En yüksek işlem tutarına sahip müşterinin bilgilerini getir
•	fMüşterilerin ortalama işlem tutarlarını listele
•	En az işlem yapan müşterinin terminal bilgilerini getir
•	En çok işlem yapılan terminalin 
