# Multiclass Semantic Segmentation of Breast Cancer Histopathological Images

## Description
This project implements U-Net models for the multiclass semantic segmentation of Whole Slide Images (WSIs) in breast cancer, utilizing the public **Breast Cancer Semantic Segmentation (BCSS)** dataset. The primary objective is to classify tissue regions into critical categories—such as Tumor, Stroma, Lymphocytic Infiltrate, Necrosis, and Others—to support advanced computational pathology workflows.

## Objectives
- Develop robust U-Net models tailored for multiclass segmentation on high-resolution WSIs.
- Compare and contrast model performance using input patch sizes of 256x256 and 512x512 pixels.
- Evaluate segmentation accuracy and generalization capabilities using standard medical imaging metrics (Dice Coefficient, Jaccard Index, and Global Accuracy).

## Methodology
- **Architecture**: U-Net framework leveraging KimiaNet (a DenseNet-121 based backbone) as a pretrained encoder.
- **Dataset**: BCSS dataset, featuring expert-annotated WSIs.
- **Preprocessing**: Grid-based patch extraction at 256x256 and 512x512 pixel resolutions.
- **Training**: Stratified K-Fold cross-validation, AdamW optimizer, Categorical Crossentropy loss function, and progressive layer fine-tuning.
- **Hyperparameters**: Learning rates ranging from $1\times10^{-3}$ to $1\times10^{-5}$, batch sizes of 8, 10, and 12, trained over 18 epochs.
- **Evaluation**: Per-class metrics and micro-averaged aggregates to effectively handle highly imbalanced tissue classes.

## Key Results
The developed models achieved high-fidelity segmentation, yielding predicted masks that closely align with ground-truth annotations, particularly within majority classes (Tumor and Stroma). The 512x512 model demonstrated superior performance in capturing broader spatial context, whereas the 256x256 model proved more efficient at recognizing micro-features in minority classes. Cross-validation verified robust generalization across unseen tissue samples.

## Publication
If you find this work useful for your research, please cite our conference paper:

> J. Albarracin, F. Cano and A. Cruz-Roa, *"Semantic Segmentation of Tissue in Histopathological Breast Cancer Images Using a U-Net,"* **2025 21st International Symposium on Biomedical Image Processing and Analysis (SIPAIM)**, Pasto, Colombia, 2025, pp. 1-4. 
> **DOI:** [10.1109/SIPAIM67325.2025.11283435](https://doi.org/10.1109/SIPAIM67325.2025.11283435)

## Requirements
- Python 3.8+
- Frameworks & Libraries: TensorFlow, PyTorch, NumPy, OpenSlide, scikit-learn
- Hardware: NVIDIA GPU with at least 16 GB of VRAM recommended (e.g., NVIDIA T4, RTX 3080, or superior)

## Installation & Setup
1. Clone this repository:
   ```bash
   git clone https://github.com/Johan98-dev/histopathology-semantic-segmentation.git

## Acknowledgments
This undergraduate thesis, developed under the EPI (Research Project Student) modality, was carried out within the framework of the research project titled “Implementación de una red de investigación, desarrollo tecnológico e innovación en patología digital (RedPat) soportada por tecnologías de la industria 4.0 en el Meta” [Implementation of a research, technological development, and innovation network in digital pathology (RedPat) supported by Industry 4.0 technologies in Meta], Code BPIN 2019000100060. This project was funded by MinCiencias (the Colombian Ministry of Science, Technology, and Innovation) and the OCAD of the Science, Technology, and Innovation Fund of the General Royalties System.
