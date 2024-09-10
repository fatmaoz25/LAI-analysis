# LAI-analysis
The contents in this repository are intended to quantify the leaf-area-index (LAI) of leaf images.

# Getting Started:
1. Create a directory called “LAI_Analysis” and store the zipped file with all the images (“CS24_CERCA_PHOTOS.zip”)
2. Extract the file containing all of the images (“CS24_CERCA_PHOTOS.zip”) and store them in a separate folder called “LAI_Extracted.” Organize the extracted files by creating a folder for each sample (named according to the sample i.e. “CN_2WA_1”) to store the image containing the leaves and their bag name.
3. Go through the images and manually crop them using the editing tool. Remove unnecessary objects in the background and make sure the cropped images are stored in a new folder called “LAI_Extracted_Crop” in JPEG format with its corresponding sample name (i.e. “CN_2WA_1”)

*This should be the structure of the folders:
- LAI_Analysis
  - LAI_Extracted
     - Sample1
     - Sample2
     - Sample3
   - LAI_Extracted_Crop
# Python Scripts:
These are the Python scripts corresponding to each step of the process:

## Data Preparation:
- LAI_Perspective.py – Perspective Transformation: Assuming all of the objects in the images are at a slanted angle, this script is intended to give more of a “bird’s eye view” perspective to straighten the objects.
## Mask Creation:
- LAI_YoloV8.py - Automatic Object Detection: This allows you to create masks using YoloV8 trained on the COCO8 dataset with 80 classes for object detection
- LAI_Auto_Mask.py – Automatic Mask Generation: This takes the image and automatically creates masks of everything that the Segment-Anything-Model (SAM) detects
- LAI_Manual_Mask.py – Bounding Box Mask Generation: This takes the image and allows you to create a box around the region-of-interest (ROI) for a custom mask
- LAI_Annotations.py – Custom Object Detection: This allows you to create masks using Yolov8 trained on your own annotated dataset with 2 classes (leaves and ruler) for object detection
## Quantification:
- LAI_Pixels.py – Quantifying LAI: This allows you to obtain pixel counts and convert them into area (cm3) format.
