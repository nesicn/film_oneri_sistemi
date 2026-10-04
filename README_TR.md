<p align="center">
  <a href="README.md"><img src="https://img.shields.io/badge/Language-English-blue?style=for-the-badge&logo=googletranslate&logoColor=white" alt="English"></a>
  <img src="https://img.shields.io/badge/Dil-Türkçe-red?style=for-the-badge&logo=googletranslate&logoColor=white" alt="Türkçe">
</p>

---

# 🎬 CosineCast — Film Öneri Sistemi

[![Canlı Demo](https://img.shields.io/badge/Canlı_Demo-CosineCast_App-E50914?style=for-the-badge&logo=google&logoColor=white)](https://cosinecast.ai.studio/)
[![Colab'da Aç](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1_gwoZcq9GkjQnLejZ5dtYFn62_auoNNT?usp=sharing)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Veri Seti](https://img.shields.io/badge/Veri_Seti-MovieLens_100K-F37021?style=flat)](https://grouplens.org/datasets/movielens/100k/)

**MovieLens 100K** referans veri seti üzerinde geliştirilmiş, matematiksel temellere dayanan, uçtan uca bir Film Öneri Sistemi. 

Bu repo; tamamen sıfırdan oluşturulmuş **Google Colab not defterini**, algoritmaları ve keşifsel veri analizini (EDA) içermektedir. Modelin gerçek zamanlı performansını sergilemek amacıyla **Google AI Studio** kullanılarak etkileşimli ve canlıya alınmaya hazır (production-ready) bir web uygulaması demosu geliştirilmiştir.

🔗 **Canlı Web Uygulamasını İnceleyin:** [CosineCast Etkileşimli Demo](https://cosinecast.ai.studio/)

---

## 📌 Proje Mimarisi ve Katkılar

- **Temel Makine Öğrenmesi ve Algoritmalar (Google Colab):**  
  Google Colab üzerinde **sıfırdan** tasarlanmış, formüle edilmiş ve uygulanmıştır. Veri aktarımı (data ingestion), keşifsel veri analizi (EDA), matris vektörleştirme ve öneri matematiğini (İçerik Tabanlı ve İş Birlikli Filtreleme) kapsar.
  
- **Etkileşimli Web Demosu (Google AI Studio):**  
  **Google AI Studio** kullanılarak etkileşimli ve reaktif bir web kullanıcı arayüzüne dönüştürülmüştür.

---

## 🚀 Temel Öneri Algoritmaları

### 1. İçerik Tabanlı Filtreleme (Tür Kosinüs Benzerliği)
- Film türlerini ikili (binary) özellik vektörlerine dönüştürür.
- Öğeler arasındaki yüksek boyutlu kosinüs benzerliğini hesaplar:
  $$\text{Kosinüs Benzerliği}(\mathbf{u}, \mathbf{v}) = \frac{\mathbf{u} \cdot \mathbf{v}}{\|\mathbf{u}\|_2 \|\mathbf{v}\|_2}$$
- Seçilen herhangi bir film için en yakın $N$ sinematik eşleşmeyi önerir.

### 2. Kullanıcı Tabanlı İş Birlikli Filtreleme (User-Item Matrix)
- Seyrek (sparse) bir özet matris ($610 \text{ kullanıcı} \times 9.700+ \text{ film}$) oluşturur.
- Ortak zevk profillerine sahip, en yüksek korelasyona sahip emsal kullanıcıları (peer users) tespit eder.
- Eksik film puanlarını benzerlik ağırlıklı oylama ile tahmin eder ve hedefli öneriler sunar.

### 3. Yeni Kullanıcılar İçin Soğuk Başlangıç (Cold-Start) Çözümü
- Kullanıcı katılım sürecinde (onboarding) bir zevk profili oluşturucu sunarak soğuk başlangıç sorununu çözer.
- Geçmiş kullanıcı verisine ihtiyaç duymadan, ilk verilen puanları ve tür tercihlerini dinamik olarak harmanlayarak gerçek zamanlı kişiselleştirilmiş öneriler sunar.

### 4. Keşifsel Veri Analizi (EDA)
- Puan dağılımları, kullanıcı aktivite histogramları, seyreklik (sparsity) analizi ve tür ısı haritaları.

---

## 📊 Veri Seti: GroupLens MovieLens 100K

- **9.742** film genelinde **100.836** puanlama.
- **610** benzersiz anonim kullanıcı.
- Puanlama ölçeği: $0,5$ - $5,0$ yıldız.

---

## 🛠️ Teknolojiler ve Kütüphaneler

- **Veri İşleme ve Matematik:** Python, `pandas`, `numpy`, `scipy`
- **Makine Öğrenmesi ve Benzerlik:** `scikit-learn` (`cosine_similarity`)
- **Geliştirme Ortamı:** Google Colab
- **Canlı Demo Platformu:** Google AI Studio / Cloud Run (React, TypeScript, Tailwind CSS)

---
