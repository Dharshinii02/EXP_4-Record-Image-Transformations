# Exp-4- Record-Image Transformations

## Experiment Details

### Developed By: Dharshini J

### Register Number: 212224240036

## Aim

To perform various image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping using OpenCV and Python.

## Software Required

- Anaconda
- Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

**Step 1:** Import the necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

**Step 2:** Read the input image using the `cv2.imread()` function and store it in a variable.

**Step 3:** Apply different image transformations using the following methods:

1. **Translation:** Moves the image along the X-axis or Y-axis using a translation matrix.
2. **Scaling:** Resizes the image using scaling factors.
3. **Shearing:** Distorts the image along one or both axes using a shear matrix.
4. **Reflection:** Flips the image horizontally or vertically using `cv2.flip()`.
5. **Rotation:** Rotates the image by a specified angle using `cv2.getRotationMatrix2D()`.
6. **Cropping:** Extracts a specific portion of the image using array slicing.

**Step 4:** Display the original and transformed images using Matplotlib.

**Step 5:** Convert the BGR image into RGB format using `cv2.cvtColor()` to display the correct colors.

## Program

### Developed By: Dharshini J

### Register Number: 212224240036

### i) Original Image

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread("dhar.jpeg")

# Display the original image
plt.imshow(image[:, :, ::-1])
plt.title("Original Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="370" height="502" alt="Screenshot 2026-11-14 212546" src="https://github.com/user-attachments/assets/51558434-b28f-44fa-9a7f-8f6eb390b24e" />


### ii) Image Translation

```python
tx, ty = 100, 200

M_translation = np.float32([
    [1, 0, tx],
    [0, 1, ty]
])

translated_image = cv2.warpAffine(
    image, M_translation, (673, 419)
)

plt.imshow(translated_image[:, :, ::-1])
plt.title("Translated Image")
plt.axis("on")
plt.show()
```

**Output:**

<img width="372" height="506" alt="Screenshot 2026-11-14 212551" src="https://github.com/user-attachments/assets/6c25c1f7-788b-41b7-bee2-9f27ee8e91b4" />


### iii) Image Scaling

```python
fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image, None, fx=fx, fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(cv2.cvtColor(
    scaled_image, cv2.COLOR_BGR2RGB
))

plt.title("Scaled Image")
plt.axis("off")
plt.show()
```

**Output:**


<img width="656" height="382" alt="Screenshot 2026-11-14 212556" src="https://github.com/user-attachments/assets/69572436-8ebf-4a43-ab6a-8dc80ab377c2" />


### iv) Image Shearing

```python
shear_matrix = np.float32([
    [1, 0.5, 0],
    [0.5, 1, 0]
])

sheared_image = cv2.warpAffine(
    image, shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(cv2.cvtColor(
    sheared_image, cv2.COLOR_BGR2RGB
))

plt.title("Sheared Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="367" height="515" alt="Screenshot 2026-11-14 212604" src="https://github.com/user-attachments/assets/64b3c0f6-747c-43c0-9548-772af2408ea2" />



### v) Image Reflection

```python
reflected_image = cv2.flip(image, 2)

plt.imshow(cv2.cvtColor(
    reflected_image, cv2.COLOR_BGR2RGB
))

plt.title("Reflected Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="370" height="515" alt="Screenshot 2026-11-14 212612" src="https://github.com/user-attachments/assets/c7090807-2c20-4ad6-8c26-a3cbea6f4ee9" />


### vi) Image Rotation

```python
(height, width) = image.shape[:2]

angle = 45
center = (width // 2, height // 2)

M_rotation = cv2.getRotationMatrix2D(
    center, angle, 1
)

rotated_image = cv2.warpAffine(
    image, M_rotation, (width, height)
)

plt.imshow(cv2.cvtColor(
    rotated_image, cv2.COLOR_BGR2RGB
))

plt.title("Rotated Image")
plt.axis("off")
plt.show()
```

**Output:**

<img width="360" height="506" alt="Screenshot 2026-11-14 212617" src="https://github.com/user-attachments/assets/da71b6f0-e406-42a9-8d2e-999640ffdcf0" />


### vii) Image Cropping

```python
x, y, w, h = 100, 100, 200, 150

cropped_image = image[y:y+h, x:x+w]

plt.imshow(cv2.cvtColor(
    cropped_image, cv2.COLOR_BGR2RGB
))

plt.title("Cropped Image")
plt.axis("off")
plt.show()
```

**Output:**


<img width="645" height="522" alt="Screenshot 2026-11-14 212622" src="https://github.com/user-attachments/assets/048c593b-8389-407e-b781-aa65c04269bd" />


## Result

Thus, the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation, and Cropping were successfully performed using OpenCV and Python programming.a
