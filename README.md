# Depth Estimation from Images using MiDaS in Google Colab

This project demonstrates depth estimation from images using the MiDaS model in a Google Colab environment. It enables you to predict depth maps from images, visualize results, and explore 3D representations of depth.

## Features
- **GPU Support**: Utilizes GPU acceleration for faster inference.
- **Pretrained Model**: Downloads and uses MiDaS' lightweight pretrained model.
- **Image Sources**: Supports depth estimation from:
  - Example image
  - URL
  - Uploaded images
  - Webcam capture
- **Visualization Tools**: Visualize results as a depth map, overlay, or 3D scatter plot.
- **Save Results**: Option to save outputs locally or download them.

## Requirements
- Google Colab environment
- Python dependencies (auto-installed):
  - `torch`
  - `timm`
  - `torchvision`
  - `numpy`
  - `opencv-python`
  - `matplotlib`
  - `PIL` (Pillow)

## Setup and Usage

### 1. Install Required Packages
The script installs missing packages automatically. However, you may ensure the required libraries by running:

```bash
!pip install timm
```

### 2. Run the Script
Copy the provided code into a Google Colab notebook and execute it.

### 3. Select an Image Input Method
Upon running the demo (`run_depth_estimation_demo()`), choose from:

- **Option 1**: Process an example image.
- **Option 2**: Provide an image URL.
- **Option 3**: Upload your image.
- **Option 4**: Capture an image using your webcam.

## Key Functions

### 1. Download Pretrained Model
`download_model()`
- Downloads the MiDaS small variant if not already present.

### 2. Depth Estimation
`estimate_depth(img_path, model)`
- Processes an image and generates its depth map.

### 3. Visualization
- `visualize_depth(rgb_img, depth_map, colormap, alpha)`
  - Displays the original image, depth map, and an overlay of the two.
- `visualize_3d(rgb_img, depth_map, downsample)`
  - Creates a 3D scatter plot from the depth map.

### 4. Image Processing
- **From URL**: `process_from_url(url, model)`
- **From Upload**: `process_uploaded_image(model)`
- **From Webcam**: `process_from_webcam(model)`

### 5. Save Results
`save_results(rgb_img, depth_map, depth_colored, overlay)`
- Saves the original image, depth map, colored depth map, and overlay locally.

## Example Workflow
```python
# Initialize and run the demo
run_depth_estimation_demo()
```
Follow the prompts to choose an image source and visualize depth estimation results.

## Output Files
Generated outputs include:
- `original.jpg`: Original RGB image.
- `depth_map.jpg`: Grayscale depth map.
- `depth_colored.jpg`: Depth map with color visualization.
- `overlay.jpg`: Overlay of depth map on the original image.

Download them directly via Colab.

## Troubleshooting

- **Error in Model Loading**: Ensure internet connectivity to download the pretrained model.
- **Slow Performance**: Enable GPU in Colab (Runtime > Change runtime type > Hardware accelerator: GPU).
- **Unsupported Formats**: Only RGB images are supported; convert grayscale or unsupported formats before input.

This project provides a practical and flexible setup for depth estimation tasks, supporting research, education, and experimentation in computer vision.

