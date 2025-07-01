# Behavior Cloning-based Active Scene Recognition via Generated Expert Data with Revision and Prediction Method for Domestic Robots

This repository includes the demonstration videos of our proposed method called **Behavior Cloning-based Active Scene Recognition via Generated Expert Data with Revision and Prediction Method for Domestic Robots**. 


# Framework

<p align="center">
<img src="https://github.com/simpleliu66/ASR/blob/main/img/framework.jpg" height= "600" width="800">
</p>


# Demonstration
## Some demos of scene recognition tasks in [**Habitat**](https://aihabitat.org/datasets/hm3d/).
The left window shows the robot's real-time observations, and the right window displays the process and result of active scene recognition.

### task 1
https://github.com/user-attachments/assets/df514b1d-82d7-4b66-acda-f30d6ea252c3

### task 2
https://github.com/user-attachments/assets/6d0aa2de-7ebc-4807-985c-4e30e7314a75

### task 3
https://github.com/user-attachments/assets/71ee0556-fcb7-474e-a94e-7ca60b13a6be

### task 4
https://github.com/user-attachments/assets/0b00e982-6a32-42d7-b077-4ad650587cd8

### task 5
https://github.com/user-attachments/assets/4191c29b-437c-4ff8-8838-a780a80a1867

### task 6
https://github.com/user-attachments/assets/2db0aae6-c766-4dc2-a549-40e5cc92cc62

## Using ASR during robot random exporation
When the scene recognition request (shown in the left top of the window) is **Yes** during the random exporation, the robot needs to recognize the scene using our method. 

### Demo 1
https://github.com/user-attachments/assets/aa68176b-8fdc-4a4b-a69c-0011f17afe45

### Demo 2
https://github.com/user-attachments/assets/95fc9f9c-8103-4909-928e-cb2270e3cf47

## Real-word Robot Demonstration
The proposed method deployed on a Turtlebot 4 to recognize scene in a real-word domestic environment (kitchen).
###  
https://github.com/user-attachments/assets/c738dcbe-a5ab-489e-aaaf-3eaab641fa34


# Getting started
## 1.Install the dependent package for training action model
```
conda create -n train_AM python=3.7.10
conda activate train_AM
pip install -r requirements_for_train_AM.txt
```
Download pre-trained  [T2T_ViT_19](https://drive.google.com/file/d/1P0_-TmtMO58EEXSd-a9AJQz2cvJSQ07c/view?usp=drive_link) model and put it into './vit_model_py/'.

## 2.Download the training data 
Download the [AVDB](https://drive.google.com/file/d/1meYw7VtlPEK6hY9u3U5ttUP8K9bP3USB/view?usp=drive_link) datasetand [expert data](https://drive.google.com/file/d/10CetydhZrBMNSB5uPAY2wl5_eJuN2Oq2/view?usp=drive_link)
Put them into './train_data/'.

## 3.Run the training procedure
```
python train_action_model.py
```

## 4.Install the dependent package for testing
```
conda create -n test_ASR python=3.9.18
conda activate test_ASR
pip install -r requirements_for_test_ASR.txt
```

## 5.Download Habitat testing data
Download  [**Habitat**](https://aihabitat.org/datasets/hm3d/) data and extract all files in '/val' and 'hm3d_annotated_basis.scene_dataset_config.json' in './Habitat - Matterport 3D Research Dataset/'.

## 6.Run the testing procedure
Here are the well-trained [action model](https://drive.google.com/file/d/136fKyi4P2D6HxKkzErWSRa5QlsjAV4UM/view?usp=drive_link) and [SR model](https://drive.google.com/file/d/1_AnUc_ds88Hu-KNhJH4vcWUUKDbFqJOt/view?usp=drive_link) tested in the paper. You can download them in './well_trained_model/' for testing.
```
python ASR_test.py
```
