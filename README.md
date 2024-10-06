# Face Detection with OpenCV

This project demonstrates how to use the OpenCV library in Python to perform face detection. The program utilizes a pre-trained Haar Cascade classifier to detect faces in an image and draws rectangles around them. The processed image is then saved with the detected faces highlighted.

## Requirements

Before running the script, make sure you have the following installed:

- **Python 3.x**
- **OpenCV (cv2)**: You can install it via pip.
- **NumPy**: Required for numerical operations.

## Installation

You can install OpenCV and NumPy using the following commands:

```bash
pip install opencv-python numpy
```

## How It Works

1. **Load the Classifier**: A pre-trained Haar Cascade classifier (`haarcascade_frontalface_default.xml`) is used for detecting faces in the input image.
2. **Load the Input Image**: An image is read from the local system.
3. **Detect Faces**: The classifier detects faces and returns the coordinates of bounding boxes around them.
4. **Draw Rectangles**: Rectangles are drawn around each detected face.
5. **Save the Output**: The resulting image with highlighted faces is saved.

## How to Run

1. **Modify the Input Image Path**: Ensure the path to your image is correctly set in the script.
2. **Run the Script**: Execute the script in your Python environment.
3. **Check Output**: The processed image will be saved as `face_detected.png` in the working directory.

## Example Code

Here’s a snippet to illustrate the implementation:

```python
import cv2

# Load the Haar Cascade classifier
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')

# Load the input image
img = cv2.imread(r"path_to_your_image.jpg")

# Perform face detection
faces = face_cascade.detectMultiScale(img, 1.1, 4)

# Draw rectangles around the faces
for x, y, w, h in faces:
    cv2.rectangle(img, (x, y), (x + w, y + h), (255, 0, 0), 2)

# Save the result
cv2.imwrite("face_detected.png", img)
print("Photo successfully exported!")
```

## Troubleshooting

- **Face not detected**: Check the clarity and lighting of the image. Adjust the `scaleFactor` and `minNeighbors` in `detectMultiScale()` if needed.
  
- **No module named 'cv2'**: Ensure OpenCV is installed correctly.

## License

This project is open-source and available under the MIT License.
