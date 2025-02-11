# Face Blur using OpenCV and MediaPipe

## Overview
Simple Python script that detects faces in images, videos, or webcam feeds and blurs them using **OpenCV** and **MediaPipe**.

## Dependencies
```bash
pip install opencv-python mediapipe
```

## How It Works
The script uses **MediaPipe Face Detection** to locate faces and then applies a **blur effect** to them.

### Modes of Operation
The script supports three modes:
1. **Image Mode** - Processes a single image and saves the output.
2. **Video Mode** - Processes a video and saves the blurred version.
3. **Webcam Mode** - Continuously detects and blurs faces in real-time webcam feed.

## Usage
Run the script with the following command:

### 1. Image Mode
```bash
python script.py --mode image --filePath path/to/image.jpg
```
- Reads the image from `filePath`.
- Detects faces and blurs them.
- Saves the output as `output/output.png`.

### 2. Video Mode
```bash
python script.py --mode video --filePath path/to/video.mp4
```
- Reads the video from `filePath`.
- Processes each frame to blur faces.
- Saves the output as `output/output.mp4`.

### 3. Webcam Mode
```bash
python script.py --mode webcam
```
- Uses the **default webcam** (index `0`).
- Displays real-time face-blurring.
- Press `q` to **exit**.

## Code Explanation

### 1. **Face Detection and Blurring** (`process_img` function)
- Converts the input image to **RGB** (required by MediaPipe).
- Uses MediaPipe's `FaceDetection` model to detect faces.
- Extracts **bounding box coordinates** of detected faces.
- Applies a **blur filter** to the detected face region.

### 2. **Processing Modes**
- **Image Mode**: Loads an image, processes it, and saves the blurred version.
- **Video Mode**: Reads frames from a video, processes them, and saves an output video.
- **Webcam Mode**: Captures frames from a webcam, processes them, and displays them in real-time.

## Output
All processed images/videos are saved in the `output/` directory.

## Exiting Webcam Mode
Press `q` to exit webcam mode.

## Notes
- The script uses **MediaPipe's Face Detection model (model_selection=0)**.
- A **minimum detection confidence of 0.5** is used.
- Blurring is done using `cv2.blur(img, (30, 30))`.

## License
MIT License

