# **Banka Pazarlama Veri Seti Üzerinde Sınıflandırma**

## Problem Tanımı
Bu projede, bir Portekiz bankasının 2008-2010 yılları arasındaki telefonla pazarlama çabalarının kayıtlarını içeren bir veri seti üzerinde çalışılmıştır. Bankanın gelecek kampanyalarında daha fazla müşteriyi banka mevduatına abone olmaya ikna etmek için en etkili taktikleri belirlemek amacıyla makine öğrenimi teknikleri uygulanmıştır. Veri seti, 45211 veri örneği ve 17 özellikten oluşmaktadır. Bu proje, bankanın pazarlama stratejilerini iyileştirmek için makine öğrenimi algoritmalarını kullanmayı amaçlamaktadır.


## Metodoloji
Veri seti, iletişime geçilen müşterinin mevduatı abone olup olmadığına bağlı olarak 'evet' veya 'hayır' olarak etiketlenmiştir. Bu bir pazarlama problemidir ve sonuç büyük ölçüde bankanın gelecekteki stratejilerini etkileyecektir. Banka kurumu çok büyük bir müşteri tabanına ve hatta daha büyük hedef müşterilere sahiptir. Gerçek dünyada, daha az müşteri pazarlama kampanyasına olumlu yanıt verecek ve çoğu hayır diyecektir. Tüm müşterilere ulaşmak zaman alıcı bir görevdir ve büyük zaman ve çaba gerektirir. İnsan kaynaklarını verimli bir şekilde yönetmek için, evet deme olasılığı daha yüksek olan müşterileri doğru bir şekilde tanımlamak gereklidir. İşte burada makine öğrenimi devreye girer.

## Değişkenler ve Keşifsel Veri Analizi

### Bağımsız Değişkenler

- **Age** : Kişinin yaşı

- **Job** : Kişinin yapmakta olduğu meslek ("yönetici", "bilinmeyen", "işsiz", "yönetim", "hizmetçi", "girişimci", "öğrenci", "mavi yakalı", "serbest meslek sahibi" ,"emekli", "teknisyen", "hizmetler")

- **Marital** : Kişinin medeni hali ("evli", "boşanmış", "bekar"; not: "boşanmış" boşanmış veya dul anlamına gelir.)

- **Education** : Kişinin eğitim durumu ("bilinmiyor", "ikincil", "ilköğretim", "üçüncül")

- **Default** : Kişi kredi ödeme şartlarını ihlal etti mi? ("evet", "hayır")

- **Balance** : Müşterinin hesabındaki euro cinsinden ortalama yıllık bakiyesi

- **Housing** : Kişinin hali hazırda bir konut kredisi var mı? ("evet", "hayır")

- **Loan** : Müşterinin bankada kredisi var mı? ("evet", "hayır")

- **Contact** : İletişim türü ("bilinmeyen", "telefon", "cep telefonu")

- **Day** : Kişiyle son iletişim günü

- **Month** : Kişiyle son iletişim ayı ("ocak", "şubat", "mar", ..., "kasım", "aralık")

- **Duration** : saniye cinsinden son temas süresi

- **Campaign** : Bu kampanya sırasında ve bu müşteri için gerçekleştirilen iletişim sayısı

- **Pdays** : Önceki bir kampanyadan müşteriyle son iletişime geçildikten sonra geçen gün sayısı (-1, müşteriyle daha önce iletişime geçilmediği anlamına gelir.)

- **Previous** : bu kampanyadan önce ve bu müşteri için gerçekleştirilen iletişim sayısı

- **Poutcome** : önceki pazarlama kampanyasının sonucu ("bilinmiyor", "diğer", "başarısızlık", "başarı")

### Bağımlı Değişken

- **Deposit** : Kişi vadeli mevduata abone oldu mu? ("1 : hayır", "2 : evet") 

### Keşisel Veri Analizi için Değişken Mühendisliği Kapsamında Türetilen Değişkenler

- **Yaş Aralık** : 18-30 yaş arası "Genç Yetişkin", 30-65 yaş arası "Yetişkin", 65+ "Yaşlı" olarak sınıflandırılmıştır.

- **Çalışma Durumu** : Eğer kişinin işi "Unemployed", "Student", "Retired" olarak belirtildiyse bu kişiler "Çalışmıyor", geri kalan tüm işlere sahip olanlar "Çalışıyor" olarak sınıflandırılmıştır.

- **İletişim Durumu** : Önceki bir kampanyadan müşteriyle son iletişime geçildikten sonra geçen gün sayısı -1 ise "İletişime Geçilmedi", -1'den farklı ise "İletişime Geçildi" olarak sınıflandırılmıştır.

Bu değişkenler kullanılarak, çaprazlamalar, görselleştirmeler yapılmış ve desenlerin yakalanması amaçlanmıştır.

## Yöntem

Veri üzerinde yapılan incelemeler ve görselleştirmeler sonucunda bağımlı değişkendeki sınıflar arasında dengesizlik olduğu saptanmıştır. Vadeli mevduata **abone olan** kişi sayısı 5289, **abone olmayan** kişi sayısı ise 39922'dir.
Projenin amacı potansiyel müşterilerin tespit edilmesi olduğu için ve makine öğrenmesi algoritmaları, dengeli veri setlerinde daha iyi çalıştığından bu dengesizliğin ortadan kaldırılması gerekmektedir. Bu kapsamda sentetik veri üreterek dengesizlik sorunu çözülmektedir. Projede örnekleme yöntemi kullanılmadan ve 5 farklı örnekleme yöntemi kullanılarak performansları açısından karşılaştırma yapılmıştır. Kullanılan aşırı örnekleme ve eksik örnekleme teknikleri şunlardır;

### Aşırı Örnekleme Teknikleri;

- **Random Over Sampler**

- **Smote**

- **BorderLine Smote**

### Azınlık Örnekleme Teknikleri;

- **Random Under Sampler**

- **TomekLinks**




