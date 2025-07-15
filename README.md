# Real-Time Monocular Vision Object Detection and Navigational Assistance System (RT-MVODNAS)

## Overview

**RT-MVODNAS** is a state-of-the-art, real-time vision assistant project designed to provide object detection, depth estimation, navigational guidance, environment description, and face analysis using a monocular camera (webcam/laptop camera). It is built primarily for visually impaired users or for robotics, leveraging advanced AI models and GPU acceleration.

The system combines deep learning models (YOLOv8 for object detection, MiDaS for depth estimation) with speech recognition and text-to-speech to offer a seamless, interactive, and voice-controlled experience. The application features a modern Tkinter GUI, voice command navigation, live camera feed processing, and robust module testing.

---

## Results

Here are some sample outputs from the project:

![Navigation Path ](images/pathNaviDesk.jpg)
*Navigation Assistant: Visualized navigation paths and obstacle avoidance.*


---

## Features

- **Object Detection**  
  Real-time identification and annotation of objects in the camera view using YOLOv8.

- **Depth Estimation**  
  Generates colored depth maps from a single RGB frame using MiDaS. Useful for estimating obstacle distance.

- **Navigation Assistant**  
  Voice-guided navigation to user-specified objects, with path planning, obstacle avoidance, and distance-based commands. Designed for mirrored laptop cameras and robust in cluttered environments.

- **Environment Description**  
  Categorizes and summarizes the surroundings, describing furniture, obstacles, and spatial relationships in natural language.

- **Face Analysis**  
  Detects faces, analyzes lighting/contrast, and describes their position in the frame.

- **Speech Recognition & TTS**  
  Full voice interaction: activate navigation, switch modes, and receive spoken feedback using `speech_recognition` and `pyttsx3`.

- **Performance Monitoring**  
  Tracks CPU, memory, GPU usage, and FPS in real time.

- **Modular Testing**  
  Includes a test harness for validating each module independently.

---

## Project Structure

```
VISIONTECH/
│
├── depth_estimation/
│   ├── depth.py
│   └── __init__.py
│
├── env_description/
│   ├── descriptor.py
│   └── __init__.py
│
├── face_analysis/
│   ├── analyzer.py
│   └── __init__.py
│
├── navigation/
│   ├── navigator.py
│   ├── pathplanner.py
│   └── __init__.py
│
├── object_detection/
│   ├── detector.py
│   └── __init__.py
│
├── tools/
│   └── performance_monitor.py
│
├── config.py
├── gui_interface.py
├── main.py
├── requirements.txt
├── test_modules.py
├── yolov8n.pt
└── vision_assistant.log
```

---

## Requirements

- Python 3.8+
- OpenCV, PyTorch, Ultralytics YOLO, Pillow, Numpy, pyttsx3, psutil, GPUtil, speech_recognition, and other dependencies (see `requirements.txt`)

---

## How It Works

1. **Launch the Application:**  
   `python main.py`  
   The GUI launches, auto-starts the camera, and initializes all modules (object detection, depth, navigation, etc.).

2. **Select a Mode:**  
   Use the left-side buttons to select between Object Detection, Depth Estimation, Navigation, Environment Description, or Face Analysis.

3. **Voice Commands:**  
   - Say "Navigate to [object]" (e.g., "Navigate to chair") to begin voice-guided navigation.
   - Use "Stop navigation", "Pause navigation", or "Resume navigation" to control navigation.
   - Spoken feedback and environment descriptions are provided via TTS.

4. **Real-Time Feedback:**  
   - Annotated camera feed and live descriptions are shown in the GUI.
   - Status labels show FPS and GPU status.
   - Navigation paths are visualized over the video stream.

5. **Testing Modules:**  
   Run `test_modules.py` to validate each component independently.

---

## Use Cases

- **Assistive Technology:**  
  Navigation and scene understanding for visually impaired users.

- **Robotics:**  
  Real-time perception and navigation for autonomous or teleoperated robots.

- **Research/Education:**  
  Computer vision, AI, and HCI demonstration.

---

## Notes

- GPU acceleration is automatically detected and utilized if available.
- The system is modular; each major feature can be used and tested independently.
- For best results, a CUDA-compatible GPU is recommended.

---

## Acknowledgements

- [Ultralytics YOLO](https://github.com/ultralytics/ultralytics)
- [MiDaS Depth Estimation](https://github.com/isl-org/MiDaS)
- OpenCV, PyTorch, and the open-source community.

---

## License

This project is licensed under the MIT License.

---

**Contributions, feedback, and improvements are welcome!**
