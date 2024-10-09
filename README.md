# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: Initialize Environment:

Import necessary libraries: cv2, numpy, and matplotlib.pyplot.
Load the Image:

Use cv2.imread() to read the image file (e.g., "HappyFish.jpg").
Convert the image from BGR to RGB format using cv2.cvtColor() for accurate color representation in Matplotlib.
Perform Transformations:

### Step2: Translation:

Retrieve the image dimensions (rows and columns).
Create a translation matrix M_translate to shift the image by a specified number of pixels (e.g., 50 pixels right and 100 pixels down).
Apply the translation using cv2.warpAffine().
### Step3: Scaling:

Use cv2.resize() to scale the image by specified factors (e.g., 1.5 times its original size in both dimensions).
### Step4: Shearing:

Define a shearing transformation matrix M_shear with specified shear factors.
Apply shearing using cv2.warpAffine().
### Step5: Reflection (Flipping):

Use cv2.flip() to create a horizontal reflection (flip along the y-axis) of the image.
### Step6: Rotation:

Calculate the rotation matrix using cv2.getRotationMatrix2D(), specifying the center of rotation, angle (e.g., 45 degrees), and scale (1).
Apply rotation using cv2.warpAffine().
### Step7: Display the Results:

Use Matplotlib to create subplots for the original and transformed images.
Set titles for each subplot and disable axes for better visual presentation.
Adjust layout for clear viewing and show the plots.
### Step8: Optional Cropping:

(If needed) Crop a specified region of the original image using array slicing.
## Program:
```python
Developed By: NARAMALA KUMARTEJA
Register Number: 212223230132
```
## i)Image Translation:

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)  
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```
## ii) Image Scaling:
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR)
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```

## iii)Image shearing
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```


## iv)Image Reflection
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
reflected_image = cv2.flip(image_rgb, 1)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```
## v)Image Rotation
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```

## vi)Image Cropping
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('HappyFish.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
cropped_image = image_rgb[50:300, 100:400]
plt.tight_layout()
plt.show()
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```

## Output:
### Original Image
![image](https://github.com/user-attachments/assets/03421840-40b7-4961-b93f-79b11670ce55)

### i)Image Translation
![image](https://github.com/user-attachments/assets/be316218-3840-4ec0-9990-d275b189952d)

### ii) Image Scaling
![image](https://github.com/user-attachments/assets/b0bba58d-2ee7-4113-8191-0a5906603fb5)

### iii)Image shearing
![image](https://github.com/user-attachments/assets/faed884d-3f41-4f8b-beb6-fad82d8be81d)

### iv)Image Reflection
![image](https://github.com/user-attachments/assets/2ae50244-9c87-4010-85d1-d1c66b870c7e)

### v)Image Rotation
![image](https://github.com/user-attachments/assets/e19178ee-73bd-4ace-b2f6-9d02050c4992)

### vi)Image Cropping
![image](https://github.com/user-attachments/assets/3604b240-8815-429e-b92f-215047a44de7)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
