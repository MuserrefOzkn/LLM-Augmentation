# LLM-Augmentation
# 📌 LLM ile Veri Artırma Projesi

Bu proje, **büyük dil modelleri (LLM) kullanarak metin sınıflandırması için veri artırma** yöntemlerini incelemektedir. Çalışmada hem eğitim hem de test kümelerine farklı veri artırma yöntemleri uygulanmış ve sınıflandırma başarıları değerlendirilmiştir. Test veri kümesi için arttılan veriler ve orijinallerinin kararları birleştirilerek tahminler yapılmıştır.

## 📖 Proje Açıklaması

Metin sınıflandırma modellerinin performansını artırmak amacıyla veri setlerine farklı büyük dil modelleri kullanılarak veri artırma uygulanmıştır. **XGBoost ve Destek Vektör Makinesi (SVM) algoritmaları** ile sınıflandırma gerçekleştirilmiştir.

Kullanılan LLM modelleri:
- `google/flan-t5-large`
- `tuner007/pegasus_paraphrase`
- `eugenesiow/bart-paraphrase`
- `gemini-1.5-flash`

Veri artırma, **iki, üç ve beş katına çıkarma** yöntemleri ile test edilmiş ve sonuçlar değerlendirilmiştir.

## 📊 Kullanılan Veri Kümeleri

1. **Gıda Ürünleri Yorumları:** Kullanıcı yorumlarından ve puanlarından oluşan bir veri kümesi.
2. **Otel Rezervasyon Yorumları:** Otel müşterilerinin yorumları ve verdikleri puanları içeren veri kümesi.

Her iki veri kümesi için:
- **%80 eğitim, %20 test** olarak ayrılmıştır.
- Sınıflar dengeli tutulmuştur.
- Accuracy ve F1-Score metrikleri kullanılarak değerlendirme yapılmıştır.

## 🔍 Kullanılan Yöntemler

- **Veri Temsili:** `all-MiniLM-L12-v2` modeli ile metinler vektör uzayında temsil edilmiştir.
- **Sınıflandırma Algoritmaları:** 
  - Gıda yorumları için **XGBoost**
  - Otel yorumları için **Destek Vektör Makinesi (SVM)**
- **Veri Artırma Teknikleri:**
  - LLM tabanlı paraphrasing (yeniden ifade etme)
  - Farklı modeller ile veri üretimi

## 📊 Deneysel Sonuçlar

- Eğitim verisini **iki katına çıkarma** yöntemiyle **accuracy skoru %25'ten %50'ye** kadar artırılmıştır.
- Farklı LLM modelleri için test verisi artırılarak oylama yöntemiyle karar birleştirilmiştir.
- En iyi sonuçlar:
  - **Eğitim kümesi:** `google/flan-t5-large` modeli (%50 accuracy)
  - **Test kümesi:** `eugenesiow/bart-paraphrase` modeli (%30 accuracy)

Detaylı sonuçlar için **[📄 Proje Raporu](docs/LLM Augmentation (2).pdf)** dosyasını inceleyebilirsiniz.
