# [2024 ETRI 휴먼이해 AI경진대회 대상수상 모델](https://aifactory.space/task/2790/overview)
- [PixleepFlow: A Pixel-Based Lifelog Framework for Predicting Sleep Quality and Stress Level](https://www.arxiv.org/abs/2502.17469)
<img width="710" alt="image" src="https://github.com/user-attachments/assets/ba5cc2fe-a753-4734-940b-4ecd6ce67af8" />

![image](https://github.com/user-attachments/assets/7b271186-6864-43b6-8e77-8071cab8a3ae)



#### Repository Overview
Welcome to the GitHub repository for Team Tongmotjahaotdog's submission to the 3rd ETRI Human Understanding AI Competition in 2024. This repository contains all the necessary source codes and instructions for reproducing our model and results. Our approach includes processing and synchronizing various sensor data to predict human activities and conditions accurately.

#### Team Name: Tongmotjahaotdog
- **Date**: June 28, 2024

#### Repository Structure:
The overall folder structure is depicted in the diagram below:

```
ETRLHumanUnderstanding/
│
├── datasets/
│   ├── val_datasets/
│   ├── test_datasets/
│   ├── image_datasets/
│   └── raw_datasets/
│       ├── valid_datasets/
│       └── test_datasets/
│           ├── acc/
│           ├── activity/
│           ├── hr/
│   └── raw_datasets_all_sensor/
│       ├── valid_datasets/
│           ├── acc/
│           ├── activity/
│           ├── hr/
│           ├── step/
│           ├── light/
│           ├── gps/
│       └── test_datasets/
│           ├── acc/
│           ├── activity/
│           ├── hr/
│           ├── step/
│           ├── light/
│           ├── gps/
│
├── notebooks/
│   ├── preprocessing/
│   ├── training/
│   └── inference/
│
├── logs/
├── models/
└── result/
```

#### Source Code Execution Order:
1. Move `val_datasets` and `test_datasets` to `./datasets` folder.
2. Execute all 4 preprocessing notebooks (for 5-channel and 11-channel data sets).
3. Run 2 training notebooks.
4. Execute 2 inference notebooks.
5. Run `submit.ipynb` to generate the `submit.csv` file, which is the final output.

### Installation and Requirements
- Clone the repository:
  ```bash
  git clone https://github.com/Tongmotjahaotdog/ETRI2024.git
  ```
- Install required libraries:
  ```bash
  pip install -r requirements.txt
  ```

### Dataset
The datasets provided by ETRI are processed without including the year in the training and validation datasets as per the competition rules. Please note that the datasets are pre-split according to provided instructions, including separate folders for validated and test datasets.

### How to Run
- **Preprocessing**
  ```bash
  jupyter notebook preprocessing_valid.ipynb
  jupyter notebook preprocessing_test.ipynb
  jupyter notebook preprocessing_valid_all_sensor.ipynb
  jupyter notebook preprocessing_test_all_sensor.ipynb
  ```
- **Training**
  ```bash
  jupyter notebook train_11channel(resnext101).ipynb
  jupyter notebook train_5channel(seresnext101).ipynb
  ```
- **Inference**
  ```bash
  jupyter notebook inference_5channel(seresnext101).ipynb
  jupyter notebook inference_11channel(resnext101).ipynb
  ```
- **Submission**: Finally, run the `submit.ipynb` notebook to compile results into `submit.csv`.

### Methodology
Our methodology involves synchronization of sensor data at different frequencies and converting them into a uniform 1Hz time-series data before processing them into image format. This allows us to leverage convolutional neural networks (CNNs) for feature extraction and subsequent activity prediction.

### Results and Discussion
Our models are based on variations of ResNet and SEResNeXt, which have shown robust performance in handling time-series image data derived from synchronized sensor readings. Detailed analysis and comparison of model performance are available in the `models/` directory.

### Future Work
We aim to explore more sophisticated data augmentation techniques and potentially leverage multi-view learning frameworks to enhance model generalizability and performance.

### Contributors
- Yonghoon Na
- Seunghoon Oh
- Seongji Ko

For any additional information or queries, please open an issue in this repository.
