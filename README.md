# DEEP LEARNING BASED BRAIN HAEMORRHAGE DETECTION USING CT IMAGES

## Overview

Intracranial hemorrhage (ICH) is a serious and life-threatening medical condition requiring rapid diagnosis. This project leverages deep learning, specifically YOLOv8, for detecting and classifying ICH in non-contrast head CT scans. By utilizing advanced pre-processing techniques with the `pydicom` library and training with the Brain Hemorrhage Extended (BHX) dataset, our model achieves robust performance in localizing and classifying hemorrhages.

## Key Features
- **Automated Hemorrhage Detection:** Identifies six types of hemorrhages from CT images.
- **YOLOv8-based Architecture:** Utilizes the latest YOLO version for superior performance.
- **DICOM Image Processing:** Pre-processed using `pydicom` for enhanced image quality.
- **Efficient Training:** Trained on the CQ500 dataset with bounding box annotations.

## Dataset
We used the **CQ500 dataset** from Qure.ai, which includes:
- **491 head CT scans**
- **205 positive hemorrhage cases**
- Images with varying characteristics (thick-slice, thin-slice, bone-filtered, contrast-enhanced, and soft-tissue non-contrast-enhanced series)
- Annotations by expert neuroradiologists

### Hemorrhage Categories
1. Intraparenchymal
2. Subarachnoid
3. Intraventricular
4. Epidural
5. Subdural
6. Chronic Subdural Hematoma

## Preprocessing
- **Image-UID Mapping:** Used SOPUID from DICOM metadata to match labels.
- **Windowing & Normalization:** Adjusted intensity values to improve contrast and brightness.
- **Noise Reduction:** Applied dilation operation for artifact suppression.
- **Format Conversion:** Converted DICOM to JPG (YOLOv8-compatible format).
- **Data Split:** 90% training, 10% validation.

## Model Training
- **Pre-trained Weights:** Utilized YOLOv8x with OpenImagesV7 dataset.
- **Epochs:** 50 (limited due to resource constraints)
- **Bounding Box Extrapolation:** Improved localization accuracy.

## Results
### Confusion Matrix
- Model performed well in detecting true positives.
- Higher false positives observed in Subarachnoid and Subdural categories.

### Performance Metrics
| Metric  | Value  |
|---------|--------|
| Precision | High  |
| Recall    | High  |
| F1-Score  | Good  |

![image](https://github.com/user-attachments/assets/99a5080b-8d4e-4e86-8feb-1c8c74506186)
Normalized confusion matrix

![image](https://github.com/user-attachments/assets/5abffc3e-bb95-40f9-9109-8f41bfa15d4d)
training loss, validation loss, precision, recall.

### Visual Comparisons
- True Labels vs. Predicted Results indicate strong detection capability.

## Future Work
- **User Interface:** Develop an image upload system with treatment suggestions.
- **Improved Bounding Box Extrapolation:** Reduce misalignment in bounding boxes.
- **Expanded Classification:** Include more brain abnormalities beyond ICH.
- **Cross-Modality Analysis:** Extend to MRI for comprehensive neuroimaging analysis.

## Conclusion
This project demonstrates the potential of YOLOv8 in medical imaging, offering real-time and accurate hemorrhage detection. Future improvements could enhance clinical usability and diagnostic reliability.

## Contributors
- **Tinal Abeygunathilaka**
- https://github.com/tinal28
- **Himanshi De Silva**
- https://github.com/HimanshiDeSilva

## References
1. Chilamkurthy S et al. (2018). Deep learning for detecting critical findings in head CT scans. *The Lancet.*
2. Heit, J. J. et al. (2017). Imaging of Intracranial Hemorrhage. *Journal of Stroke.*
3. Weicheng K et al. (2019). Expert-level detection of ICH using Deep Learning. *PNAS.*
4. PhysioNet. (2020). BHX Dataset.
5. Ultralytics YOLOv8 Documentation.
