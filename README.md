# parking-space-counter

The Parking Space Detector is a computer vision-based project designed to automatically detect available and occupied parking spaces in real-time using video feed input. It uses machine learning models and image processing techniques to analyze parking spots and determine whether they are empty or filled.



![Parking](https://github.com/user-attachments/assets/cd4f8792-e91e-46c0-9afa-2f2be643107b)


## data
Dataset used in this projec is available at https://drive.google.com/drive/folders/1kBYviUCS3I_KgbkYi-djI4PqdwO51AS6?usp=sharing




## Features

1) Real-Time Detection: Continuously monitors a parking lot using a video feed to determine the availability of parking spaces.
2) Automated Spot Recognition: Identifies individual parking spots using a mask and analyzes their status (empty or occupied).
3) Visual Output: Highlights available spots in green and occupied spots in red on the video feed.
4) Customizable: Easily adaptable to different parking lot layouts by adjusting the mask and model.


## Requirements
To run this project, you'll need the following Python packages:

    opencv-python==4.6.0.66
    scikit-learn==1.1.3
    pandas==1.5.1
    Pillow==9.3.0
    scikit-image==0.17.2
    matplotlib==3.6.2


## Installation
Clone the repository:

    git clone https://github.com/Tupsamundarsachin/parking-space-detector.git
    cd parking-space-detector


## Create a virtual environment and activate it:

    python3 -m venv venv
    source venv/bin/activate

    
## Install the required dependencies:

    pip install -r requirements.txt

## Prepare the Mask:

The system requires a mask to identify parking spaces. This mask should be a binary image where the parking spots are marked.
Place the mask image in the correct directory and update the path in the main.py script.



## Run the Application:

    python main.py
The application will start processing the video feed from the specified path, analyzing each parking spot in real-time.
View Results:

The application will display the video feed with parking spots highlighted. Available spots are shown in green, and occupied spots are shown in red.
The total number of available spots is displayed on the screen.

## Project Structure

main.py: The main script that handles video processing, parking spot detection, and visualization.

utils.py: Contains utility functions for parking spot detection and classification.

model.p: The pre-trained machine learning model used to classify parking spots as empty or occupied.

mask_1920_1080.png: The binary mask image used to identify the locations of parking spots in the video.


## How It Works
Parking Spot Detection: The get_parking_spots_bboxes function in utils.py uses a connected components algorithm to identify and extract the bounding boxes of parking spots from the mask.

Spot Classification: The empty_or_not function classifies each detected spot using a pre-trained model. The model takes a cropped image of a parking spot, processes it, and predicts whether it is empty or occupied.

Real-Time Video Processing: The main.py script processes the video frame-by-frame, continuously updating the status of each parking spot and displaying the results.

