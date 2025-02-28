# Fashion MNIST Üzerinde MLP Modeli ile Çoklu Sınıflandırma

Bu proje, Fashion MNIST veri seti üzerinde çok sınıflı görüntü sınıflandırma yapmak için geliştirilen bir yapay sinir ağı (MLP) modelini kullanmaktadır. Modelin eğitim süreci, optimizasyon teknikleri ve elde edilen sonuçlar raporlanmıştır.

## Proje Özeti

Bu proje, Fashion MNIST veri seti üzerinde çok sınıflı sınıflandırma yapmak için bir MLP (Multi-Layer Perceptron) modeli geliştirmiştir. Modelde kullanılan optimizasyon algoritmalarının karşılaştırılması, hiperparametrelerin ayarlanması ve modelin doğrulama doğruluğu üzerinde yapılan iyileştirmeler ele alınmıştır. Modelin eğitimi Adam ve SGD optimizasyon algoritmaları ile yapılmış, doğrulama doğruluğu %88.95, eğitim doğruluğu ise %92.05 olarak elde edilmiştir.

## Model Mimarisi

- **Giriş Katmanı**: 28x28 boyutundaki görseller tek boyutlu vektörlere dönüştürülür.
- **İlk Gizli Katman**: 300 nöronlu bir Dense katmanı ve ReLU aktivasyon fonksiyonu kullanılır.
- **İkinci Gizli Katman**: 100 nöronlu bir Dense katmanı ve ReLU aktivasyonu.
- **Çıktı Katmanı**: 10 nöronlu Dense katmanı, Softmax aktivasyon fonksiyonu ile sınıflandırma yapılır.
- **Düzenleme Teknikleri**: Dropout (0.2) ve Batch Normalization kullanılarak aşırı öğrenme (overfitting) engellenmeye çalışılmıştır.
- **Optimizasyon Algoritmaları**: Adam ve SGD kullanılarak modelin performansı karşılaştırılmıştır.
- **Kayıp Fonksiyonu**: `sparse_categorical_crossentropy`
- **Doğruluk Metriği**: `accuracy`

## Kullanılan Hiperparametreler

- **Optimizasyon Algoritması**: Adam (0.001 öğrenme oranı) ve SGD karşılaştırıldı.
- **Öğrenme Oranı**: 0.001 ve 0.005 olarak test edilmiştir.
- **Dropout Oranı**: 0.2 olarak ayarlanmıştır.
- **Batch Size**: 64, 32 ve 128 batch size seçenekleri ile test edilmiştir.
- **Epoch Sayısı**: 30 epoch boyunca eğitim yapılmıştır.

## Sonuçlar ve İyileştirme Önerileri

- **Adam Optimizasyonu vs. SGD**: Adam optimizasyonu, daha hızlı öğrenme sağlarken, SGD daha stabil ve düşük test kaybı sağladı. Adam, model doğruluğunu artırdı, ancak precision oranında bir düşüş görüldü.
- **Öğrenme Oranı**: 0.001 öğrenme oranı, en iyi performansı gösterdi.
- **Dropout**: Dropout (0.2) oranı, modelin doğrulama doğruluğunu artırdı.
- **Batch Size**: Batch size 64, en iyi doğrulama doğruluğunu elde etti.
- **Batch Normalization**: Batch Normalization eklenmesi, modelin doğrulama doğruluğunu bir miktar düşürse de overfitting’i önledi.

### İyileştirme Önerileri

- **Hiperparametre Optimizesi**: Öğrenme oranı, batch size ve epoch sayısı üzerine iyileştirmeler yapılabilir.
- **Daha Derin Ağ Yapıları**: Daha fazla katman ve nöron ekleyerek modelin karmaşıklığı artırılabilir.
- **Veri Augmentasyonu**: Eğitim verisini artırmak için görüntü augmentasyon teknikleri kullanılabilir.
- **L2 Regularization ve Early Stopping**: Overfitting'i engellemek için bu teknikler kullanılabilir.
- **Transfer Learning**: Önceden eğitilmiş modelleri kullanarak eğitim süreci hızlandırılabilir.

## Sonuçlar

- **Eğitim Doğruluğu**: %92.05
- **Doğrulama Doğruluğu**: %88.95
- **Eğitim Kaybı**: Düşük ancak doğrulama kaybı biraz artmış olabilir.

Model, genel doğruluğu ile iyi sonuçlar verirken, genelleme yeteneği açısından bazı iyileştirme alanlarına sahiptir.

## Ekstra Deneyler

Modelin eğitim sürecinde, üç gizli katman kullanılmıştır ve her katmanda Dropout uygulanmıştır. Ayrıca, eğitim sürecinde Adam optimizasyonu kullanılmış ve model 25 epoch boyunca eğitilmiştir. Eğitimde elde edilen doğruluk sonuçları oldukça olumlu olmuş ve genelleme yeteneği üzerinde iyileştirmeler yapılabileceği önerilmiştir.

## Kurulum

Projenin çalışabilmesi için aşağıdaki adımları takip edebilirsiniz:

1. Python 3.6+ sürümü gereklidir.
2. Aşağıdaki kütüphaneleri yükleyin:

   ```bash
   pip install tensorflow numpy matplotlib pandas scikit-learn seaborn
   ```
