# Fish Behavior Analysis in Aquaculture

Behavior analysis in aquaculture involves observing fish swimming patterns, gill movements, and feeding interactions to understand the physiological and environmental factors impacting their behavior. Studying fish behavior helps us comprehend their feeding cues, motivations, and preferences, optimizing the aquaculture harvest.

## Problem Statement: Need for Efficient Behavioral Analysis

- **Ammonia Buildup**
- **Reduced Fish Growth and Health**
- **Aggression Among Fish**

## Solution

A custom-trained YOLOv10s model is used to detect fish. Methods like tracking and Delaunay triangulation classify the feeding behavior of fish.

## Dataset

The dataset has been completely annotated from scratch.

[Dataset Link](https://app.roboflow.com/sudeep-p8zsb/aquaculture2024/6)

## Instructions to Run the Code

1. Open the `gpu-train-yolov10-trial.ipynb` file.
2. Create a conda environment using the commands:

    ```bash
    conda create env -o pt python=3.10
    conda activate pt
    pip install -r requirements.txt
    ```

3. Run the code from the notebook. Use the dataset link to load the dataset for training if needed or refer to the data links provided in `./data/data_link.md` and `./Feeding_data/feeding_data_link.md`.

## GPU Used

![image](https://github.com/user-attachments/assets/8c439098-e1bc-4958-896d-8ef9b86164ea)

## Fish Detection & Analysis Results

### Object Detection

![20240718-1444-56 6404381-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/971ccf1c-2645-41ae-a183-eb9f91d730e5)

### Tracking

![tracking](https://github.com/user-attachments/assets/f782194a-ff94-4f1d-bce6-7dcc345a7c03)

### Delaunay Triangulation

![delauney](https://github.com/user-attachments/assets/0e9a29ca-3c8e-4302-8afd-218f86837c7b)

## Results

### Training Results for Different YOLOv10 Models (S to L)

- The accuracy results were best for the YOLOv10_small version for our dataset and size.

![image](https://github.com/user-attachments/assets/38c3acb2-68a7-4206-804e-e18ca7ce72b2)
![image](https://github.com/user-attachments/assets/56480668-962c-485e-ad3d-84646cfbe6b9)

### Training on Custom Dataset

- Trained custom data on the YOLOv10 small model.
- Observed better accuracy metrics and stable detection, initial loss convergence, followed by increased validation bounding box loss.
- Multiple epochs were run, and the best model in these epochs was saved.

![image](https://github.com/user-attachments/assets/700c53a9-e30f-4263-8351-6ef3515b0608)
![image](https://github.com/user-attachments/assets/eb9a6582-19b1-4c49-bb56-ee934f5b27f6)

### Analyzing the Data

- **Average Speed**: Determining the mean speed of the fish within each tank.
- **Average Flocking Index**: Measuring the degree of cohesive movement and interaction among the fish.
- **Average Triangle Area**: Calculating the average area formed by triplets of fish, indicating spatial distribution.
- **Average Edge Length**: Assessing the average length of edges connecting fish, reflecting the overall density and spread.

![image](https://github.com/user-attachments/assets/001faffe-3646-4b30-a158-db6da9d66887)

- Flocking Index is higher for well-fed fish since they group together more, while hungry fish search for food and are separated.
- Average Triangle Area provides information about how spread out the fish are, despite their grouping or flocking index.

![image](https://github.com/user-attachments/assets/51acff18-a9d2-4b2c-badd-41ebe4284250)

- Less difference in Edge Length since it is subjective to individual fish.
- Hungry fish are more explorative, hence higher speed values are observed.
