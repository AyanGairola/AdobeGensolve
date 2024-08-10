# Project Overview: Shape Detection, Symmetry Analysis, and Curve Completion

This project is designed to process and analyze doodles or images containing various shapes. The primary goals of the project are to detect and classify regular geometric shapes, assess their symmetry, and perform image completion using a Generative Adversarial Network (GAN). The project is divided into two approaches, each addressing different aspects of shape detection and analysis.

## Approach 1: Advanced Shape Detection and Symmetry Identification

This approach builds on the shape detection and classification process by introducing a more sophisticated method for detecting regular shapes and analyzing their symmetry.

### 1.	Advanced Shape Detection:
•	Shapes are detected by converting the image to grayscale, applying Gaussian blur, and thresholding the image to create a binary version. Contours are then detected in the binary image.
•	The detected contours are classified based on the number of vertices into shapes such as triangles, squares, rectangles, pentagons, hexagons, heptagons, stars, circles, ellipses, or polygons.
	
 ### 2.	Symmetry Analysis:
•	Symmetry is analyzed by drawing symmetry lines (vertical and horizontal) through the center of the bounding box around the contour of each shape.
•	A symmetry score is calculated by comparing the contours of the left and right halves and the top and bottom halves of the shape, with a higher score indicating greater symmetry.
	
 ### 3.	Visualization and Integration:
•	The detected shapes and their symmetry are visualized by drawing contours and symmetry lines on the image. The results are displayed using Matplotlib for easy interpretation.

## Approach 2: Identifying Regular Shapes in Doodles and Curve Completion

This approach focuses on detecting and classifying shapes within doodles or images, analyzing their regularity, and completing missing parts of shapes using a GAN.

### 1.	Shape Detection and Classification:
•	The process begins by detecting contours in the image using OpenCV, which helps identify the edges of shapes.
•	The contours are then classified into various geometric shapes like triangles, squares, rectangles, polygons, or circles based on the number of sides and other geometric properties.
•	The regularity of these shapes is checked against predefined criteria to determine if they are regular geometric shapes (e.g., squares, circles).
	
 ### 2.	Symmetry Detection:
•	The symmetry of detected shapes is analyzed by comparing the left and right halves of the shape as well as the top and bottom halves. This is done by mirroring one side and calculating the difference between the mirrored and original sides.
•	Shapes are classified as symmetric or asymmetric based on a calculated symmetry score.
	
 ### 3.	Curve Completion with GAN:
•	A GAN is used to complete missing parts of shapes in images. The GAN is trained using a U-Net-based generator and a PatchGAN discriminator to predict and fill in the incomplete regions of an image.
•	The model is trained with synthetically generated datasets, resized, normalized, and converted to grayscale.
•	After training, the GAN can be used to predict and complete shapes, and the results are saved as polylines in a CSV file for further analysis.


# Overall Goal

The overall goal of the project is to develop a robust system that can detect and classify geometric shapes in doodles or images, assess their symmetry, and complete missing parts of shapes using deep learning techniques. The project combines traditional image processing techniques with modern deep learning models to achieve accurate and reliable results, making it useful for various applications in computer vision, art analysis, and more.

# Required Libraries

•	OpenCV (cv2)
•	NumPy (np)
•	Pandas (pd)
•	Matplotlib (matplotlib.pyplot)
•	Pandas (pd)
•	TensorFlow (tf)
•	SciPy (scipy)
•	scikit-learn (sklearn)
