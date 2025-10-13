# MediaPipe Pose & Holistic Analysis for Multimodal Interaction Research

> Attribution: Use the script prepared for the focus group session. Attribute to this Envision Box module: [Module](https://www.envisionbox.org/embedded_MergingMultimodal_inPython.html)

A comprehensive tutorial for extracting human pose landmarks using Google's MediaPipe library, specifically designed for **multimodal interaction research** and gesture analysis.

## 🔬 Research Context

This project is based on the [MEDAL Workshop on Multimodal Interaction](https://github.com/Multimodal-Language-Department-MPI-NL/medal_workshop_on_multimodal_interaction/tree/main) by Raquel Fernandez & Esam Ghaleb. It provides tools for:

- **Gesture segmentation** and classification
- **Kinematic feature extraction** for movement analysis  
- **Multimodal similarity analysis** combining speech and gesture features
- **Temporal alignment** of different modalities in conversation

## 🎯 What This Project Does

1. **Pose Landmark Extraction**: Extract 33 body landmarks using MediaPipe Pose or 75+ landmarks (body + hands + face) using MediaPipe Holistic
2. **Model Configuration**: Understand trade-offs between different model complexities (0, 1, 2) and their impact on accuracy vs. speed
3. **Temporal Smoothing**: Learn how tracking affects landmark stability and reduces jitter
4. **Gesture Analysis**: Apply pose extraction specifically for gesture segmentation and multimodal interaction research
5. **Data Visualization**: Plot landmark trajectories and analyze movement patterns

## 📁 Project Structure

```
MediaPipe_keypoints/
├── README.md
├── .gitignore
├── .gitattributes
├── environment.yml
├── notebooks/
│   └── Mediapipe_Pose_Tutorial.ipynb
├── utils/
│   ├── __init__.py
│   └── extract_mp_pose.py          # Required by the notebook
├── scripts/
│   └── pose_cli.py                 # Optional CLI wrapper
├── input_videos/
│   └── .gitkeep                    # Put your .mp4 files here or use webcam=0
├── Mediapipe_results/
│   └── .gitkeep                    # Output directory for processed videos
└── results/
    └── .gitkeep                    # Output directory for keypoints data
```

## 🚀 Quick Start

### Run the Interactive Notebook
```bash
conda env create -f environment.yml
conda activate mp-keypoints
jupyter lab
# open notebooks/Mediapipe_Pose_Tutorial.ipynb
```



## 📊 Smoothing Process

- **Keypoints Array**: Shape `(n_frames, n_landmarks, 4)` where 4 = [x, y, z, visibility]
- **Overlay Videos**: Annotated videos with drawn landmarks saved to `Mediapipe_results/`
- **Raw Data**: Numpy arrays with landmark coordinates for further analysis

## 🔧 Smoothing Techniques

## 📚 Additional Resources

- **MediaPipe Documentation**: [https://mediapipe.dev/](https://mediapipe.dev/)
- **MEDAL Workshop Repository**: [https://github.com/Multimodal-Language-Department-MPI-NL/medal_workshop_on_multimodal_interaction](https://github.com/Multimodal-Language-Department-MPI-NL/medal_workshop_on_multimodal_interaction)
- **Multimodal Interaction Research**: Explore recent papers in gesture analysis and multimodal communication