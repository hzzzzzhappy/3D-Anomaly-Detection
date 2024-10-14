# 3D Anomaly Detection Methods
Welcome to the **3D Anomaly Detection** repository! This GitHub repository is dedicated to collecting, organizing, and evaluating various methods used for 3D anomaly detection. If you find this repository helpful, please consider giving it a ⭐ Star!
We will organize it into the following forms: data sets (including the introduction and now SOTA), feature embedding methods, and reconstruction methods.

## Datasets

### 1. MvTec3D-AD
- **Year**: 2021
- **Description**: A real-world dataset with depth and RGB images of common objects like food and tools. The dataset is aligned, making it easier to use for anomaly detection tasks. Depth maps can be converted to 3D point clouds.
- **Categories**: 10 object classes, each with 3-5 types of anomalies. Point clouds contain 10K-30K points.
- **Link**: [MvTec 3D-AD Dataset]([https://www.mvtec.com/company/research/datasets/mvtec-3d-ad](https://www.mvtec.com/company/research/datasets/mvtec-3d-ad)

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
- **Link**: [Anomaly-ShapeNet Dataset (Githbu)](https://github.com/chopper-233/anomaly-shapenet)
