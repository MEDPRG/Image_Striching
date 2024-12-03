
# Image Stitching with Python and OpenCV

This repository contains a Python script for performing image stitching using OpenCV. The script combines multiple overlapping images into a seamless panorama through feature detection, matching, homography estimation, and image warping.

## Features

- **Feature Detection and Matching**:
  - Supports multiple feature extraction methods: SIFT, SURF, ORB, and BRISK.
  - Matches keypoints using BFMatcher, with support for brute force and KNN matching.

- **Homography Estimation**:
  - Calculates the perspective transformation matrix using RANSAC and matched keypoints.

- **Image Warping and Blending**:
  - Aligns images based on the homography matrix and overlays them seamlessly.
  - Includes cropping logic to remove black regions in the stitched panorama.

- **Iterative Stitching**:
  - Handles multiple images by iteratively stitching them into a single panorama.

- **Visualization**:
  - Displays the final stitched image using Matplotlib.

## Requirements

To run the script, ensure you have the following dependencies installed:

- Python 3.x
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- ImageIO

Install the required packages using pip:

```bash
pip install opencv-python numpy matplotlib imageio
```

## Usage

1. **Prepare Your Images**:
   - Place your images in a directory. Ensure that adjacent images have significant overlapping regions for optimal stitching.

2. **Update the Script**:
   - Modify the `main` function in the script to include your image paths and specify an output directory:
     ```python
     initial_image_paths = [
         'path/to/image1.jpg',
         'path/to/image2.jpg',
         'path/to/image3.jpg',
     ]
     output_directory = 'path/to/output'
     ```

3. **Run the Script**:
   ```bash
   python image_stitching.py
   ```

4. **View Results**:
   - The final stitched image will be saved in the specified output directory and displayed at the end of the script.

## Input Data

The script works with a pair or a set of overlapping images. Ensure the images have significant overlapping regions and are in a supported format (e.g., JPEG or PNG).

## Output

The script generates a stitched panorama as the final output, with intermediate cropped results saved during the iterative stitching process. Cropped images and the final panorama are saved in the specified output directory.

## Example

Here’s an example of the stitching process:

1. **Input Images**:
   ![Input Images](examples/input_images.jpg)

2. **Stitched Panorama**:
   ![Stitched Panorama](examples/stitched_panorama.jpg)

## Contributing

Contributions, bug reports, and feature requests are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
