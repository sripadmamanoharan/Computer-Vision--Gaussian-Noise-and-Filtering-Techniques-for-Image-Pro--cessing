# Computer-Vision--Gaussian-Noise-and-Filtering-Techniques-for-Image-Processing

The effectiveness of filtering techniques in reducing noise from the image lena.png. The steps involved are:
– Add Gaussian noise to the image using a normal distribution N(0.1,0.1).
– Apply Gaussian smoothing and evaluate whether it improves the noisy image.
– Apply Median filtering to the noisy image and observe the changes.
– Modify the noise by setting it to 1 where r > 0.2, and to 0 otherwise, then reapply Gaussian smoothing and median filtering.
– Compare the results of both filtering techniques for different types of noise.
Analysis
Adding Gaussian Noise
Gaussian noise with a mean of 0.1 and variance of 0.1 is added to each pixel in the image. The noise is sampled from a normal distribution N (0.1, 0.1), meaning random values are added to each pixel, simulating real-world image degradation.
Gaussian Smoothing
After adding noise, Gaussian smoothing is applied with an appropriate kernel size and standard deviation. The purpose of smoothing is to reduce noise by averaging pixel values, thus softening sharp edges introduced by the noise.
Median Filtering
A median filter is also applied to the noisy image. This technique replaces each pixel value with the median of its neighboring pixels within a defined window, which helps preserve edges while reducing noise. Median filtering is particularly effective for images with sharp transitions or ”salt- and-pepper” noise.
Noise Thresholding
A modified noise model is created where noise values are set to 1 where they exceed 0.2 and to 0 otherwise. This transforms the noise into a binary pattern. Both Gaussian smoothing and median filtering are applied to this modified noise, and the results are analyzed.
Results and Observations Original Noise N(0.1,0.1)
After introducing Gaussian noise to the image, significant degradation occurs, particularly in areas with fine details. Noise is visible across the entire image.
Gaussian Smoothing
Gaussian smoothing effectively reduces the noise, but it also blurs the image. Fine details are lost, resulting in a softer overall appearance. While this method is useful for reducing continuous noise, it can also diminish sharp edges.
6
Median Filtering
Median filtering successfully reduces noise while preserving sharp edges better than Gaussian smoothing. It performs particularly well in regions with fine textures or sharp transitions. However, it can sometimes struggle to handle highly complex textures as effectively as Gaussian smoothing.
Thresholded Noise
After thresholding the noise to binary values (1 for noise r > 0.2, and 0 otherwise), the noisy image shows pronounced artifacts in areas where the noise is set to 1.
Gaussian Smoothing
While Gaussian smoothing reduces the binary noise, it significantly blurs the image, causing a noticeable loss of detail. This method struggles to retain sharp features in the presence of binary noise.
Median Filtering
Median filtering performs well in removing binary noise, effectively reducing the artifacts without losing as much detail. It preserves most of the edges and structural details of the image better than Gaussian smoothing.
Comparison and Conclusion Gaussian Smoothing
This technique works well for reducing continuous Gaussian noise, balancing noise reduction and image detail. However, it tends to blur the image, especially in regions with fine textures or sharp transitions.
Median Filtering
Median filtering is more effective when the noise is localized, such as with salt-and-pepper or binary noise. It preserves edges and sharpness much better than Gaussian smoothing. However, it can be computationally more expensive and may not be as effective in handling continuous noise patterns.
Failure Cases Over-Smoothing
Gaussian smoothing tends to overly blur the image when applied to high levels of noise, leading to a significant loss of detail, particularly in areas with edges and textures.
Median Filter Limitations
While median filtering is excellent for localized noise, it may not perform as well on highly textured or complex regions of the image. Additionally, with larger kernel sizes, the computational cost of median filtering increases.
