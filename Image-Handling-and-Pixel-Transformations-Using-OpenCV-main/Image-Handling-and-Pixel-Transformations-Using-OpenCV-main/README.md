# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** VENKATA MOHAN N 
- **Register Number:** 212224230298

  ### Ex. No. 01

#### 1. Read the image ('Eagle_in_Flight.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('Eagle_in_Flight.jpg', cv2.IMREAD_COLOR)

```

#### 2. Print the image width, height & Channel.
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 3. Display the image using matplotlib imshow().
```python
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
<img width="633" height="529" alt="image" src="https://github.com/user-attachments/assets/8170a722-86dd-4890-bf72-b1aeceb64a88" />


#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg') 
```



#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
img_rgb.shape
```

#### 7. Crop the image to extract any specific (Eagle alone) object from the image.
```python
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg') 
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```
<img width="495" height="527" alt="image" src="https://github.com/user-attachments/assets/4304f7d5-c962-410b-8dcc-78d978f3649b" />


#### 8. Resize the image up by a factor of 2x.
```python
# Resize the image to half its size
resized_image = cv2.resize(image, (768 * 4, 600 * 4))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (double the size)")
plt.axis("off")
plt.show()
```
<img width="629" height="531" alt="image" src="https://github.com/user-attachments/assets/ef5bbac0-8f79-4e4b-930f-8fc7f34fb062" />

#### 9. Flip the cropped/resized image horizontally.
```python
# Load the image
image = cv2.imread('Eagle_in_Flight.jpg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()

# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```
<img width="641" height="556" alt="image" src="https://github.com/user-attachments/assets/f7c1ba88-c72d-45fb-b433-e1f632457b42" />
<img width="627" height="516" alt="image" src="https://github.com/user-attachments/assets/4940eee6-de05-447f-8da4-9abd211f9da4" />



#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
# Read the image using OpenCV
img = cv2.imread('Apollo-11-launch.jpg', cv2.IMREAD_COLOR)
```
<img width="673" height="393" alt="image" src="https://github.com/user-attachments/assets/bd524564-3382-43be-9b8b-26aedae88548" />


#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = 'Apollo 11 Saturn V Launch, July 16, 1969'
font_face = cv2.FONT_HERSHEY_PLAIN
# YOUR CODE HERE: use putText()


# Load the image
image = cv2.imread('Apollo-11-launch.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Add text to the image
text_img = cv2.putText(img_rgb, 'Apollo 11 Saturn V Launch, July 16, 1969', (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
```
<img width="688" height="436" alt="image" src="https://github.com/user-attachments/assets/c9fac4b7-da4d-46e5-b71a-1c81ff5bb251" />


#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
# rect_color = magenta
# YOUR CODE HERE
# Load the image
image = cv2.imread('Apollo-11-launch.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)

```

#### 13. Display the final annotated image.
```python
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```
<img width="677" height="427" alt="image" src="https://github.com/user-attachments/assets/eef8d840-fad3-44a1-809a-cae5f2634cad" />


#### 14. Read the image ('Boy.jpg').
```python
# Read the image using OpenCV
img = cv2.imread('boy.jpg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()
```
<img width="659" height="525" alt="image" src="https://github.com/user-attachments/assets/2ce9a928-20e0-4d03-914e-dd5d36db040b" />


#### 15. Adjust the brightness of the image.
```python
image = cv2.imread('boy.jpg')
bright = cv2.convertScaleAbs(image, alpha=1, beta=50)

# Convert BGR → RGB 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

```

#### 16. Create brighter and darker images.
```python
#img_brighter = cv2.add(img, matrix)
#img_darker = cv2.subtract(img, matrix)
# YOUR CODE HERE
bright_rgb = cv2.cvtColor(bright, cv2.COLOR_BGR2RGB)




dark = cv2.convertScaleAbs(image, alpha=1, beta=-50)

# Convert BGR → RGB
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
dark_rgb = cv2.cvtColor(dark, cv2.COLOR_BGR2RGB)




```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python

plt.imshow(img_rgb, cmap='viridis')
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()


plt.imshow(dark_rgb)
plt.title("Darker")
plt.axis('off')

plt.show()



plt.imshow(bright_rgb)
plt.title("Brightened")
plt.axis('off')
plt.show()
```
<img width="675" height="521" alt="image" src="https://github.com/user-attachments/assets/96d6c4c3-5470-4c44-a405-53aa6f4e4c01" />
<img width="668" height="544" alt="image" src="https://github.com/user-attachments/assets/2d63078a-1024-436e-8d98-aa483e2fa3b7" />
<img width="647" height="522" alt="image" src="https://github.com/user-attachments/assets/241378af-8a91-4d30-93f5-4934f7156a47" />



#### 18. Modify the image contrast.
```python
image = cv2.imread('boy.jpg')
high = cv2.convertScaleAbs(image, alpha=1.5, beta=0)
low = cv2.convertScaleAbs(image, alpha=0.5, beta=0)

# Convert BGR → RGB
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
high = cv2.cvtColor(high, cv2.COLOR_BGR2RGB)
low = cv2.cvtColor(low, cv2.COLOR_BGR2RGB)

```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```python

# Convert BGR → RGB
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
high = cv2.cvtColor(high, cv2.COLOR_BGR2RGB)
low = cv2.cvtColor(low, cv2.COLOR_BGR2RGB)


plt.imshow(image)
plt.title("Original")
plt.axis('off')
plt.show()

plt.imshow(low)
plt.title("Low Contrast")
plt.axis('off')
plt.show()

plt.imshow(high)
plt.title("High Contrast")
plt.axis('off')

plt.show()
```
<img width="666" height="527" alt="image" src="https://github.com/user-attachments/assets/4f24977f-206a-465a-a163-60cc63cbfa24" />
<img width="650" height="531" alt="image" src="https://github.com/user-attachments/assets/523216cb-18ad-413b-9975-6c97cb8708be" />
<img width="635" height="502" alt="image" src="https://github.com/user-attachments/assets/eb985136-39fa-4abe-9645-b35f05b71445" />


#### 20. Split the image (boy.jpg) into the B,G,R components & Display the channels.
```python
# Load the image
image = cv2.imread('boy.jpg') 
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)

# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)


# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)

```

#### 21. Merged the R, G, B , displays along with the original image
```python
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```
<img width="638" height="549" alt="image" src="https://github.com/user-attachments/assets/8fa9cd0a-a7b1-4c6c-9516-21765c53e678" />


#### 22. Split the image into the H, S, V components & Display the channels.
```python
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()

plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()


# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
```
<img width="651" height="524" alt="image" src="https://github.com/user-attachments/assets/480010a1-2f7e-457b-9408-be34bd6fb383" />
<img width="716" height="530" alt="image" src="https://github.com/user-attachments/assets/1f69ecaf-4fed-4b92-8442-92dd06c48028" />
<img width="650" height="548" alt="image" src="https://github.com/user-attachments/assets/94836082-48a0-4fb2-9b7d-d4aeacf1da93" />

#### 23. Merged the H, S, V, displays along with original image.
```python
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

<img width="636" height="541" alt="image" src="https://github.com/user-attachments/assets/1c94de00-82a5-4cc9-af19-0eb1d0099614" />


## Output:
- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

