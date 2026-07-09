# 🌿 Plant Leaf Segmentation: A Data-Centric Deep Learning Pipeline

> **Complete data-centric semantic segmentation pipeline demonstrating how systematic dataset improvement, annotation refinement, targeted augmentation, and architectural enhancements can significantly improve plant leaf segmentation performance.**

<img width="1343" height="901" alt="image" src="https://github.com/user-attachments/assets/529d9a48-e2b5-4bed-becc-6298f70f3b02" />


<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue">
  <img src="https://img.shields.io/badge/TensorFlow-2.x-orange">
  <img src="https://img.shields.io/badge/OpenCV-4.x-green">
  <img src="https://img.shields.io/badge/Task-Semantic%20Segmentation-success">
  <img src="https://img.shields.io/badge/Model-Attention%20U--Net-brightgreen">
</p>

---
## 🏆 Project Highlights

- 🌱 Designed a complete **data-centric semantic segmentation pipeline** instead of focusing solely on model architecture.
- 🔍 Performed systematic **error analysis** to identify the root causes of segmentation failures.
- 🧹 Inspected the dataset manually and removed corrupted samples.
- ✍️ Refined segmentation annotations Manually on **Roboflow**.
- 🎯 Applied **targeted data augmentation** inspired by the model failures due to being low on training data.
- 🧠 Improved the baseline model using **Attention U-Net**.
- ✨ Applied post-processing techniques to refine predicted masks and suppress false positives.
- ⚖️ Benchmarked the final pipeline against a **fine-tuned DeepLabV3 + MobileNetV3** model using the same dataset.
---
## 🏗️ Project Pipeline

```text
┌────────────────────┐    ┌────────────────────┐    ┌────────────────────┐
│ Roboflow Dataset   │───▶│   Baseline U-Net   │───▶│   Error Analysis   │
└────────────────────┘    └────────────────────┘    └────────────────────┘
                                                         │
                                                         ▼
                     ┌────────────────────────────────────────────┐
                     │ Dataset Inspection & Cleaning              │
                     └────────────────────────────────────────────┘
                                         │
                                         ▼
                     ┌────────────────────────────────────────────┐
                     │ Original vs Cleaned Dataset Comparison     │
                     └────────────────────────────────────────────┘
                                         │
                    ┌────────────────────┴────────────────────┐
                    ▼                                         ▼
     ┌──────────────────────────────┐         ┌──────────────────────────────┐
     │ Annotation Refinement        │         │ Targeted Data Augmentation   │
     │ (Uploaded a Complete
      modified dataset on Roboflow) │────────▶│                             │
     └──────────────────────────────┘         └──────────────────────────────┘
                                         │
                                         ▼
                     ┌────────────────────────────────────────────┐
                     │              Attention U-Net              │
                     └────────────────────────────────────────────┘
                                         │
                                         ▼
                     ┌────────────────────────────────────────────┐
                     │              Post-processing               │
                     └────────────────────────────────────────────┘
                                         │
                                         ▼
                     ┌────────────────────────────────────────────┐
                     │ Fine-tuned DeepLabV3 + MobileNetV3         │
                     └────────────────────────────────────────────┘
                                         │
                                         ▼
                     ┌────────────────────────────────────────────┐
                     │       Final Performance Benchmarking       │
                     └────────────────────────────────────────────┘
```

---
## 📊 Performance Visualization

The final pipeline achieved substantial improvements over the baseline through a sequence of data-centric enhancements, architectural improvements, and post-processing techniques.

<p align="center">
<img width="1330" height="653" alt="image" src="https://github.com/user-attachments/assets/0d4f4fd7-bed3-4bfa-8e12-7f853f7e3ceb" />

</p>

### Real world test (example outside from the complete dataset splits)

<p align="center">
    <img width="467" height="461" alt="image" src="https://github.com/user-attachments/assets/f1fbbfd3-febb-42a4-b291-361aa989b1e9" />

</p>
---






## ⚖️ Performance Benchmarking 

The final pipeline was compared against a fine-tuned **DeepLabV3 + MobileNetV3** model trained under the same dataset.
Fine tuning the **DeepLabV3 + MobileNetV3** model was part of this project

<p align="center">
  <img width="1237" height="237" alt="image" src="https://github.com/user-attachments/assets/3d81f44e-480c-4bfa-ac19-c5c733c4f1d5" />
  
  <img width="1077" height="588" alt="image" src="https://github.com/user-attachments/assets/4a8f6a84-edff-43e4-aa7b-b885bd437023" />
 


</p>

The comparison highlights the effectiveness of the proposed data-centric pipeline while providing a fair reference against a widely adopted semantic segmentation architecture.


---

## 💡 Key Takeaways

Throughout this project, several practical observations became clear:

- Improving dataset quality had a greater impact than simply increasing model complexity.
- Systematic error analysis revealed issues that evaluation metrics alone could not identify.
- Manual annotation refinement significantly improved segmentation consistency.
- Targeted data augmentation proved more effective than applying aggressive augmentation to the entire dataset (in this case).
- Attention U-Net produced cleaner leaf boundaries than the baseline U-Net.
- Post-processing further reduced small false-positive regions without retraining the model.
- A fair benchmark against DeepLabV3 + MobileNetV3 provided stronger validation of the proposed pipeline.

---
## 🔮 Future Work (SOON)
- Expanding the dataset with additional plant species and real-world field images to increase model quality and generalization on any plant leaf.
- Integrating the segmentation model with a downstream plant disease classification pipeline.
---

## 📁 Repository Structure

```text
Plant-Leaf-Segmentation/
│
├── 📂 images/
│   ├── Project full map.png
│   ├── Model Performance on test split images (1).png
│   ├── Model Performance on test split images (2).png
│   └── Model Performance on real world images.png
│
├── 📂 Results & Benchmarking/
│   ├── Original Vs Clean Dataset.jpg
│   ├── Unet Vs Attention Unet.png
│   ├── Benchmark Table.png
│   └── Benchmark Graph.png
│
├── 📂 Notebooks/
│   ├── 01_Unet_Error_Analysis_Corrupted_vs_Cleaned.ipynb
│   ├── 02_Attention_UNet_and_Driven_Augmentation.ipynb
│   ├── 03_Attention_UNet_Postprocessing.ipynb
│   └── 04_Fine_Tuning_DeepLabV3_MobileNetV3_Benchmark.ipynb
│
├── 📂 Model/
│   └── LeafSegNet_Attention.keras
│
├── 📂 Data Sets/
│   ├── Original Dataset Link.txt
│   └── My Refined Dataset.txt
│
├── README.md
```









