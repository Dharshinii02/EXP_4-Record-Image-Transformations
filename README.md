# EXP_4-Record-Image-Transformations
**Developed By:** Dharshini J

**Register Number:** 212224240036

**Title:** EXP_4 Record-Image Transformations

---

## Aim

To write a Python program using OpenCV to perform different image transformations such as translation, scaling, shearing, reflection, rotation, and cropping on an input image.

---

## Software Used

- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Jupyter Notebook
- Anaconda (optional)

---

## Algorithm

### Step 1: Import Required Libraries

Import OpenCV, NumPy, and Matplotlib libraries for image processing and visualization.

### Step 2: Load and Display the Original Image

1. Read the input image using `cv2.imread()`.
2. Convert the image from BGR to RGB color format.
3. Display the original image using Matplotlib.

### Step 3: Image Translation

1. Define the translation values `tx` and `ty`.
2. Create a translation matrix using `np.float32()`.
3. Apply translation using `cv2.warpAffine()`.
4. Display the translated image.

### Step 4: Image Scaling

1. Define the horizontal and vertical scaling factors.
2. Resize the image using `cv2.resize()`.
3. Use `cv2.INTER_LINEAR` interpolation.
4. Display the scaled image.

### Step 5: Image Shearing

1. Create a shearing matrix using `np.float32()`.
2. Apply the shearing transformation using `cv2.warpAffine()`.
3. Display the sheared image.

### Step 6: Image Reflection

1. Apply reflection using `cv2.flip()`.
2. Display the reflected image using Matplotlib.

### Step 7: Image Rotation

1. Get the height and width of the original image.
2. Define the rotation angle as 45 degrees.
3. Calculate the center of rotation.
4. Create a rotation matrix using `cv2.getRotationMatrix2D()`.
5. Apply rotation using `cv2.warpAffine()`.
6. Display the rotated image.

### Step 8: Image Cropping

1. Define the starting coordinates and cropping dimensions.
2. Crop the image using array slicing.
3. Display the cropped image using Matplotlib.

---

## Program



### 1. Import Required Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

### 2. Load and Display the Original Image

```python
image = cv2.imread('puppy.jpeg')

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```

### 3. Image Translation

```python
tx, ty = 350, 250

M_translation = np.float32([[1, 0, tx], [0, 1, ty]])

translated_image = cv2.warpAffine(
    image,
    M_translation,
    (image.shape[1] + tx, image.shape[0] + ty)
)

plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
```

### 4. Image Scaling

```python
fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image,
    None,
    fx=fx,
    fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))
plt.title("Scaled Image")
plt.axis('off')
```

### 5. Image Shearing

```python
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])

sheared_image = cv2.warpAffine(
    image,
    shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')
```

### 6. Image Reflection

```python
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')
```

### 7. Image Rotation

```python
(height, width) = image.shape[:2]

angle = 45

center = (width // 2, height // 2)

M_rotation = cv2.getRotationMatrix2D(center, angle, 1)

rotated_image = cv2.warpAffine(
    image,
    M_rotation,
    (width, height)
)

plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
```

### 8. Image Cropping

```python
x, y, w, h = 100, 100, 200, 150

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
```

---

## Output

The following outputs are obtained:

### i) Display the Original Image

<img width="235" height="410" alt="image" src="https://github.com/user-attachments/assets/d12e700a-d9ed-417c-9464-e53e53678d8b" />


### ii) Display the Translated Image

<img width="297" height="412" alt="image" src="https://github.com/user-attachments/assets/7b9ffe15-fded-406f-9f04-738bf4765cb5" />


### iii) Display the Scaled Image

<img width="550" height="406" alt="image" src="https://github.com/user-attachments/assets/f6357074-6e21-4211-85cb-d22db2ec3b48" />


### iv) Display the Sheared Image

<img width="253" height="410" alt="image" src="https://github.com/user-attachments/assets/fe350cde-11f0-4bc0-a4b8-8c64eb41939f" />


### v) Display the Reflected Image

<img width="252" height="407" alt="image" src="https://github.com/user-attachments/assets/3b568bfb-b619-4bd7-bf3d-0a20177b26e3" />


### vi) Display the Rotated Image

<img width="237" height="413" alt="image" src="https://github.com/user-attachments/assets/445ad4d4-e399-4c97-8b8c-b63f83d92696" />


### vii) Display the Cropped Image

<img width="527" height="402" alt="image" src="https://github.com/user-attachments/assets/62721d16-811c-43b4-86f5-5259487452ef" />


---

## Result

Thus, different image transformations such as translation, scaling, shearing, reflection, rotation, and cropping were successfully performed on the input image using Python and OpenCV.
