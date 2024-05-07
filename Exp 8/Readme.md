## Ques: Implement the Image Processing basics: Converting Image to RGB to BGR and to Grayscale, create a White / Black Color Image, how to draw shapes on image
# Image Processing Basics with OpenCV

This directory contains Python code snippets for performing basic image processing tasks using the OpenCV library. The provided functions demonstrate converting images to grayscale, BGR, and RGB color spaces, creating white and black color images, and drawing shapes on images.

## Prerequisites

Make sure you have the following installed:

- Python (3.x recommended)
- OpenCV library (`cv2`)
- NumPy library (`numpy`)

You can install OpenCV and NumPy using pip:

```
pip install opencv-python numpy
```

## Functions

### 1. `convert_to_grayscale(image_path)`

This function loads an image from the specified `image_path`, converts it to grayscale, and displays both the original and grayscale images.

### 2. `convert_to_bgr(image_path, output_path)`

This function loads an image from the specified `image_path`, converts it to BGR color space, displays both the original and BGR images, and saves the BGR image to the specified `output_path`.

### 3. `convert_bgr_to_rgb(output_path)`

This function loads an image from the specified `output_path`, which is assumed to be in BGR color space, converts it to RGB color space, and displays both the original BGR and converted RGB images.

### 4. `create_white_image(width, height)`

This function creates a white color image with the specified `width` and `height` dimensions and displays it.

### 5. `create_black_image(width, height)`

This function creates a black color image with the specified `width` and `height` dimensions and displays it.

### 6. `draw_shapes_on_image(image_path)`

This function loads an image from the specified `image_path`, draws shapes (rectangle, circle, and line) on the image, and displays the image with the drawn shapes.

## Usage

1. Import the necessary functions from `image_processing_basics.py`.
2. Use the functions with appropriate arguments to perform desired image processing tasks.

Example usage:

```python
from image_processing_basics import *

# Path to the image
image_path = "download.jpeg"

# Convert image to grayscale
convert_to_grayscale(image_path)

# Convert image to BGR and save
output_path = "output.jpg"
convert_to_bgr(image_path, output_path)

# Convert BGR image to RGB
convert_bgr_to_rgb(output_path)

# Create white and black color images
width, height = 800, 600
create_white_image(width, height)
create_black_image(width, height)

# Draw shapes on an image
draw_shapes_on_image(image_path)
```

---
