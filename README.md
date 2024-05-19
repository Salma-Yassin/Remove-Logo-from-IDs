# Remove Logo from IDs

### Project Description
This project aims to remove the logo of "جمهورية مصر العربية" from images of Egyptian national IDs and replace it with the background color, ensuring a seamless and homogenous replacement. The solution uses image processing techniques to achieve this task.

![image](https://github.com/Salma-Yassin/Remove-Logo-from-IDs/assets/109458906/9d4ad2d0-aa64-433f-9360-b435700b3324)


### Solution Steps:

- Detects keypoints and computes descriptors using the Scale-Invariant Feature Transform (SIFT) algorithm on the given image.
- Matches descriptors from a logo image and a scene image using the FLANN-based matcher.
- Applies the ratio test to filter good matches from the list of matches.
- Finds the homography matrix using the good matches between the keypoints of the logo and scene images.

The main function `remove_logo()` loads the input image and the logo image specified by the provided paths. It then converts the input image to grayscale and detects keypoints and computes descriptors using (SIFT) algorithm for both the logo and scene images. The descriptors are then matched, and a ratio test is applied to filter good matches. If a sufficient number of good matches are found, a homography matrix is calculated. With the homography matrix, the logo's position in the scene image is determined, and a mask is created to isolate the logo region. The logo region is inpainted and blurred to remove itfrom the scene image. Finally, the modified scene image is saved to the specified output path.

Steps involved in SIFT algorithm :

- Scale-space detection: Generate a series of images with progressively reduced resolution and different levels of Gaussian blur, Compute the Difference of Gaussians (DoG) for adjacent blurred images and Identify local extrema in the DoG images.
- Keypoint Localization: Accurately locating the feature keypoints.
- Orientation Assignment: Assigning orientation to keypoints.
- Keypoint descriptor: Describing the keypoints as a high dimensional vector.
- Keypoint Matching


### Usage 
`remove_logo(input_image_path, output_image_path, logo_image_path='Logo_2.PNG')`

### Results
- We can use `remove_logo()` to remove the logo as seen:
  
<img src="https://github.com/Salma-Yassin/Remove-Logo-from-IDs/assets/109458906/eb3932c5-37ce-4cb0-bbdb-b5b6552a8ec9" width="400" style="margin-right: 100;">

<img src="https://github.com/Salma-Yassin/Remove-Logo-from-IDs/assets/109458906/790b9565-35b0-4778-bfc9-80ebe0cc6057" width="400">



