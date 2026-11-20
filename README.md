# Experiment 4: Image Transformations

### Aim :
To perform various image transformations such as translation, scaling, shearing, reflection, rotation, and cropping using Python and OpenCV.

### Developed By : ABISHEK S
### Register Number : 212224240003
### Requirements :
- Jupyter Notebook / Anaconda
- Matplotlib
- Input image: taj1.webp

### Procedure : 
1. Import the required libraries: OpenCV, NumPy, and Matplotlib.
2. Load and display the original image.
3. Perform translation to shift the image horizontally and vertically.
4. Apply scaling to resize the image.
5. Perform shearing to slant the image along the horizontal and vertical axes.
6. Apply reflection to flip the image.
7. Rotate the image by 45 degrees.
8. Crop a selected portion of the original image.
9. Display and observe the results of all transformations.

### Program : 

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### Step 1: Load the image :

```python
image = cv2.imread('pic.jpeg')  # Load the image from file

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct display
plt.title("Original Image")  
plt.axis('on') 
```

### Step 2: Image Translation

```python
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])  # Translation matrix: 
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))  # Display the translated image
plt.title("Translated Image")  
plt.axis('on')
```

### Step 3: Image Scaling :

```python
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
# resize: Resize the image by scaling factors fx, fy
# INTER_LINEAR: Uses bilinear interpolation for resizing

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))  # Display the scaled image
plt.title("Scaled Image")  # Set title
plt.axis('on')
```

### Step 4: Image Shearing :

```python
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))  # Display the sheared image
plt.title("Sheared Image")  # Set title
plt.axis('on')
```

### Step 5: Image Reflection :

```python
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))  # Display the reflected image
plt.title("Reflected Image")  # Set title
plt.axis('on')
```

### Step 6: Image Rotation :

```python
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45  # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)  # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height))  # Apply rotation

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))  # Display the rotated image
plt.title("Rotated Image")  # Set title
plt.axis('on')
```

### Step 7: Image Cropping :

```python
x, y, w, h = 200, 100, 100, 150  # Define the top-left corner (x, y) and the width (w) and height (h) of the crop
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
# The crop is performed by slicing the image array in the y and x directions

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))  # Display the cropped image
plt.title("Cropped Image")  # Set title
plt.axis('on')
```

### Output :

### Step 1: Load the image :

<img width="314" height="410" alt="download" src="https://github.com/user-attachments/assets/188bc65c-adca-4150-bba7-b184531e6582" />


### Step 2: Image Translation

<img width="314" height="410" alt="download" src="https://github.com/user-attachments/assets/433d19ff-1186-4111-8e07-9de712701678" />

### Step 3: Image Scaling :

<img width="516" height="290" alt="download" src="https://github.com/user-attachments/assets/738ced65-df78-43e5-a6e2-e6f0bba54b3d" />


### Step 4: Image Shearing :

<img width="314" height="410" alt="download" src="https://github.com/user-attachments/assets/226f8e60-b0c7-4a14-a8c6-2a3321779dc2" />

### Step 5: Image Reflection :

<img width="314" height="410" alt="download" src="https://github.com/user-attachments/assets/a4abfbca-ad8e-4cc5-b976-7ed1b5b6769d" />

### Step 6: Image Rotation :

<img width="314" height="410" alt="download" src="https://github.com/user-attachments/assets/7e8a317d-bda7-4d2b-9fb3-4d036d579773" />

### Step 7: Image Cropping :

<img width="512" height="410" alt="download" src="https://github.com/user-attachments/assets/7b75d869-0d4c-4a47-bc2e-ff55ae3a031b" />


### Result :
Thus , the Various image transformations, including translation, scaling, shearing, reflection, rotation, and cropping, were successfully performed using Python and OpenCV.
