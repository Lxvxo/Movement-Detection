# Optical Flow Detection using Horn-Schunck and Lucas-Kanade Methods

## Introduction
This project focuses on the implementation and analysis of two well-known methods for optical flow detection: the **Horn-Schunck method** and the **Lucas-Kanade method**. Optical flow refers to the pattern of apparent motion of objects, surfaces, and edges in a visual scene, caused by the relative motion between an observer and the scene. The goal of this project was to estimate pixel movement between successive images in a video sequence using these techniques.

For mathematical resolution, please refer to the CR.pdf file.

## Example 

![newplot](https://github.com/user-attachments/assets/654926ec-ad3d-412a-a355-e6aca01c280e)

## Methods

### 1. Horn-Schunck Method
The Horn-Schunck method is based on the minimization of a global energy function that includes both data fidelity and spatial coherence. The method calculates the optical flow by solving the following optimization problem:

- **Data Fidelity:** Ensures that the movement preserves pixel intensity.
- **Spatial Coherence:** Imposes smoothness on the flow field.

**Key Equation:**

\[ \text{Optical Flow Equation: } \nabla_x I \cdot u + \nabla_y I \cdot v + \nabla_t I = 0 \]

### 2. Lucas-Kanade Method
The Lucas-Kanade method, in contrast, assumes a constant motion model within a small neighborhood around each pixel. It uses a weighted least squares approach to solve the optical flow equations for each pixel neighborhood.

**Key Equation:**

\[ A \cdot \begin{bmatrix} u \\ v \end{bmatrix} = -b \]

Where \(A\) and \(b\) are matrices derived from image gradients within the neighborhood.

## Implementation

### 1. Horn-Schunck Implementation
- **Gradient Calculation:** Sobel filters were used to compute image gradients, given their precision over simple finite differences.
- **Parameter Tuning:** The influence of the parameter \( \lambda \) was studied, balancing between noise sensitivity and flow smoothness.

### 2. Lucas-Kanade Implementation
- **Neighborhood Considerations:** Various sizes of neighborhoods were tested to find an optimal balance between capturing local details and computational efficiency.
- **Weighting:** Both Gaussian and linear weighting schemes were applied to evaluate their impact on noise resistance and smooth motion estimation.

## Application to Image Sequences
The developed methods were applied to sequences of images, where the algorithms calculated the optical flow between consecutive frames, allowing for a robust estimation of motion across the sequence.

## Conclusion
While both methods provide effective solutions for optical flow detection, they are sensitive to noise and occlusions. The choice of method and parameters can significantly impact the accuracy of motion estimation, particularly in regions with little intensity variation.

## How to Run
To replicate the results:
1. Clone the repository.
2. Install the required dependencies.
3. Run the provided scripts with the test images.
