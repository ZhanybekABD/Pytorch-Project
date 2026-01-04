# Rice Type Classification with PyTorch
Bu proje, pirinç tanelerinin morfolojik özelliklerini kullanarak türlerini (Gönen ve Jasmine) sınıflandırmak amacıyla geliştirilmiş bir derin öğrenme projesidir. Proje kapsamında PyTorch kütüphanesi kullanılarak yapay sinir ağı (ANN) modeli tasarlanmış, eğitilmiş ve test edilmiştir.

# Veri Seti Açıklaması
Kullanılan veri seti, Kaggle üzerinden temin edilen "Rice Type Classification" veri setidir.

Veri Boyutu: Toplam 18,185 satır ve 11 sütundan oluşmaktadır.

Sınıflar: Veri seti dengeli bir dağılıma sahiptir:

Class 1 (Jasmine): 9,985 örnek.

Class 0 (Gönen): 8,200 örnek.

Özellikler (Features): Model eğitiminde pirincin Alan (Area), Çevre (Perimeter), Yuvarlaklık (Roundness), Eksantriklik (Eccentricity) gibi 10 farklı morfolojik özelliği girdi olarak kullanılmıştır.

Veri Ön İşleme: - Eksik veriler temizlenmiş ve gereksiz sütunlar (ID gibi) kaldırılmıştır.

Modelin daha hızlı yakınsaması için tüm özellikler maksimum değerlerine bölünerek normalize edilmiştir.
# Model Mimarisi
Model, ikili sınıflandırma (binary classification) görevini yerine getirmek üzere tasarlanmış çok katmanlı bir yapay sinir ağıdır.

Mimari Detayları:

Giriş Katmanı: 10 özellik (features).

Gizli Katmanlar:

Gizli Katman: 32 nöron + ReLU Aktivasyon.

Gizli Katman: 16 nöron + ReLU Aktivasyon.

Gizli Katman: 8 nöron + ReLU Aktivasyon.

Çıkış Katmanı: 1 nöron + Sigmoid Aktivasyon (Olasılıksal çıktı için).

Optimizasyon: Adam Optimizer.

Kayıp Fonksiyonu: Binary Cross Entropy Loss (BCELoss).

# Eğitim ve Başarı Metrikleri
Model, T4 GPU hızlandırıcısı kullanılarak PyTorch üzerinde eğitilmiştir. Eğitim süreci boyunca hem kayıp (loss) hem de doğruluk (accuracy) değerleri takip edilmiştir.

## Eğitim Grafikleri
Eğitim sürecindeki performans değişimi aşağıdaki grafiklerde raporlanmıştır:

Loss Grafiği: Eğitim ve doğrulama kaybının epochlar ilerledikçe istikrarlı bir şekilde düştüğü gözlemlenmiştir.

Accuracy Grafiği: Modelin eğitim ve test setleri üzerindeki başarısının %99 seviyelerine ulaştığı kaydedilmiştir.

# Başarı Metrikleri
Modelin test veri seti üzerindeki nihai başarısı şu şekildedir:

Test Doğruluğu (Test Accuracy): ~%99+

Kayıp Değeri (Final Loss): Minimum seviyeye indirilmiştir.

# Gereksinimler
Projenin çalıştırılması için aşağıdaki kütüphanelerin yüklü olması gerekir:

torch 
torchsummary 
pandas 
numpy 
matplotlib 
scikit-learn 
opendatasets

# Çalıştırma
Notebook dosyasını (21703910_NN.ipynb) Google Colab veya yerel bir Jupyter ortamında açarak tüm hücreleri sırasıyla çalıştırabilirsiniz. Veri seti opendatasets aracılığıyla otomatik olarak Kaggle'dan indirilecektir.

Bu proje Zhanybek ABDUPATTAEV tarafından geliştirilmiştir.
