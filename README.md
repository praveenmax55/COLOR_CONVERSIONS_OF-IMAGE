# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

##### Program:
### Developed By: Praveen D
### Register Number: 212222240076



### i) Read and display the image
```python
import cv2
import numpy as np
img=cv2.imread("eiffeltower.jpg")
cv2.imshow("window",img)
cv2.waitKey(0)
```
## Output:
<img src="https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/cdbedec7-0bf0-43ec-ab24-1c1df79364c8" alt="Your Image" width="300">
<br>
<br>

### ii)Write the image
```python
import cv2
img=cv2.imread('eiffeltower.jpg')
cv2.imwrite('paris.jpg',img)
```
## Output:
<img src="https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/0970cedd-a87d-4ffd-9394-e24505e80c97" alt="Your Image" width="300">
<br>
<br>

### iii)Shape of the Image
```python
import cv2
img=cv2.imread('eiffeltower.jpg')
print(img.shape)
```
## Output:
<img src="https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/8ea04688-1d35-42fb-ac13-0c80bda096f5" alt="Your Image" width="300">
<br>
<br>

### iv)Access rows and columns
```python
import cv2
import random
img=cv2.imread('eiffeltower.jpg')
for i in range(150,200):
    for j in range(img.shape[1]):
        img[i][j]=[random.randint(0,255),
                  random.randint(0,255),
                  random.randint(0,255)]
cv2.imshow('img',img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
<img src="https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/e037827b-db28-4172-a1dc-8547bbc98ab1" alt="Your Image" width="300">
<br>
<br>

### v)Cut and paste portion of image
```python
import cv2
img=cv2.imread('eiffeltower.jpg')
tag=img[150:200,110:160]
img[110:160,150:200]=tag
cv2.imshow('paris1',img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
<img src="https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/7211e05d-45d4-40ad-9296-d52807615cbf" alt="Your Image" width="300">
<br>
<br>

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('eiffeltower.jpg',1)
cv2.imshow('Paris2',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![InShot_20240215_214806058](https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/400d0860-1621-4a44-9bff-1eea6bfe2366)
<br>
<br>

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('eiffeltower.jpg')

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![InShot_20240215_215102457](https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/d034636a-f8e1-405c-b2e5-d83c61f766d8)

<br>
<br>

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('eiffeltower.jpg')
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![InShot_20240215_215452201](https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/b7fa5490-b041-4e40-9bac-123c12c7953d)
<br>
<br>

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('eiffeltower.jpg')

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![InShot_20240215_215933473](https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/8ae16d3f-8aaa-481e-8694-9441b343d9e9)
<br>
<br>

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("eiffeltower.jpg")
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## Output:
![InShot_20240215_220206626](https://github.com/Adhithyaram29D/COLOR_CONVERSIONS_OF-IMAGE/assets/119393540/8d19c1eb-7d8e-4380-8263-a3d2eec09b5e)
<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.




