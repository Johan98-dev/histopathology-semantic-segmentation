# Segmentación Semántica Multiclase de Imágenes Histopatológicas de Cáncer de Mama

## Descripción
Este proyecto implementa modelos U-Net para la segmentación semántica multiclase de Imágenes de Diapositiva Completa (WSI) de cáncer de mama, utilizando el dataset público **Breast Cancer Semantic Segmentation (BCSS)**. El objetivo es clasificar regiones tisulares en clases como Tumor, Estroma, Infiltrado Linfocítico, Necrosis y Otros, apoyando el análisis patológico computacional.

## Objetivos
- Desarrollar modelos U-Net para segmentación multiclase de WSIs.
- Comparar el rendimiento de modelos con tamaños de entrada de 256x256 y 512x512 píxeles.
- Evaluar la precisión y generalización mediante métricas estándar (Dice, Jaccard, Accuracy).

## Metodología
- **Arquitectura**: U-Net con KimiaNet (basado en DenseNet-121) como backbone preentrenado.
- **Dataset**: BCSS, con WSIs anotadas por expertos.
- **Preprocesamiento**: Extracción de parches de 256x256 y 512x512 píxeles.
- **Entrenamiento**: Validación cruzada K-Fold, optimizador AdamW, función de pérdida Categorical Crossentropy, ajuste fino progresivo de capas.
- **Hiperparámetros**: Tasas de aprendizaje (1x10⁻³ a 1x10⁻⁵), tamaños de lote (8, 10, 12), 18 épocas.
- **Evaluación**: Métricas por clase y micro-average para clases desbalanceadas.

## Resultados
Los modelos lograron una segmentación precisa, con máscaras predichas altamente similares a las reales, especialmente en clases mayoritarias (Tumor, Estroma). El modelo de 512x512 mostró ventajas en clases con mayor contexto espacial, mientras que el de 256x256 fue más eficiente en clases minoritarias. La validación cruzada aseguró generalización robusta.

## Requisitos
- Python 3.8+
- Bibliotecas: TensorFlow, PyTorch, NumPy, OpenSlide, scikit-learn
- Hardware: GPU recomendada (por ejemplo, NVIDIA GTX 1080 o superior)

## Instalación
1. Clona el repositorio:
   ```bash
   git clone https://github.com/[tu-usuario]/[tu-repositorio].git

## Agradecimientos
Este trabajo de grado en modalidad EPI ha sido desarrollado en el marco del proyecto de investigación titulado “Implementación de una red de investigación, desarrollo tecnológico e innovación en patología digital (RedPat) soportada por tecnologías de la industria 4.0 en el Meta”, Código BPIN 2019000100060, financiado por MinCiencias y el OCAD del Fondo de Ciencia Tecnología e Innovación del Sistema General de Regalías.
