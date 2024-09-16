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
### Developed By: Gokkul M
### Register Number: 212223240039
```python
import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread(r"C:\Users\admin\Downloads\gray--gray.jpg", cv2.IMREAD_GRAYSCALE)  
color_image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg") 
cv2.imshow("Gray Image",gray_image)
cv2.imshow("Color Image",color_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
```python
import cv2
import matplotlib.pyplot as plt

gray_image = cv2.imread(r"C:\Users\admin\Downloads\gray--gray.jpg", cv2.IMREAD_GRAYSCALE)  
color_image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg") 

gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
color_hist = cv2.calcHist([color_image], [0], None, [256], [0, 256])

plt.figure(figsize=(12, 6))

plt.subplot(1, 2, 1)
plt.title("Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(gray_hist, color='black')

plt.subplot(1, 2, 2)
plt.title("Color Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
plt.plot(color_hist, color='blue')

plt.tight_layout()
plt.show()

```
```python
import cv2
import matplotlib.pyplot as plt
gray_image = cv2.imread(r"C:\Users\admin\Downloads\gray--gray.jpg", cv2.IMREAD_GRAYSCALE)
color_image = cv2.imread(r"C:\Users\admin\Downloads\gray .jpg")
resized_gray_image = cv2.resize(gray_image, (500, 400))
equalized_image = cv2.equalizeHist(gray_image)
cv2.imshow("Original Grayscale Image", gray_image)
cv2.waitKey(0)

cv2.imshow("Resized Grayscale Image", resized_gray_image)
cv2.waitKey(0)
cv2.imshow("Equalized Grayscale Image", equalized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()

plt.figure()

plt.subplot(1, 2, 1)
plt.title("Original Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
plt.plot(gray_hist)

plt.subplot(1, 2, 2)
plt.title("Equalized Grayscale Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")
equalized_hist = cv2.calcHist([equalized_image], [0], None, [256], [0, 256])
plt.plot(equalized_hist)

plt.tight_layout()
plt.show()

```
## Output:
### Input Grayscale Image and Color Image
![image](https://github.com/user-attachments/assets/3dba6b5a-d3e7-46f7-b74b-ac5be7ef27f3)

![image](https://github.com/user-attachments/assets/5c37933d-e76c-4d00-9c6a-ce4c28561c6d)

### Histogram of Grayscale Image and any channel of Color Image
![image](https://github.com/user-attachments/assets/2345dbe7-d188-4e87-9c2d-f17e15aea59d)

![image](https://github.com/user-attachments/assets/43f1e2a2-73f5-4c6d-9c4b-33105bd4921d)

### Histogram Equalization of Grayscale Image.
![image](https://github.com/user-attachments/assets/c7f51b47-27de-467d-acea-0ad8ab913915)

![image](https://github.com/user-attachments/assets/a249d21b-e58f-443f-918b-a21dcf4fa226)

![image](https://github.com/user-attachments/assets/1cc079b9-e4de-4c0f-969a-72d102390a86)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
