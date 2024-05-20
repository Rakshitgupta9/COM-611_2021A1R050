## Ques: Implement the detection of Eye or face or Smile from the Image

# Face Detection using OpenCV

This is a simple Python script that demonstrates face detection using the OpenCV library. The script detects faces, eyes, and smiles in an image, and draws rectangles around them to highlight the detected regions.

## Prerequisites

- Python 3.x
- OpenCV library (cv2)
- Numpy library (numpy)

## Installation

Ensure that you have Python installed on your system. You can install the required libraries using pip:

```
pip install opencv-python
pip install numpy
```

## Usage

1. Clone the repository or download the script.
2. Place your image file (e.g., `download.jpg`) in the same directory as the script.
3. Run the script using Python:

```
python face_detection.py
```

The script will display the original image along with the detected faces, eyes, and smiles.

## Description

- The script first imports the necessary libraries: NumPy and OpenCV.
- It then loads the pre-trained Haar cascades for face, eye, and smile detection provided by OpenCV.
- Reads the image (`download.jpg`) using OpenCV's `imread` function and displays it.
- Converts the image to grayscale using OpenCV's `cvtColor` function and displays the grayscale image.
- Detects faces in the grayscale image using the `detectMultiScale` method of the `CascadeClassifier` object.
- For each detected face, it draws a rectangle around it on the original image and extracts the region of interest (ROI) from both the grayscale and color image.
- Within each face ROI, it detects eyes and smiles using similar methods and draws rectangles around them.
- Displays the final image with all the detected features.

## Credits

- This script is based on the OpenCV library and utilizes the pre-trained Haar cascades for face, eye, and smile detection.

