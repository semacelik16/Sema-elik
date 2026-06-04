# Sema-elik
Envanter Takip Sistemi
# Tekstil Envanter Yönetim Sistemi (Mobil)

[cite_start]Bu proje, Kocaeli Üniversitesi Bilişim Sistemleri Mühendisliği Bölümü TBL331: Veritabanı Yönetim Sistemleri dersi kapsamında geliştirilmiş bir dönem projesidir[cite: 1, 2, 4]. 

## Proje Özeti & Genel Yapı
[cite_start]Tekstil ürünlerinin (renk, beden ve kumaş tipi detaylarıyla) stok giriş-çıkışlarını takip etmeyi sağlayan, mobil tabanlı bir envanter yönetim sistemidir[cite: 22, 46]. [cite_start]Sistem; verilerin bütünlüğünü sağlayan ilişkisel bir SQL veritabanı, bu veritabanı ile güvenli haberleşmeyi sağlayan bir arka plan API servisi ve kullanıcı etkileşimini kolaylaştıran bir mobil arayüzden oluşmaktadır[cite: 46]. [cite_start]Öğeler maddeler halinde, kısa ve net cümlelerle tasarlanmıştır[cite: 23].

## Problem Tanımı
[cite_start]Tekstil sektöründe aynı ürünün farklı beden, renk ve kumaş varyasyonlarının bulunması, geleneksel yöntemlerle stok takibini zorlaştırmakta ve manuel kayıt hatalarına yol açmaktadır[cite: 40]. [cite_start]Bu karmaşıklığı ortadan kaldırmak için, verilerin merkezi bir veritabanında güvenle tutulduğu, anlık olarak erişilebilen ve kullanıcı dostu bir mobil çözüme ihtiyaç duyulmuştur[cite: 40].

## Yapılan Araştırmalar
* [cite_start]Mobil uygulamaların doğrudan veritabanına bağlanmasının güvenlik zafiyetleri ve performans kayıpları yaratacağı tespit edilmiş, çözüm olarak aracı bir Web API katmanı kullanılmasına karar verilmiştir[cite: 42].
* [cite_start]Veritabanı tarafında ürün varyasyon karmaşasını önlemek adına 5N (Normalizasyon) kurallarına uygun yapısal araştırmalar yapılmış ve tablolar buna göre ayrıştırılmıştır[cite: 42, 50].
* [cite_start]Mobil ekranda kullanım kolaylığını sağlamak amacıyla göz yormayan, pastel mavi ve pastel yeşil tonlarında modern bir UI/UX deneyimi araştırılıp projeye entegre edilmiştir[cite: 42].

## Yazılım Mimarisi ve Geliştirme Ortamı
[cite_start]Projenin kodlanması aşamasında 3 katmanlı modern bir mimari tercih edilmiştir[cite: 45]. [cite_start]Geliştirme ortamı ve kullanılan teknolojiler şu şekildedir[cite: 22]:
* **Veritabanı Katmanı:** Microsoft SQL Server 2022
* **Backend (Aracı Katman):** ASP.NET Core Web API (C#) & Entity Framework Core
* **Frontend (Mobil Kullanıcı Arayüzü):** .NET MAUI (XAML & C#)
* **Geliştirme Aracı (IDE):** Visual Studio 2022

## Projenin Yüklenmesi ve Çalıştırılması
[cite_start]Projenin test edilmesi ve çalışır duruma getirilmesi için aşağıdaki adımlar izlenmelidir[cite: 22]:
1.  GitHub üzerinden proje dosyaları bilgisayara indirilir.
2.  [cite_start]`grupno_sql_betikleri.txt` dosyası içindeki SQL kodları SQL Server Management Studio (SSMS) üzerinde çalıştırılır[cite: 27]. [cite_start]Bu işlem sayesinde tablolar, Primary/Foreign Key ilişkileri, Check/Unique kısıtlayıcıları ve minimum 10 adet test (dummy) verisi otomatik olarak sisteme eklenir[cite: 16, 17].
3.  [cite_start]Yine aynı dosya içinde yer alan Index, View, Trigger ve Stored Procedure yapıları veritabanında derlenir[cite: 18].
4.  Visual Studio üzerinden `EnvanterAPI` projesi açılır. `appsettings.json` dosyası içindeki `DefaultConnection` cümlesi yerel SQL Server bilgilerine göre güncellenir ve proje çalıştırılır.
5.  [cite_start]API ayaktayken `EnvanterMobil` projesi açılır, `MainPage.xaml.cs` içindeki API port adresi güncellenerek mobil uygulama "Windows Machine" veya Android Emülatör üzerinde derlenip çalıştırılır[cite: 22].

## Görseller ve Diyagramlar
*Not: Aşağıdaki alanlara projeye ait ilgili ekran görüntüleri eklenecektir.*

* [cite_start]**Arayüz Görseli:** `[Buraya mobil uygulamanızın ekran görüntüsünü ekleyin]` [cite: 22]
* [cite_start]**Veri Tabanı (ER) Diyagramı:** `[Buraya SQL tablolarınızın ER diyagramı görüntüsünü ekleyin]` [cite: 46]
* [cite_start]**Akış Şeması:** `[Buraya uygulamanın genel çalışma mantığını gösteren şemayı ekleyin]` [cite: 44]

## Referanslar
* Microsoft .NET MAUI Resmî Dokümantasyonu
* ASP.NET Core Web API Microsoft Dokümantasyonu
* SQL Server 2022 T-SQL Referans Kaynakları
[cite_start]* [cite: 47]
