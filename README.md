# Image_Processing_Assignment
This repository contains my image processing assignment including source code, input images and annotated output images. 
# problem Description 
In quality control applications, detecting defective products on a production line is a critical task. This project develops an automated image processing solution to detect whether biscuits are broken or intact using only classical image processing techniques — no Machine Learning or Deep Learning methods are used.
The program:
•	Detects each individual biscuit in an image
•	Classifies each biscuit as Intact or Broken
•	Annotates the output image with bounding boxes and labels
# Tools and Libraries used
Tool / Library	Purpose
Python 3.x	Programming language
OpenCV (cv2)	Core image processing operations
NumPy	Numerical operations and array handling
Matplotlib	Result visualization and plotting

requirements.txt:
opencv-python
numpy
matplotlib

# Image Processing Methods Used
1.	Grayscale Conversion — Convert the input BGR image to grayscale for simpler processing
2.	Gaussian Blur — Reduce noise before thresholding
3.	Thresholding (Otsu's method) — Separate biscuits from the white A4 background
4.	Morphological Operations — Erosion and dilation to clean up the binary mask and fill gaps
5.	Contour Detection — cv2.findContours() to locate individual biscuit regions
6.	Shape Analysis — Analyze contour properties (area, perimeter, circularity, convexity defects) to determine if a biscuit is broken or intact
7.	Annotation — Draw bounding boxes and classification labels on the output image
Broken vs. Intact Decision Logic
•	Intact biscuit: High solidity (area / convex hull area ≥ threshold), smooth contour, regular shape
•	Broken biscuit: Low solidity, irregular edges, significant convexity defects or fragmented contour
# Instructions to run the code
Prerequisites
•	Python 3.7 or higher installed
•	Clone this repository
Install Dependencies
pip install -r requirements.txt
Run on a Single Image
python src/biscuit_detection.py --image dataset/circular/circular_01.jpg
Run on All Images in a Folder
python src/biscuit_detection.py --folder dataset/circular/

# Output
Annotated images will be saved to the output/ directory. Each detected biscuit will be marked with:
•	A green bounding box for Intact Biscuit
•	A red bounding box for Broken Biscuit
•	A text label indicating the classification result
# Example Output Images
Circular

Rectangular

