# Stereo Vision Depth Estimation System

## Objective
This project implements a **stereo vision system** to compute depth images from stereo image pairs. It utilizes datasets with pre-defined calibration parameters to accurately generate disparity maps and depth images, which can be applied in various fields such as robotics, autonomous vehicles, and 3D scene reconstruction.

## Key Features

- **Calibration & Rectification**: 
  - Detected and matched features between stereo image pairs.
  - Estimated **Fundamental** and **Essential** matrices.
  - Decomposed the matrices into **rotation** and **translation** components.
  - Rectified images using **homography matrices** to align the stereo image pairs.

- **Depth Map & Image Generation**:
  - Calculated **disparity maps** using the rectified stereo images.
  - Rescaled the disparity maps for **grayscale** and **color visualization**.
  - Generated **depth images** by converting disparity data to depth information.

- **Applications**:
  - Demonstrated the potential for **depth estimation** in applications such as:
    - **Robotics**: For navigation and obstacle detection.
    - **Autonomous Vehicles**: For environment perception and decision-making.
    - **3D Scene Reconstruction**: For creating 3D models of real-world environments.

## Calibration Parameters

The following table describes the parameters used in the `calib.txt` file for stereo image calibration:

| **Parameter** | **Description** |
| ------------- | --------------- |
| **cam0, cam1** | Camera matrices for the rectified views, in the form `[f 0 cx; 0 f cy; 0 0 1]`. |
| **f**         | Focal length in pixels. |
| **cx, cy**    | Principal point coordinates. |
| **doffs**     | X-difference of principal points: `doffs = cx1 - cx0` (usually 0). |
| **baseline**  | Camera baseline in mm. |
| **width, height** | Image dimensions. |
| **ndisp**     | Conservative bound on the number of disparity levels; used by the stereo algorithm to search from `d = 0 .. ndisp-1`. |
| **vmin, vmax** | Tight bounds on minimum and maximum disparities, used for color visualization; stereo algorithm may not use this information. |

## Project Structure

- `Stereo_Vision.ipynb`: The main Jupyter notebook file containing the implementation of the stereo vision system. It walks through the steps of image calibration, rectification, disparity map calculation, and depth image generation.

## Prerequisites

Ensure you have the following dependencies installed:

- **Python 3.x**
- **NumPy**
- **OpenCV**
- **Matplotlib**

To install the dependencies, you can use the following command:

```bash
pip install numpy opencv-python matplotlib
