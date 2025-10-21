# MediaPipe Keypoint Extraction

> Attribution: Based on work from the [MEDAL Workshop on Multimodal Interaction](https://github.com/Multimodal-Language-Department-MPI-NL/medal_workshop_on_multimodal_interaction) and Wim Pouw's [envisionBOX modules](https://github.com/WimPouw/envisionBOX_modulesWP).

A streamlined tool for extracting human pose keypoints from videos using Google's MediaPipe Holistic library. The extracted data is saved as CSV files for further analysis in multimodal interaction research.

## Overview

This module generates motion tracking data from videos using Google's MediaPipe Holistic library to extract human pose landmarks across all video frames.

## What This Module Does

1. **Extracts MediaPipe Holistic landmarks** from video files:
   - 33 body landmarks (with X, Y, Z coordinates + visibility scores)
   - 42 hand landmarks (21 per hand, with X, Y, Z coordinates)
   - 478 face landmarks (with X, Y, Z coordinates)

2. **Exports time series data** as CSV files:
   - `*_body.csv` - Body keypoints
   - `*_hands.csv` - Hand keypoints
   - `*_face.csv` - Face keypoints

## Project Structure

```
MediaPipe_keypoints_extraction/
├── README.md
├── environment.yml
├── notebooks/
│   └── Mediapipe_Pose_Tutorial.ipynb  # Main extraction notebook
├── input_videos/
│   └── (place your .mp4 video files here)
├── Mediapipe_results/
│   └── (CSV files will be saved here)
└── utils/
    └── __init__.py
```

## Quick Start

### 1. Set up the environment
```bash
conda env create -f environment.yml
conda activate mp-keypoints
```

### 2. Add your videos
Place your video files (.mp4) in the `input_videos/` folder.

### 3. Run the notebook
```bash
jupyter lab
# Open notebooks/Mediapipe_Pose_Tutorial.ipynb and run all cells
```

### 4. Get your results
CSV files will be saved in the `Mediapipe_results/` folder with the following naming convention:
- `<video_name>_body.csv`
- `<video_name>_hands.csv`
- `<video_name>_face.csv`

## Output Format

Each CSV file contains frame-by-frame time series data:
- **Time column**: Milliseconds from start of video
- **Body CSV**: X, Y, Z, visibility for 33 body landmarks (133 columns + time)
- **Hands CSV**: X, Y, Z for 42 hand landmarks (126 columns + time)
- **Face CSV**: X, Y, Z for 478 face landmarks (1434 columns + time)

## Next Steps

The extracted CSV files can be used for:
- **Smoothing and normalization** (see `../Smoothing/` module)
- **Kinematic analysis** - speed, acceleration, jerk (see `../Speed_Acceleration_Jerk/` module)
- **Gesture segmentation** (see `../Submovements_Holds/` module)
- **Multimodal merging** with ELAN annotations (see `../Merging_Motion_ELAN/` module)

## Additional Resources

- **MediaPipe Documentation**: [https://mediapipe.dev/](https://mediapipe.dev/)
- **MEDAL Workshop Repository**: [https://github.com/Multimodal-Language-Department-MPI-NL/medal_workshop_on_multimodal_interaction](https://github.com/Multimodal-Language-Department-MPI-NL/medal_workshop_on_multimodal_interaction)
- **Wim Pouw's envisionBOX**: [https://github.com/WimPouw/envisionBOX_modulesWP](https://github.com/WimPouw/envisionBOX_modulesWP)