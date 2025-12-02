ECG Image Digitization and Signal Extraction
Project Description

    Drive Mounting: The notebook first mounts Google Drive to access necessary data and model weights.
    Path Configuration: Defines base paths for input data (test images, test CSV) and ensures their existence.
    Dependency Import: Imports essential libraries including torch, pandas, numpy, matplotlib, torchvision, and custom modules from the Open-ECG-Digitizer-main project.
    Model Weights: The U-Net models for segmentation and lead identification are loaded from specified paths within Google Drive.

How to Run

    Execute Cells Sequentially: Run all code cells in order.
    Sample Processing: The notebook first processes a small sample of ECG images to demonstrate the pipeline and visualize intermediate results.
    Full Inference: After the sample run, it proceeds to perform full inference on all unique IDs specified in test.csv, generating an output.csv with the extracted signal values.

Key Components

    UNet: Segmentation model for identifying signal, grid, and text regions.
    PerspectiveDetector & Cropper: For correcting image perspective and cropping relevant areas.
    PixelSizeFinder: Determines the pixel-to-mm scale based on the ECG grid.
    SignalExtractor: Extracts raw signal traces from the segmented signal probability map.
    LeadIdentifier: Identifies and organizes the extracted signals into canonical ECG leads.

Output

The final output is output.csv, located at /content/drive/MyDrive/kaggle_data/competitions/physionet-ecg-image-digitization/output.csv. This file contains two columns: id (combining image ID, sample index, and lead name) and value (the digitized signal value in mV).