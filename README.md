# Air Canvas - Virtual Drawing with Hand Gestures

Draw in the air using just your hand movements! Air Canvas is a computer vision application that tracks your hand gestures in real-time and lets you create digital art without touching anything.

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![OpenCV](https://img.shields.io/badge/OpenCV-4.12-green.svg)
![MediaPipe](https://img.shields.io/badge/MediaPipe-0.10-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## ✨ Features

- **Gesture-Based Drawing**: Draw using your index finger
- **5 Color Palette**: Choose from Purple, Blue, Green, Red, or Eraser
- **Color Selection**: Use two fingers to select colors from the palette
- **Real-time Hand Tracking**: Powered by MediaPipe for accurate detection
- **Clear Canvas**: Reset your drawing with a single keypress
- **Smooth Drawing Experience**: Optimized for fluid hand movements

## 🎮 How to Use

### Hand Gestures

- **Draw Mode**: Extend only your **index finger** to draw
- **Select Mode**: Extend both **index and middle fingers** to select colors from the top palette
- **Idle**: Keep fingers down to pause

### Keyboard Controls

- **C**: Clear the canvas
- **Q**: Quit the application

## 🖼️ Demo

When you run the application:

1. Your webcam will activate
2. Show your hand to the camera
3. Use gestures to draw or select colors from the palette at the top

## 🔧 Requirements

- **Python 3.10+** (required for MediaPipe)
- **Webcam** (built-in or external)
- **Operating System**: macOS, Linux, or Windows

## 🚀 Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/JAYP752/air_canvas.git
cd air_canvas
```

### 2. Install Python 3.10

Ensure you have Python 3.10 installed.

**Linux (Ubuntu/Debian):**

```bash
sudo apt update && sudo apt install python3.10 python3.10-venv
```

**macOS (Homebrew):**

```bash
brew install python@3.10
```

**Windows / macOS (Manual):**
Download the installer directly from [python.org](https://www.python.org/downloads/release/python-3100/).

### 3. Create Virtual Environment

```bash
# Create virtual environment
python3.10 -m venv venv

# Activate it
# On macOS/Linux:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the Application

```bash
python main.py
```

## 📦 Dependencies

- **opencv-python** - Video capture and image processing
- **opencv-contrib-python** - Additional OpenCV functionalities
- **mediapipe** - Hand tracking and landmark detection
- **numpy** - Array operations for image manipulation

See `requirements.txt` for complete list of dependencies.

## 🛠️ Troubleshooting

### Camera Not Working

- Ensure your webcam is connected and not being used by another application
- Grant camera permissions to the terminal/Python

### Hand Not Detected

- Ensure good lighting conditions
- Keep your hand clearly visible to the camera
- Try adjusting the detection confidence in `main.py` (lines 10-12)

### Performance Issues

- Close other applications using the webcam
- Reduce video resolution if needed
- Ensure you're using Python 3.10+

## 🎨 Customization

You can customize the drawing experience by modifying `main.py`:

```python
# Change colors (line 17-23)
colors = [
    (255, 0, 255),  # purple
    (255, 0, 0),    # blue
    (0, 255, 0),    # green
    (0, 0, 255),    # red
    (0, 0, 0),      # Eraser
]

# Adjust hand detection sensitivity (line 10-12)
hands = mp_hands.Hands(
    max_num_hands=1,
    min_detection_confidence=0.6,  # Increase for more accuracy
    min_tracking_confidence=0.6    # Increase for smoother tracking
)

# Change brush thickness (line 105)
thickness = 60 if current_color == (0, 0, 0) else 8  # eraser : brush
```

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](#) file for details.

## 🙏 Acknowledgments

- [MediaPipe](https://google.github.io/mediapipe/) by Google for hand tracking
- [OpenCV](https://opencv.org/) for computer vision capabilities

## 🤝 Contributing

Contributions are welcome! Feel free to:

- Report bugs
- Suggest new features
- Submit pull requests

## 📧 Contact

For questions or feedback, please open an issue on the repository.

---

**Enjoy drawing in the air! ✨🎨**
