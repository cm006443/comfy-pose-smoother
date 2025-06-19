# comfy-pose-smoother
Pose smoothing pipeline for OpenPose + ComfyUI

# 🩻 Comfy Pose Smoother

A clean, modular pipeline for processing full videos through OpenPose inside ComfyUI — complete with **temporal smoothing**, **keypoint interpolation**, and **pose visualization**. Designed to fix jittery or incomplete skeletons when subjects are partially cropped (no more floating kneecaps or vanishing heads!).

---

## ✨ Features

- 🎥 Load any `.mp4` video and split into frames
- 🕴️ Detect human keypoints with OpenPose
- 📉 Smooth movement using Kalman filtering
- 🔗 Interpolate missing joints from occlusions/crops
- 🎨 Visualize cleaned-up skeletons overlayed on video
- 🧰 Fully customizable and node-based using ComfyUI

---

## 🧱 Folder Structure
```
comfy-pose-smoother/
├── input/                   # Raw input video folder
│   └── input_video.mp4      # Your video
│
├── output/                  # Processed video + keypoints
│
├── smoothing/               # Smoothing logic
│   ├── kalman_filter.py         # Kalman filter logic
│   └── interpolate_missing.py   # Fills occluded joints
│
├── config/                  # ComfyUI workflow setup
│   └── workflow.json
│
├── launch_comfyui.sh        # Optional start script
└── README.md                # This file
```
---

## 🚀 Getting Started

### 1. Install ComfyUI

```
bash
git clone https://github.com/comfyanonymous/ComfyUI.git
cd ComfyUI
python main.py


2. Download or clone this repo
git clone https://github.com/cm006443/comfy-pose-smoother.git
Or unzip the archive beside your ComfyUI directory.

3. Install Required Extensions
Make sure the following ComfyUI nodes are installed:
controlnet-aux (for OpenPose support)
JSONSaver
PythonScriptExecutor (or equivalent scripting support)

4. Load the Workflow
Open ComfyUI, click Load Workflow, and select:
comfy-pose-smoother/config/workflow.json

Make sure your input video is placed as:
comfy-pose-smoother/input/input_video.mp4

🛠️ Customization
- 🔧 Modify kalman_filter.py and interpolate_missing.py for different smoothing styles or thresholds
- 🖼️ Use a different visualizer node to change how pose data is overlaid
- 🧪 Add new stages (e.g., gesture classification, depth estimation) as needed

💬 Credits
- Built with ❤️ using ComfyUI
- Pose detection powered by OpenPose via controlnet-aux
- Kalman filter via pykalman, interpolation via scipy

📄 License
MIT License — use, remix, and share freely.

> REM: Concepts by me, but all the implementation and coding executed by Copilot

---


