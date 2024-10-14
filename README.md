# 3D Anomaly Detection Methods
Welcome to the **3D Anomaly Detection** repository! This GitHub repository is dedicated to collecting, organizing, and evaluating various methods used for 3D anomaly detection. If you find this repository helpful, please consider giving it a ⭐ Star!
We organize the repository into the following sections: 

- [Datasets](##Datasets)
- [Feature Embedding Methods](##Feature-Embedding-Methods)
- [Reconstruction Methods](#Reconstruction-Methods)
- [Traditional Methods](#Traditional-method)
- [LLM Methods](#LLM-method)


## Datasets

### 1. MvTec3D-AD
- **Year**: 2021
- **Description**: A real-world dataset with depth and RGB images of common objects like food and tools. The dataset is aligned, making it easier to use for anomaly detection tasks. Depth maps can be converted to 3D point clouds.
- **Categories**: 10 object classes, each with 3-5 types of anomalies. Point clouds contain 10K-30K points.
- **Link**: [MvTec 3D-AD Dataset](https://www.mvtec.com/company/research/datasets/mvtec-3d-ad)

### 2. Eyecandies
- **Year**: 2022
- **Description**: A synthetic dataset that simulates industrial processes with RGB and depth images of candies under various lighting conditions and assembly line backgrounds. It provides depth maps but does not support conversion to 3D point clouds.
- **Categories**: 10 object classes with 3 types of anomalies.
- **Link**: [Eyecandies Dataset (Github)](https://eyecan-ai.github.io/eyecandies/download)

### 3. PAD
- **Year**: 2023
- **Description**: The Multi-Pose Anomaly Detection (MAD) dataset is designed for pose-agnostic 3D anomaly detection, featuring 4K views of 20 complex-shaped Lego toys in various poses. It includes both simulated and real-world 3D anomalies, enabling the development of methods that detect anomalies regardless of object pose, addressing the challenge of inconsistent pose alignment between training and test samples.
- **Categories**: 20 object classes with 3 types of anomalies.
- **Link**: [PAD Dataset (Github)](https://github.com/EricLee0224/PAD)
- 
### 4. Real3D-AD
- **Year**: 2023
- **Description**: A realistic dataset obtained from scanned industrial and everyday products. The dataset provides large point clouds, with training sets having more points than the test sets, making it more challenging for anomaly detection.
- **Categories**: 12 object classes, each with 2 types of anomalies. Point clouds range from 35K to 780K points.
- **Link**: [Real3D-AD Dataset (Github)]([https://github.com/m-3lab/real3d-ad)

### 5. Anomaly-ShapeNet
- **Year**: 2023
- **Description**: A synthetic 3D dataset based on the ShapeNet dataset, augmented by sculpting anomalies into original 3D models. This dataset focuses on testing the robustness of models by reducing point density.
- **Categories**: 40 object classes with 6 types of anomalies. Point clouds contain 8K-30K points.
- **Link**: [Anomaly-ShapeNet Dataset (Github)](https://github.com/chopper-233/anomaly-shapenet)

## Feature-Embedding-Methods

### 1. PatchCore
- **Description**: An extension of a 2D anomaly detection method, PatchCore uses a memory bank constructed from features to detect anomalies in 3D point clouds.
- **Evaluation**: The method shows limited robustness when applied to 3D data, as irregular point cloud structures make it difficult for the memory bank to accurately represent normal features across different object regions.

### 2. Reg-AD
- **Description**: Reg-AD performs point cloud registration followed by anomaly detection through dual testing using both point coordinates and PointMAE transfer learning. The final decision is based on combining both test results.
- **Evaluation**: As the first attempt at using a memory bank on a real 3D dataset, Reg-AD shows promise, but its dependence on registration introduces sensitivity to rotation, suggesting future work should focus on improving representations with rotational invariance.

### 3. Group3AD
- **Description**: Group3AD improves upon Reg-AD by clustering feature space into multiple groups and aligning them geometrically. This allows for better characterization of point cloud features before detecting anomalies.
- **Evaluation**: By clustering the feature space, Group3AD achieves more refined feature representation, which leads to improved performance in anomaly detection compared to Reg-AD.

### 4. M3DM
- **Description**: M3DM aims to align RGB and 3D information for anomaly detection. It leverages contrastive learning and builds multiple memory banks for 3D and RGB information using transfer learning techniques such as PointMAE and ViT.
- **Evaluation**: While M3DM offers an effective approach for integrating multimodal information, the effectiveness of the fused modalities remains questionable, warranting further exploration into more sophisticated fusion strategies.

### 5. CPMF
- **Description**: CPMF enhances 3D anomaly detection by generating 2D projections of the 3D object and aligning the surface views with 3D structures to improve the detection of anomalies.
- **Evaluation**: Although it provides an innovative approach to bridging 2D and 3D information, experimental results are inconsistent, and the code implementation does not fully align with the paper, which raises concerns about reproducibility.

### 6. Looking3D
- **Description**: Looking3D focuses on aligning 2D and 3D anomalies. It introduces a large dataset called BrokenChairs-180K, which pairs 180,000 2D images of defective objects with 3D shapes, enabling multimodal anomaly detection.
- **Evaluation**: This method provides a significant contribution by emphasizing the relationship between 2D and 3D defects. However, the scale and complexity of the dataset suggest that this work may be geared towards preparing for large-scale model development in the future.
---

## Reconstruction-Methods

### Reconstruction in Feature Space

### 1. ShapeGuided
- **Description**: ShapeGuided utilizes both shape and appearance experts to jointly predict 3D and RGB anomalies. The method reconstructs signed distance functions (SDF) in the feature space using PointNet embeddings.
- **Evaluation**: As an initial attempt at feature-space reconstruction, ShapeGuided benefits from the alignment in the MvTec3D-AD dataset, which simplifies the reconstruction process. However, its applicability to more complex datasets remains uncertain.

---

### Reconstruction in Raw Point Clouds

### 1. IMRNet
- **Description**: IMRNet, based on modifications of PointMAE, iteratively reconstructs masked point clouds, rebuilding 40% of the points at each iteration. The final anomaly detection is done by comparing the reconstructed point cloud to the original.
- **Evaluation**: This method marks an important first step in iterative point cloud reconstruction for anomaly detection. However, the feasibility of achieving highly accurate reconstructions, especially in large-scale datasets, remains in question.

### 2. R3D-AD
- **Description**: R3D-AD employs a diffusion model inspired by heat diffusion to progressively refine point cloud reconstructions. The method compares full-mask reconstructions with the original point cloud to identify anomalies.
- **Evaluation**: While R3D-AD builds on ideas introduced by IMRNet and achieves promising results, the simplicity of relying solely on PointNet and distillation processes to achieve high performance has been met with skepticism, indicating a need for more rigorous validation.

---

## Traditional-method

### 1. BTF
- **Description**: BTF (Basic Tensor Field) is an analytical method that emphasizes the importance of 3D structure in anomaly detection. It directly computes feature descriptors using mathematical formulas without the need for training.
- **Evaluation**: As a traditional method, BTF underscores the critical role of 3D structural information in detecting anomalies. However, it lacks cross-sample robustness, which is a limitation of non-learning-based approaches in modern anomaly detection tasks.


## LLM-method

### 1. PointAD
- **Description**: PointAD leverages CLIP for zero-shot anomaly detection by projecting 3D structures into 2D for easier anomaly recognition, based on 2D understanding.
- **Evaluation**: Although the use of 2D projections can simplify the anomaly detection task, it inherently leads to a loss of 3D structural information, which limits the method's effectiveness in fully leveraging 3D data.

