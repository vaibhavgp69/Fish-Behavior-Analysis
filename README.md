# Fish-Behavior-Analysis

In aquaculture, behavior analysis observes fish swimming, gill movements and feeding interactions to understand physiological or environmental factors impacting their behavior.
Studying fish behavior helps us understand their feeding cues, motivations and preferences to optimize the aquaculture harvest.

## Problem Statement -> Need For Efficient Behavioral Analysis
- Ammonia Buildup
- Reduced fish growth and health
- Aggression among fish

The solution here uses a custom trained YOLOV10S model to detect fishes and methods like tracking, delauney triangulation are being used to classify the feeding behaviour of fishes.

## Dataset Link: https://app.roboflow.com/sudeep-p8zsb/aquaculture2024/6
The above dataset has been completletly annotated from scratch.

## Instructions to run the Code

- Open the gpu-train-yolov10-trial.ipynb file
- Make sure you have created a conda env using the commands :
  conda create env -o pt python=3.10

  conda activate pt

  pip install requirements.txt

- Now you can freely run the code from notebook, use the dataset link to load the dataset for training if needed or the Data link provided in ./data/data_link.md and ./Feeding_data/feeding_data_link.md

## GPU used : 
![image](https://github.com/user-attachments/assets/8c439098-e1bc-4958-896d-8ef9b86164ea)

## Fish Detection & Analysis results

### Object detection
![20240718-1444-56 6404381-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/971ccf1c-2645-41ae-a183-eb9f91d730e5)

### Tracking :

![tracking](https://github.com/user-attachments/assets/f782194a-ff94-4f1d-bce6-7dcc345a7c03)

### Delaunay Triangulation :

![delauney](https://github.com/user-attachments/assets/0e9a29ca-3c8e-4302-8afd-218f86837c7b)

## Results:

### Training results for different YOLOV10 models from S to L:
Accuracy results were best shown for Yolov10_small version for our dataset and size
![image](https://github.com/user-attachments/assets/38c3acb2-68a7-4206-804e-e18ca7ce72b2)
![image](https://github.com/user-attachments/assets/56480668-962c-485e-ad3d-84646cfbe6b9)

### Training on Custom Dataset
- Trained custom data on YOLOv10 small model.
- Observed  better Accuracy metrics and stable detection , initial loss convergence, followed by increased validation bounding box loss.
- Multiple epochs were run , best model in these epochs was saved.
![image](https://github.com/user-attachments/assets/700c53a9-e30f-4263-8351-6ef3515b0608)
![image](https://github.com/user-attachments/assets/eb9a6582-19b1-4c49-bb56-ee934f5b27f6)

### Analysing the Data
- **Average Speed** - Determining the mean speed of the fishes within each tank.
- **Average Flocking Index** - Measuring the degree of cohesive movement and interaction among the fishes.
- **Average Triangle Area** - Calculating the average area formed by triplets of fishes, indicating spatial distribution.
- **Average Edge Length** - Assessing the average length of edges connecting fishes, reflecting the overall density and spread.
  
![image](https://github.com/user-attachments/assets/001faffe-3646-4b30-a158-db6da9d66887)
Flocking Index is more for well-fed fishes since they group together more , while hungry fish search for food and are separated .
Average Triangle Area gives information about how spread out the fishes are , despite their grouping or flocking index.

![image](https://github.com/user-attachments/assets/51acff18-a9d2-4b2c-badd-41ebe4284250)
Less Difference in Edge length since it is subjective to individual fish.
Hungry fishes are more explorative , and hence higher speed values are observed.












  


