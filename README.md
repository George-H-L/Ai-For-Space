# Satellite Land-Cover Classification (EuroSAT)

This project is a deep learning pipeline for classifying satellite imagery using the EuroSAT dataset. We wanted to see if building a massive model actually helps with small 64x64 images, or if data augmentation is the real secret to high accuracy.
Confusion Matrices
<img width="2426" height="716" alt="Screenshot 2026-04-27 015716" src="https://github.com/user-attachments/assets/a0fec08d-b3c8-40c5-a70a-5c407cba7375" />
Results
<img width="849" height="1112" alt="Screenshot 2026-04-27 020044" src="https://github.com/user-attachments/assets/b04938d1-5868-4e2e-b278-77100ffe0e38" />


## What is in here?
The project is split into two main folders:

* **/data**: Preprocessing scripts to get the EuroSAT images ready.
* **/notebooks**: This is where the actual work happens.
    * `BaselineModel.ipynb`: Our custom ResNet18 (the lightweight version).
    * `resnet50_model.ipynb`: The standard ResNet50.
    * `resnet50_model_augmented.ipynb`: The ResNet50 trained with our rotation/color jittering pipeline.
    * `evaluation.ipynb`: **Run this one** to see the final comparison and graphs.
    * `*.pth` files: The saved weights so you don't have to wait hours for the models to train.

## How to run it
We set this up so the marker can just click run and see the results immediately.

1. **Check your libraries**: You'll need `torch`, `torchvision`, `matplotlib`, `seaborn`, and `sklearn` installed in your environment.
2. **Run the Preprocessing**: If the data isn't ready, run the scripts in `/data` first.
3. **Run the Evaluation**: Open `notebooks/evaluation.ipynb` and click **"Run All"**. 

The notebook uses relative paths, so as long as you keep the folders together, everything will load automatically.

## The Results
We managed to hit a peak accuracy of **97.88%** with the Augmented ResNet50. 

| Model | Setup | Accuracy |
| :--- | :--- | :--- |
| **ResNet18** | Standard | **96.84%** |
| **ResNet50** | Standard | **96.89%** |
| **ResNet50** | **Augmented** | **97.88%** |

### Key Takeaway
Upgrading from ResNet18 to ResNet50 only gave us a tiny 0.05% boost at first. It turns out the deeper model was just "data-starved." Once we added the augmentation pipeline, the accuracy jumped significantly.

## The Team
Ehsan, Oliver, Luca, George, Tausifraza
