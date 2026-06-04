# Sema-elik
Envanter Takip Sistemi
# Tekstil Envanter Yönetim Sistemi (Mobil)

Bu proje, Kocaeli Üniversitesi Bilişim Sistemleri Mühendisliği Bölümü TBL331: Veritabanı Yönetim Sistemleri dersi kapsamında geliştirilmiş bir dönem projesidir. 

## Proje Özeti & Genel Yapı
Tekstil ürünlerinin (renk, beden ve kumaş tipi detaylarıyla) stok giriş-çıkışlarını takip etmeyi sağlayan, mobil tabanlı bir envanter yönetim sistemidir. Sistem; verilerin bütünlüğünü sağlayan ilişkisel bir SQL veritabanı, bu veritabanı ile güvenli haberleşmeyi sağlayan bir arka plan API servisi ve kullanıcı etkileşimini kolaylaştıran bir mobil arayüzden oluşmaktadır. Öğeler maddeler halinde, kısa ve net cümlelerle tasarlanmıştır

## Problem Tanımı
Tekstil sektöründe aynı ürünün farklı beden, renk ve kumaş varyasyonlarının bulunması, geleneksel yöntemlerle stok takibini zorlaştırmakta ve manuel kayıt hatalarına yol açmaktadır. Bu karmaşıklığı ortadan kaldırmak için, verilerin merkezi bir veritabanında güvenle tutulduğu, anlık olarak erişilebilen ve kullanıcı dostu bir mobil çözüme ihtiyaç duyulmuştur.

## Yapılan Araştırmalar
Mobil uygulamaların doğrudan veritabanına bağlanmasının güvenlik zafiyetleri ve performans kayıpları yaratacağı tespit edilmiş, çözüm olarak aracı bir Web API katmanı kullanılmasına karar verilmiştir.
Veritabanı tarafında ürün varyasyon karmaşasını önlemek adına 5N (Normalizasyon) kurallarına uygun yapısal araştırmalar yapılmış ve tablolar buna göre ayrıştırılmıştır.
Mobil ekranda kullanım kolaylığını sağlamak amacıyla göz yormayan, pastel mavi ve pastel yeşil tonlarında modern bir UI/UX deneyimi araştırılıp projeye entegre edilmiştir.

## Yazılım Mimarisi ve Geliştirme Ortamı
Projenin kodlanması aşamasında 3 katmanlı modern bir mimari tercih edilmiştir. Geliştirme ortamı ve kullanılan teknolojiler şu şekildedir:
* **Veritabanı Katmanı:** Microsoft SQL Server 2022
* **Backend (Aracı Katman):** ASP.NET Core Web API (C#) & Entity Framework Core
* **Frontend (Mobil Kullanıcı Arayüzü):** .NET MAUI (XAML & C#)
* **Geliştirme Aracı (IDE):** Visual Studio 2022

## Projenin Yüklenmesi ve Çalıştırılması
Projenin test edilmesi ve çalışır duruma getirilmesi için aşağıdaki adımlar izlenmelidir:
1.  GitHub üzerinden proje dosyaları bilgisayara indirilir.
2.  `grupno_sql_betikleri.txt` dosyası içindeki SQL kodları SQL Server Management Studio (SSMS) üzerinde çalıştırılır. Bu işlem sayesinde tablolar, Primary/Foreign Key ilişkileri, Check/Unique kısıtlayıcıları ve minimum 10 adet test (dummy) verisi otomatik olarak sisteme eklenir.
3.  Yine aynı dosya içinde yer alan Index, View, Trigger ve Stored Procedure yapıları veritabanında derlenir.
4.  Visual Studio üzerinden `EnvanterAPI` projesi açılır. `appsettings.json` dosyası içindeki `DefaultConnection` cümlesi yerel SQL Server bilgilerine göre güncellenir ve proje çalıştırılır.
5.  API ayaktayken `EnvanterMobil` projesi açılır, `MainPage.xaml.cs` içindeki API port adresi güncellenerek mobil uygulama "Windows Machine" veya Android Emülatör üzerinde derlenip çalıştırılır.

## Görseller ve Diyagramlar
*Not: Aşağıdaki alanlara projeye ait ilgili ekran görüntüleri eklenecektir.*

* **Arayüz Görseli:**
* **Veri Tabanı (ER) Diyagramı:** 
* **Akış Şeması:** 
## Referanslar
* Microsoft .NET MAUI Resmî Dokümantasyonu
* ASP.NET Core Web API Microsoft Dokümantasyonu
* SQL Server 2022 T-SQL Referans Kaynakları
