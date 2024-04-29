# EX:01 COLOR_CONVERSIONS_OF-IMAGE
# DATE:
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
```
Developed By:PAVANA.G
Register Number: 212222230105
```

### i) Read and display the image
```
    import cv2
    image=cv2.imread('pav.jpg',1)
    image=cv2.resize(image,(400,300))
    cv2.imshow('PAVANA',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
### OUTPUT:
![WhatsApp Image 2024-02-12 at 22 00 18_0c71ebcb](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/7e41ac64-d0ca-4b73-af3b-c85f93cd0d27)
### ii)Write the image
```
    import cv2
    image=cv2.imread('pav.jpg',0)
    cv2.imwrite('de.jpg',image)
```
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 01 30_84ae0991](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/c55f7b63-1ca9-4e3a-aaf7-9d42948060a2)

### iii)Shape of the Image
```
    import cv2
    image=cv2.imread('pav.jpg',1)
    print(image.shape)
```
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 02 38_d392c057](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/a6791890-3af1-464d-a4ff-84046cc79489)

### iv)Access rows and columns
```
    import random
    import cv2
    image=cv2.imread('pav.jpg',1)
    image=cv2.resize(image,(400,400))
    for i in range (150,200):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()
```
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 04 16_e592f5de](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/d62b731c-c285-4553-8cb0-3651c5dd5a8c)

### v)Cut and paste portion of image
```
   import cv2
   image=cv2.imread('pav.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 06 13_65327a6c](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/79963286-74ad-4598-aa2a-126bab13375a)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('pav.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

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
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 09 14_c3c4ac6c](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/13c621a0-c5f9-47a3-b783-ec9e5958f1f5)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('pav.jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 10 52_7d8720f6](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/5784db89-9e8c-408a-9356-b33da61f8ad2)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('pav.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 12 08_db74babe](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/aad7acc4-e99e-446b-8a6e-3242790836fe)

### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('blue.jpg',1)
img = cv2.resize(img,(300,200))

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
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 13 27_933bf407](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/bbaf5c0b-eeb2-4fee-8b3b-d6a76286371e)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("blue.jpg",1)
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
## OUTPUT:
![WhatsApp Image 2024-02-12 at 22 14 38_7edaef1e](https://github.com/gpavana/COLOR_CONVERSIONS_OF-IMAGE/assets/118787343/fd234845-44a6-48a6-bed4-d7f1eab1adde)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







