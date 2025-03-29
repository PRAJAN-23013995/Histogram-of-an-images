# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: PRAJAN P
# Register Number: 212223240121

import cv2
import numpy as np
from matplotlib import pyplot as plt

gray_image = cv2.imread('bnw.jpg', cv2.IMREAD_GRAYSCALE)

plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')

print("Name : PRAJAN P \n Register Number : 212223240121")

plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()

equalized_gray_image = cv2.equalizeHist(gray_image)

plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)

plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')

import cv2
import numpy as np
import matplotlib.pyplot as plt

color_image = cv2.imread('color.jpg')

plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')

hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])

print("Name : PRAJAN P \n Register Number : 212223240121")


plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()

blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])

equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])

plt.title("Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')







```
## Output:
### Input Grayscale Image and Color Image
![Screenshot 2025-03-29 141956](https://github.com/user-attachments/assets/1fdc608e-736f-4a2f-aea3-cfd9922bb389)

![Screenshot 2025-03-29 142119](https://github.com/user-attachments/assets/c153579e-3a62-4807-b0b8-4ec5c4c507d5)


### Histogram of Grayscale Image and any channel of Color Image
![Screenshot 2025-03-29 142039](https://github.com/user-attachments/assets/c54469b5-5db9-4eb3-a9ad-b2f8cb5f7a38)

![Screenshot 2025-03-29 142134](https://github.com/user-attachments/assets/7cac386a-235b-4843-a81f-c3a25440d93e)


### Histogram Equalization of Grayscale Image.
![Screenshot 2025-03-29 142107](https://github.com/user-attachments/assets/33579175-de75-41c6-be2b-6b7f7e984c8d)



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
