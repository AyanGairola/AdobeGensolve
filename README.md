# Project Overview: Shape Detection, Symmetry Analysis, and Curve Completion

This project is designed to process and analyze doodles or images containing various shapes. The primary goals of the project are to detect and classify regular geometric shapes, assess their symmetry, and perform image completion using beizer curves and second approach involves a Generative Adversarial Network (GAN). The project is divided into multiple approaches, each addressing different aspects of shape detection and analysis.

## Approach 1: Advanced Shape Detection and Symmetry Identification

This functionality is designed to process images and CSV files containing shape data, detect and classify various geometric shapes, and assess their symmetry. It can visualize the detected shapes and their symmetry lines, and calculate a symmetry score for each shape.

### 1. Shape Detection:

•The detect_shapes_second function is used to detect shapes in the input image. It first converts the image to grayscale, applies Gaussian blur, and then thresholds the image to create a binary version. Contours are detected from this binary image.

### 2. Shape Classification:

•The classify_shape_second function classifies each detected contour based on the number of vertices and other geometric properties into shapes such as triangles, squares, rectangles, pentagons, hexagons, hectagons, stars, circles, ellipses, or polygons.

### 3. Symmetry Analysis:

•Symmetry lines (both vertical and horizontal) are drawn through the center of the bounding box around each shape’s contour using the draw_symmetry_lines_second function.
•The symmetry score is calculated using the calculate_symmetry_score_second function by comparing the contours of the left and right halves and the top and bottom halves of the shape.

### 4. Visualization:

•The show_detected_shape_second function visualizes the detected shapes and their symmetry lines by drawing them on the image, and displays the image using Matplotlib.
•The detected shapes and their symmetry scores are printed for easy interpretation.

## Approach 2 - Using BEIZER CURVES for curve beautification and completion 

This project provides tools for reading shape data from CSV files, generating Bezier curves, evaluating their accuracy, detecting shapes from images, and visualizing results.

### Data Handling and plotting Polylines and Bezier Curves
The read_csv function loads contour data from a CSV file, while plot_polylines visualizes these contours as polylines. To generate smooth curves, generate_bezier_curve creates a Bezier curve from given points, which can be visualized with plot_bezier_curves.

###  Shape Classification and Fitting
Shape detection is handled by classify_shape_second, which categorizes contours, and fit_line, which fits a line to a set of points. The draw_shape and draw_fitted_line functions are used to render detected shapes or fitted lines onto images.

### Accuracy Evaluation and Curvature Calculation
For evaluating how well a Bezier curve matches original points, evaluate_accuracy calculates the mean squared error and maximum deviation, while calculate_curvature measures the curvature along the Bezier curve.

### Shape Detection from Images
Shape detection from images is managed by getShapeName to determine the shape based on vertices, and plot_polylines to visualize detected shapes and contours.

### completition of curves

The code processes an image by detecting contours, generating smooth Bezier curves for each contour, saving these curves to a CSV file, and then visualizing the completed curves on the original image.

## Image Completion using a GAN(Approach 2 of Handling Incomplete curves)
This project implements a Generative Adversarial Network (GAN) for image completion tasks. The GAN consists of a U-Net-based generator and a PatchGAN-based discriminator, trained to fill in missing parts of images.

### 1. Data Preprocessing

The dataset is loaded from .npy files and resized to (256, 256). The images are then normalized to the range [-1, 1] to stabilize the training process, and the data is reshaped to have a single channel (grayscale).

### 2. Generator Model (build_generator)

The generator model is based on a U-Net architecture, which includes downsampling and upsampling layers. The downsampling layers capture context by reducing the image size while increasing the number of filters. The upsampling layers recover the spatial resolution while merging skip connections from the downsampling path to retain details.

### 3. Discriminator Model (build_discriminator)

The discriminator uses a PatchGAN architecture to evaluate the quality of the generated images by comparing them against the real images. It concatenates the input and target images and applies a series of convolutional layers to determine whether the images are real or generated.

### 4. Loss Functions and Optimizers

The generator_loss function calculates the total loss for the generator, combining the GAN loss (binary cross-entropy) and the L1 loss, which encourages the generator to produce images similar to the target. The discriminator_loss function computes the loss for the discriminator, penalizing incorrect classifications of real and generated images. Both models are optimized using the Adam optimizer.


# Overall Goal

The overall goal of the project is to develop a robust system that can detect and classify geometric shapes in doodles or images, assess their symmetry, and complete missing parts of shapes using deep learning and mathematical techniques. The project combines traditional image processing techniques with modern deep learning models and and mathematical techniques to achieve accurate and reliable results, making it useful for various applications in computer vision, art analysis, and more.

# Required Libraries

•	OpenCV (cv2)
•	NumPy (np)
•	Pandas (pd)
•	Matplotlib (matplotlib.pyplot)
•	Pandas (pd)
•	TensorFlow (tf)
•	SciPy (scipy)
•	scikit-learn (sklearn)
