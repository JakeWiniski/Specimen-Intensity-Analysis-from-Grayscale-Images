# Specimen Intensity Analysis from Grayscale Images

This script processes a folder of grayscale images to automatically identify biological specimens, extract a central region of interest (ROI), and compute intensity-based metrics. It is intended for researchers or practitioners analyzing imaging data from biological assays, materials samples, or microscopy workflows.

## Features

- Automatically detects and segments the largest specimen in each image.
- Identifies the centroid of the specimen and defines a circular ROI covering 20% of its area.
- Calculates intensity statistics for:
  - The full specimen,
  - The central ROI,
  - The surrounding specimen outside the ROI.
- Computes an intensity ratio between the center and surrounding regions.
- Generates a CSV file with compiled results for all images.
- Displays a verification overlay for the first successfully processed image.

## Requirements

- Python 3.x
- Libraries:
  - `opencv-python`
  - `numpy`
  - `matplotlib`
  - `pandas`

You can install these using pip:

```bash
pip install opencv-python numpy matplotlib pandas
```

## Usage

1. Place all images to be processed in a single folder.
2. Update the `folder_path` variable in the script to point to your image directory.
3. Run the script:

```bash
python intensity_analysis.py
```

4. After processing, a file called `compiled_intensity_data.csv` will be saved in the same folder.
5. A plot showing the specimen outline, ROI, and centroid will appear for the first valid image.

## Supported Image Formats

- `.png`, `.jpg`, `.jpeg`, `.tif`, `.tiff`

## Example Output

The script generates the following data for each image:

| Filename   | Specimen Area (pixels) | Center ROI Target Area (pixels) | Mean Intensity (Full Specimen) | Mean Intensity (Center ROI) | Mean Intensity (Outside ROI) | Intensity Ratio |
|------------|------------------------|----------------------------------|--------------------------------|-----------------------------|------------------------------|-----------------|
| image1.png | 123456                 | 24691.2                          | 145.3                          | 152.7                       | 138.1                        | 1.11            |

An overlay image is also displayed to verify correctness of the segmentation and ROI placement.

## Notes

- Ensure images are in grayscale or can be interpreted in grayscale.
- The script skips any files that cannot be loaded or where no specimen is detected.
- Errors encountered during processing are logged to the console.

## AI Use Disclosure

This project was developed with assistance from generative AI and coding-agent tools. AI was used for coding, debugging, and development support; analytical design, validation, interpretation, and final decisions were performed by the author.
