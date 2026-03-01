# Ses Veri Seti Bölümlenmesi (Audio Dataset Splitting)

Projenin ses işleme aşamasında kullanılacak olan **RAVDESS** veri seti, geliştirilecek çok modlu yapay zeka modelinin (CNN) farklı konuşmacı profillerini ve akustik özellikleri öğrenebilmesi amacıyla birleştirilerek geniş bir veri havuzu oluşturulmuştur. 

Python ortamında yürütülen analiz sonucunda, proje dizinlerinde toplam **1.248 adet temizlenmiş `.wav` uzantılı ses dosyası** tespit edilerek işleme alınmıştır.

## 📊 Veri Seti Dağılımı

Modelin aşırı öğrenme (overfitting) probleminden korunması ve genelleme yeteneğinin artırılması için bu veri seti, makine öğrenmesi standartlarına uygun olarak **%80 Eğitim, %10 Doğrulama ve %10 Test** kümelerine ayrılmıştır:

| Veri Kümesi | Oran | Kullanım Amacı |
| :--- | :---: | :--- |
| **Train (Eğitim)** | %80 | Modelin akustik özellikleri ve farklı konuşmacı profillerini öğrenmesi. |
| **Validation (Doğrulama)** | %10 | Eğitim sırasında hiperparametre optimizasyonu ve overfitting kontrolü. |
| **Test** | %10 | Eğitilmiş modelin daha önce hiç duymadığı sesler üzerindeki nihai başarısının ölçülmesi. |
| **Toplam** | **%100** | **1.248 Adet Ses Dosyası** |

## ⚙️ Metodoloji ve Araçlar

* **Kullanılan Veri Seti:** RAVDESS
* **Ortam:** Python
* **Kütüphane:** `scikit-learn` (`train_test_split`)
* **Tutarlılık (Seed) Sabiti:** `random_state=42`

Bölümlendirme işlemi, veri dağılımının her eğitimde tutarlı kalması için rastgelelik sabiti (`random_state=42`) ile güvence altına alınmıştır. Bu işlem sonucunda 1.248 adet ses verisi ilgili hedef klasörlere (Train, Validation, Test) başarıyla tasnif edilmiş ve CNN modelinin eğitimine tam anlamıyla hazır hale getirilmiştir.
