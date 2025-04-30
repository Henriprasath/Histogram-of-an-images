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
# Developed By: HENRIPRASATH S 
# Register Number: 212223230077
```

```
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()

plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()

img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```
## Output:
### Input Grayscale Image and Color Image

![Screenshot 2025-04-30 203421](https://github.com/user-attachments/assets/fea11ee2-90c4-4468-b3fe-679fd68c7b25)


![Screenshot 2025-04-30 193634](https://github.com/user-attachments/assets/0045e5ce-a273-4aff-96db-8a95eebfed55)


### Histogram of Grayscale Image and any channel of Color Image

![Screenshot 2025-04-30 193704](https://github.com/user-attachments/assets/95d30b09-c139-415b-9d01-9f3380baf6e9)

![Screenshot 2025-04-30 193718](https://github.com/user-attachments/assets/257b8932-56eb-40bd-8ee5-91043298111e)


### Histogram Equalization of Grayscale Image

![Screenshot 2025-04-30 193752](https://github.com/user-attachments/assets/f4fff500-b66a-4632-89df-8adc7880c0dd)



## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
