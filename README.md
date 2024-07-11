# Face Recognition Project

This project consists of a face recognition system using OpenCV, NumPy, and other libraries. The system is designed to recognize faces from a live video feed using a pre-trained model.

## Files

- `faces.py`
- `faces_train.py`
- `labels.pickle`
- `trainer.yml`

## Requirements

- Python 3.x
- OpenCV
- NumPy
- Pillow
- pickle

## Installation

1. Clone the repository or download the files.
2. Install the required libraries using pip:

    ```sh
    pip install numpy opencv-python Pillow
    ```

3. Place your training images in a folder named `images` in the same directory as the scripts. The folder structure should look like this:

    ```
    images/
    ├── person1/
    │   ├── image1.jpg
    │   └── image2.jpg
    ├── person2/
    │   ├── image1.jpg
    │   └── image2.jpg
    └── ...
    ```

## Usage

### Training the Model

1. Run the `faces_train.py` script to train the model and generate the `labels.pickle` and `trainer.yml` files:

    ```sh
    python faces_train.py
    ```

    The script will read the images from the `images` directory, detect faces, and train a model to recognize the faces. It will save the trained model and labels in `trainer.yml` and `labels.pickle` respectively.

### Running the Face Recognition

2. Run the `faces.py` script to start the face recognition system:

    ```sh
    python faces.py
    ```

    The script will open a video feed from the default camera, detect faces, and try to recognize them using the pre-trained model. When a face is recognized, it will display the name of the person on the video feed.

## Code Explanation

### faces_train.py

This script trains the face recognition model.

- It loads the face cascade classifier for face detection.
- It walks through the `images` directory to read all images.
- It converts the images to grayscale and resizes them.
- It detects faces in the images and adds them to the training set.
- It saves the trained model and labels using pickle.

### faces.py

This script runs the face recognition on a live video feed.

- It loads the face cascade classifier for face detection.
- It loads the pre-trained face recognizer model and the labels.
- It opens a video feed from the default camera.
- It detects faces in the video feed and tries to recognize them using the pre-trained model.
- When a face is recognized, it displays the name of the person on the video feed.
