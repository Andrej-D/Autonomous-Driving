# Autonomous-Driving

This project implements a deep learning pipeline for behavioral cloning in autonomous driving. It trains a convolutional neural network (CNN) to predict steering angles from input images captured by a car’s front-facing camera.

## Project Structure
```
Autonomous Driving/
│
├── clean_csv.py          # Script to clean up or preprocess driving_log.csv
├── drive.py              # Script to run the trained model in a simulator
├── driving_log.csv       # Dataset log file containing image paths + steering data
├── fix_csv_paths.py      # Utility to fix image paths in the CSV file
├── model.py              # Model architecture & training pipeline
├── model.h5              # Pretrained model weights
├── requirements.txt      # Python dependencies
└── utils.py              # Helper functions (data loading, augmentation, etc.)
```

## Features
- Preprocess and clean driving data logs  
- Train a CNN model to predict steering angles  
- Run a trained model in real-time in the simulator  
- Support for fixing broken paths in CSV datasets  

## Requirements
Install the dependencies:
```bash
pip install -r requirements.txt
```
Recommended:
- Python 3.7+  
- TensorFlow/Keras  
- NumPy, Pandas, OpenCV  

## Usage
### 1. Prepare Data
Ensure your dataset (images + `driving_log.csv`) is in the correct format. You can use:
```bash
python clean_csv.py
python fix_csv_paths.py
```
to clean and fix CSV paths.

### 2. Train the Model
```bash
python model.py
```
This will:
- Load and preprocess data  
- Train the CNN on the dataset  
- Save the trained weights to `model.h5`  

### 3. Run the Model in Simulator
```bash
python drive.py model.h5
```
This launches the driving script using the trained model.

## Customization
- Modify **`model.py`** to change the architecture or training parameters  
- Adjust **`utils.py`** for data augmentation techniques  

## Notes
- The provided `model.h5` is already trained and can be directly used with `drive.py`  
- If your CSV paths are broken due to directory changes, run `fix_csv_paths.py`  
- Ensure your simulator version matches the behavioral cloning project setup  
