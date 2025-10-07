# ⚡ Süperbilgisayar ile Derin Öğrenme Optimizasyon Deneyleri: CIFAR-10 & ResNet

Bu proje, **NVIDIA P100 GPU**’lu süperbilgisayar ortamında, **SLURM job scheduler** ve **PyTorch Lightning** kullanılarak **CIFAR-10 veri seti** ve **ResNet mimarisi** üzerinde farklı **optimizasyon algoritmaları, batch boyutları ve paralel eğitim yöntemlerinin** test edilmesini ve karşılaştırılmasını kapsamaktadır.  

Amaç, eğitim sürelerini ve doğruluk değerlerini etkileyen faktörleri sistematik olarak analiz ederek, **en verimli eğitim kombinasyonlarını belirlemektir**.  

---

## 🚀 Proje Özeti
- **Veri Seti & Model:**  
  - CIFAR-10 veri seti  
  - ResNet mimarisi (PyTorch Lightning ile uygulanmıştır)  

- **Deneysel Çalışmalar:**  
  - Farklı **optimizasyon algoritmaları** test edildi (SGD, Adam, RMSProp vb.)  
  - Çeşitli **batch boyutları** denendi  
  - **Paralel eğitim yöntemleri** (DDP vb. yöntemler) uygulandı  
  - **SLURM scriptleri** ile süperbilgisayar üzerinde deneyler otomatikleştirildi  

- **Karşılaşılan Zorluk:**  
  - **Büyük batch boyutlarında OOM (Out of Memory) hataları** oluştu.  
  - Bu problem **Gradient Accumulation** ile giderildi.  

- **Sonuç:**  
  - Eğitim performansını artıran en verimli kombinasyonlar belirlendi.  
  - Doğruluk ve eğitim süresi açısından **optimum ayarlar** ortaya çıkarıldı.  

---

## 📂 Kullanılan Teknolojiler
- **Python**  
- **PyTorch Lightning** → Model tanımlama, eğitim ve logging  
- **CUDA** → GPU hızlandırma  
- **NVIDIA P100 GPU** → HPC ortamı  
- **SLURM** → Job scheduling ve GPU tahsisi  
- **PyTorch DDP (Distributed Data Parallel)** → Paralel eğitim  

---

## 🔬 Çalışma Adımları
1. **Veri Hazırlama** → CIFAR-10 veri seti indirildi ve normalize edildi  
2. **Model Tanımlama** → ResNet PyTorch Lightning  implement edildi  
3. **Optimizasyon Denemeleri** → SGD, Adam, RMSProp vb. algoritmalar denendi  
4. **Batch Boyutu Analizi** → Küçük ve büyük batch boyutları test edildi  
5. **Paralel Eğitim** → Lightning Trainer + SLURM + DDP kullanılarak multi-GPU eğitim  
6. **OOM Sorunu ve Çözüm** → Gradient Accumulation ile bellek sorunu çözüldü  
7. **Performans Ölçümü** → Eğitim süresi ve doğruluk değerleri karşılaştırıldı  

---

## 📊 Sonuçlar
- **Küçük batch boyutları:** Daha stabil eğitim, fakat uzun sürede yakınsama  
- **Büyük batch boyutları:** Daha hızlı eğitim, fakat OOM sorunları  
- **Gradient Accumulation:** OOM problemini çözdü, eğitim performansını artırdı  
- **PyTorch Lightning + SLURM:** Deneylerin otomatik, tekrarlanabilir ve ölçeklenebilir şekilde yürütülmesini sağladı  
- **En verimli kombinasyonlar:** Doğruluk ve eğitim süresi arasında optimum dengeyi sağladı  

---
