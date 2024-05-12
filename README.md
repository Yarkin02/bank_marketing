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
Projenin amacı potansiyel müşterilerin tespit edilmesi olduğu için ve makine öğrenmesi algoritmaları, dengeli veri setlerinde daha iyi çalıştığından bu dengesizliğin ortadan kaldırılması gerekmektedir. Bu kapsamda sentetik veri üreterek dengesizlik sorunu çözülmektedir. Projede örnekleme yöntemi kullanılmadan ve 5 farklı örnekleme yöntemi ve 6 farklı makine öğrenmesi algoritması kullanılarak performansları açısından karşılaştırma yapılmıştır. Kullanılan aşırı örnekleme, eksik örnekleme teknikleri ve makine öğrenmesi algoritmaları şunlardır;

### Kullanılan Aşırı Örnekleme Teknikleri;

- **Random Over Sampler**

- **Smote**

- **BorderLine Smote**

### Kullanılan Azınlık Örnekleme Teknikleri;

- **Random Under Sampler**

- **TomekLinks**

### Kullanılan Makine Öğrenmesi Algoritmaları;

- **Lojistik Regresyon**

- **Destek Vektör Makineleri (SVM)**

- **Rastgele Orman**

- **Karar Ağaçları**

- **k-En Yakın Komşu (k-NN)**

Kurulan modellerde “Random_state” parametresi dışında herhangi bir parametre kullanılmamıştır. Modeller değerlendirme aşamasında her bir sınıflandırma algoritması ve örnekleme metotları için, Kesinlik (Precision), Duyarlılık (Recall), F1- Skor (F1-Score), ROC Alanı (ROC Curve), Aucpr hesaplanmıştır. Uygun modeli seçerken bu değerlerin her bir metrik için en yüksek olması beklenir fakat amacımız azınlık sınıfının daha iyi tahmin edilmesi için önceliğimiz F1-Skor ve Aucpr olacaktır. Bu koşullar altında en iyi performansı Aşırı Örnekleme Metodu BorderLine Smote kullanılan Rastgele Orman algoritması göstermektedir. Azınlık sınıfına ait elde ettiğimiz değerler şu şekildedir;

- Aucpr : 0.5085
- Roc Auc : 0.7681
- F1-score : 0.5481
- Recall : 0.6117
- Precision : 0.4964

## Model İyileştirilmesi

Model iyileştirilmesi amacıyla, Resampling, Sampling_Strategy ve Model Tunning işlemleri uygulanmıştır.

1-) Resampling : Vadeli mevduata abone olmayan 39922 kişiden 20000 kişi rastgele olarak seçilmiştir.

2-) Sampling_strategy : En iyi performans sampling_strategy = {1: 16000, 2: 13000} ile alınmıştır.

3-) Model Tunning : Bu aşamada, n_estimator(Ağaç sayısı), max_depth(Maksimum Derinlik), min_samples_split(Bir iç düğümün bölünmesi için gereken minimum örnekleme sayısı), min_samples_leaf(Bir yaprak düğümünün oluşturulması için gereken minimum örnekleme sayısı) hiperparametreleri Optuna kütüphanesi ile tune edilmiştir. Azınlık sınıfı için en yüksek f1-skorunu veren hiperparametre değerleri şu şekildedir. 

- n_estimators = 222
- max_depth = 38
- min_samples_split = 2
- min_samples_leaf = 1

## Sonuç

Yapılan bu işlemler sonrasında en iyi performansı Random Over Sampling'li Random Forest algoritması vermiştir.

İyileştirmeler sonrası elde edilen tüm değeler şu şekildedir;

- Train Cross-Validation Scores : [0.93839635 0.94148415 0.94197388 0.944939 0.94459103]

- Test Cross-Validation Scores : [0.90853659 0.91736527 0.92961165 0.91521347 0.91927711]

- - - - - - - - - - - - - - - - - - - - - - - - - 
              
              precision    recall  f1-score   support

           1       0.93      0.91      0.92      4000
           2       0.69      0.72      0.71      1058

    accuracy                           0.87      5058
    macro avg       0.81     0.82      0.81      5058
    weighted avg    0.88     0.87      0.88      5058

    Roc Auc : 0.8184
    Aucpr : 0.7473
    
- - - - - - - - - - - - - - - - - - - - - - - - - 

Azınlık sınıfına ait F1-skoru 0.5481 değerinden 0.71'e kadar çekilmiştir. Test - Train CV değerleri arasında büyük farklılıklar gözlemlenmediği için modelde herhangi bir Overfit durumu yoktur. Genelleme yeteneği yüksek, dengeli, maliyeti düşük bir model elde edilmiştir.
