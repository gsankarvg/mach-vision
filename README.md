# mach-vision

5) Resizing: The image is resized to half of its original size using cv2.resize(). You can change the scaling factor (0.5) to resize the image to a different size.
Scaling: The image is scaled by a factor of 1.5 along both dimensions using cv2.resize(). This increases the size of the image by 1.5 times.
Cropping: A region of interest (ROI) is selected from the image. This is done by specifying the starting x and y coordinates (crop_x, crop_y) and the width (crop_w) and height (crop_h) of the cropped region.
The region is then sliced from the image

6) To convert a grayscale image into a binary image without using built-in functions like cv2.threshold(), we need to manually threshold the pixel values. In a binary image, pixel values are either 0 (black) or 255 (white). Typically, a threshold value is chosen (e.g., 127), and any pixel value greater than or equal to this threshold is set to 255, and any pixel value less than the threshold is set to 0.

7) To find the complement of a grayscale image and a color image, we need to subtract the pixel values from their maximum possible values:
For grayscale images, the pixel values range from 0 to 255. The complement of a pixel value p can be calculated as 255 - p.
For color images (in BGR or RGB format), each channel (Blue, Green, Red) can be complemented independently. The complement for each channel is calculated as 255 - channel_value.

8) Manipulating color spaces such as RGB, HSV, and LAB allows us to perform operations on different aspects of the color information. Here's a brief overview of each color space:

RGB (Red, Green, Blue): The most common color space used in digital images, where colors are represented as combinations of red, green, and blue channels.
HSV (Hue, Saturation, Value): In this color space:
Hue represents the color type.
Saturation represents the intensity of the color.
Value represents the brightness.
LAB (Luminance, A, B): A color space that separates image luminance (lightness) from color information:
L represents lightness.
A represents the green to red component.
B represents the blue to yellow component.

9) In OpenCV, you can easily split and merge the color channels of an image using cv2.split() and cv2.merge() functions. These operations allow you to manipulate each channel independently, which is useful for tasks like color correction, enhancement, or filtering specific color channels.

Splitting the Channels:
The cv2.split() function splits the image into its individual color channels.
For example, an image in BGR format will be split into three channels: Blue, Green, and Red.
Merging the Channels:
The cv2.merge() function is used to merge the individual channels back into a single image.
The channels need to be in the correct order (e.g., for BGR, the channels should be [Blue, Green, Red]).

10) To view the individual channels with their respective colors (Red, Green, and Blue) instead of grayscale images, you can create a new image where only one of the channels is non-zero while the others are set to zero. This will allow you to visualize each channel in its own respective color.
Here's how to do it:
Steps:
Split the image into channels: Use cv2.split() to separate the Red, Green, and Blue channels.
Create images for each channel: Create new images where only one channel is non-zero, and the others are set to zero.
Display: Use matplotlib to show each channel with its respective color.