# Retinal imaging analysis - Recognition

## ToDo List
- W26Y2022
  - [x] Add code to download the dataset in the Colab notebook
  - [x] Select model with the highest validation accuracy and save it 
  - [x] Perform Image Augmentation before training
  - [ ] Start writing Chap 1 (Introduction)
  - [ ] Replicate existing implementations (exec. code or manually reproducting the architecture) 
- W25Y2022
  - [x] Replace MESSIDOR with MESSIDOR-2
  - [x] Review and replicate a simple CNN implementation
  - [x] EDA: Analyse and address class imbalancing
  - [x] Migrate implementation from TF to PyTorch
- W24Y2022
  - [x] Update presentation [[link](https://drive.google.com/file/d/1OGX0bOEpyr_C9Rqg5B8KhPnTC-lmHrdR/view?usp=sharing)]
  - [x] Image preprocessing (APTOS2019 and MESSIDOR)
- W23Y2022
  - [x] Set up development environment and discuss availability of technical resources
- W22Y2022
  - [x] Review existing implementations for DR detection
  - [x] Analyse available datasets
- W21Y2022
  - [x] Prepare presentation [[link](https://drive.google.com/file/d/1x6Iau4zNEIXR8FRm3Yvq1iYo9vNtHmaH/view?usp=sharing)]
  
---
## Notes from supervisor
- Use PyTorch instead of TF/Keras, for the sake of simiplicity (similar to NumPy)
- To improve the model performance [[mawady/colab-recipes-cv](https://github.com/mawady/colab-recipes-cv)]
  - Save best model while training
  - Do data augmentation
  - Use pre-trained model
  - Use weighted sampler for imbalanced data
  - Use weighted metric for evaluation (i.e. balanced acc)
- Find more papers with implementations [[Diabetic Retinopathy Detection](https://paperswithcode.com/task/diabetic-retinopathy-detection)] [[Diabetic Retinopathy Grading](https://paperswithcode.com/task/diabetic-retinopathy-grading)]
- XAI in Retinal
  - Muddamsetty, Satya M., Mohammad NS Jahromi, and Thomas B. Moeslund. "Expert level evaluations for explainable AI (XAI) methods in the medical domain." International Conference on Pattern Recognition. Springer, Cham, 2021.
  - Kind, Adrian, and George Azzopardi. "An explainable AI-based computer aided detection system for diabetic retinopathy using retinal fundus images." International Conference on Computer Analysis of Images and Patterns. Springer, Cham, 2019.
  - Niu, Yuhao, et al. "Explainable diabetic retinopathy detection and retinal image generation." IEEE Journal of Biomedical and Health Informatics 26.1 (2021): 44-55.
- Idea: XAI (CNN vs ViT vs ConvNext)
- Terms to search about:
 - vision transformer diabetic retinopathy
 - GradCAM
- LaTex for macOS
  - Compiler
    - https://formulae.brew.sh/cask/mactex
    - https://formulae.brew.sh/cask/basictex
  - Text Editor
    - https://www.texstudio.org
    - https://www.xm1math.net/texmaker/

---

## Experiments
- **Exploratory Data Analysis**: [[code](https://github.com/mawady/msc-retinalrecog/blob/main/EDA.ipynb)]
- **Image preprocessing**: [[code](https://github.com/mawady/msc-retinalrecog/blob/main/Preprocessing.ipynb)]
- **AlexNet training**: basic implementation of a classifier using AlexNet. This allows to fix any problems in the preprocessing of data. [[code](https://github.com/mawady/msc-retinalrecog/blob/main/Training_AlexNet.ipynb)] 

---

## Online Implementations
### Diabetic Retinopathy Detection
- Tymchenko, B., Marchenko, P., Spodarets, D., Deep Learning Approach to Diabetic Retinopathy Detection (2020) [[code](https://github.com/debayanmitra1993-data/Blindness-Detection-Diabetic-Retinopathy-)]
- Mathis, A., Brüggemann†, S., Kaggle Diabetic Retinopathy Detection Team o_O solution (2015) [[code](https://github.com/sveitser/kaggle_diabetic)]
- EyeNET [[code](https://github.com/gregwchase/eyenet)]


---

## Related work
### Generic Reviews
- [x] Haraburda, P., Dabała, Ł. (2022). Eye Diseases Classification Using Deep Learning. In: Sclaroff, S., Distante, C., Leo, M., Farinella, G.M., Tombari, F. (eds) Image Analysis and Processing – ICIAP 2022. ICIAP 2022. Lecture Notes in Computer Science, vol 13231. Springer, Cham. [[link](https://doi.org/10.1007/978-3-031-06427-2_14)]
- [x] Tsiknakis N, Theodoropoulos D, Manikis G, Ktistakis E, Boutsora O, Berto A, Scarpa F, Scarpa A, Fotiadis DI, Marias K. Deep learning for diabetic retinopathy detection and classification based on fundus images: A review. Comput Biol Med. 2021 Aug;135:104599 Epub 2021 Jun 25. PMID: 34247130 [[link](10.1016/j.compbiomed.2021.104599.)]
- [x] Badar, M., Haris, M., Anam, F., Application of deep learning for retinal image analysis: A review, Computer Science Review 35 (2020): 100203 [[link](https://doi.org/10.1016/j.cosrev.2019.100203)]

### Interpretability
- [x] Niu, Y., et al., Explainable Diabetic Retinopathy Detection and Retinal Image Generation, IEEE Journal of Biomedical and Health Informatics (2021) [[link](https://doi.org/10.48550/arXiv.2107.00296)]
- [ ] Muddamsetty, S. M., Jahromi, M. N. S., Moeslund, T. B., Expert level evaluations for explainable AI (XAI) methods in the medical domain, Pattern Recognition. ICPR International Workshops and Challenges (2021) [[link](https://doi.org/10.1007/978-3-030-68796-0_3)]

### Preprocessing of fundus images
- [x] Hernandez-Matas, C., Argyros, A. A., Zabulis, X., Retinal image preprocessing, enhancement, and registration, Elsevier and MICCAI Society Book Series, Computational Retinal Image Analysis, Academic Press, Chapter 4 - Pages 59-77 (2019)
[[link](https://doi.org/10.1016/B978-0-08-102816-2.00004-6)]

---

## Datasets

| Dataset     | # Samples   | Description |
| ----------- | ----------- | ----------- |
| [Kaggle EyePACS](https://www.kaggle.com/c/diabetic-retinopathy-detection)     | > 80.000       | Fundus images for **DR** detection (graded 0-4)      |
| [Kaggle APTOS 2019](https://www.kaggle.com/competitions/aptos2019-blindness-detection/overview)   | 5590        | Fundus images for **DR** detection (graded 0-4)       |
| [MESSIDOR](https://www.adcis.net/en/third-party/messidor/)   | 1200       | Fundus images for **DR** detection (graded 0-3) and assessment of **ME** risk (graded 0-2)         |
| [MESSIDOR-2](https://www.adcis.net/en/third-party/messidor2/) [Kaggle grading](https://www.kaggle.com/datasets/google-brain/messidor2-dr-grades)  | 1748       | Fundus images for **DR** detection (graded 0-4) and assessment of **ME** risk (graded 0-2)         |
| [DDR](https://github.com/nkicsl/DDR-dataset)   | 12522       | Fundus images for **DR** detection (graded 0-5)          |
| [STARE](https://cecas.clemson.edu/~ahoover/stare/)   |        |  |
| [REFUGE](https://ieee-dataport.org/documents/refuge-retinal-fundus-glaucoma-challenge)   |  1200      | Fundus images for **G** detection  |
| [RIM-ONE](https://github.com/miag-ull/rim-one-dl)   |  313      | Fundus images for **G** detection  |
| [ODIR](https://www.kaggle.com/datasets/andrewmvd/ocular-disease-recognition-odir5k)   |  5000      | Fundus images for detection of: Diabetes (D), Glaucoma (G), Cataract (C), Age related Macular Degeneration (A), Hypertension (H), Pathological Myopia (M), Other diseases/abnormalities (O) |


