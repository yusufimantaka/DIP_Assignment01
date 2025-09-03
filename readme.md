# This repository is for the DIP Assignment regarding Upsampling and Downsampling

## Generate Image
Firstly, I made code to generate a random 10x10 Black and White image that will be used to experiment on sampling methods

## Downsampling Results
I experimented using three (3) different downsampling methods, and all varied.

1. Downsampling with Average Pooling
This method, also known as average pooling, reduces the image size by calculating the average value of a group of pixels and assigning that average to a single pixel in the new, smaller image. * Analysis: The "Downsample Avg" image appears the smoothest and most blurred. This is because the averaging process blends the original black (0) and white (255) pixels, resulting in new gray values. This method is effective at reducing noise and creating a general representation of the original image but loses sharp detail.

2. Downsampling with Max Pooling
Also known as max pooling, this method works by taking the maximum value from a group of pixels and using that as the new pixel's value. * Analysis: The "Downsample Max" image retains the brightest features of the original image. In this black and white context, it preserves the white pixels (value 255) and their overall shape. The result is a high-contrast image that highlights the most dominant features, which is often useful for feature detection in computer vision tasks.

3. Downsampling with Median Pooling
This method, known as median pooling, reduces the image size by taking the median value from a group of pixels. The median is the middle value in a sorted list of the pixels in the group.

Analysis: The "Downsample Median" image is a good compromise between the other two. It preserves the edges and detail better than the average method because it is less sensitive to extreme values (noise) than the max method. The resulting image looks cleaner and less blurry than the average-pooled one while still providing a good summary of the original.

## Upsampling Results
I experimented using three (3) different upsampling methods, and all varied.

1. Nearest-Neighbor
The Nearest-Neighbor image is a scaled-up version of the original. This method simply copies the nearest pixel's value to the new pixels.

Analysis: This method is the fastest but produces the lowest quality result. It creates a blocky and jagged appearance because it doesn't smooth the transitions between pixels. The edges remain sharp and pixelated, effectively just enlarging the original pixels without any blending.

2. Bilinear
The Bilinear image is a much smoother result compared to nearest-neighbor. This method calculates a new pixel's value based on a weighted average of the four closest pixels from the original image.

Analysis: This method is a great improvement. It effectively blurs and smoothes the transitions, which removes the harsh, blocky edges seen in the nearest-neighbor image. The downside is that this smoothing can cause a slight loss of sharpness, making the image appear a bit soft or fuzzy.

3. Bicubic
The Bicubic image is the highest quality result of the three. It's more complex than bilinear, using a weighted average of a 4x4 grid (16 pixels) to determine the value of each new pixel.

Analysis: This method is the slowest but produces the best visual quality. It does an excellent job of smoothing the edges without introducing as much blur as bilinear. The result is a sharp, clear image with very smooth transitions. The added complexity of considering more pixels allows it to create a much more accurate and natural-looking interpolation, which is why it's a popular choice for high-quality upsampling.
