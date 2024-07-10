# Facial and Hand Landmark Detection Using Mediapipe

This project utilizes the Mediapipe library to detect and visualize landmarks on faces and hands in real-time using OpenCV for video capture and display.

## Installation

To run this project, ensure you have the necessary libraries installed. You can install them using pip:

```bash
pip install tensorflow==2.13.0 opencv-python mediapipe matplotlib
```

## Overview

The code provided demonstrates how to use the Mediapipe Holistic model to detect and draw landmarks for poses, faces, and both hands in a video stream. The landmarks are drawn using OpenCV and displayed in real-time.

## Code Explanation

### Libraries Used:

- **opencv-python**: For capturing and displaying video frames.
- **mediapipe**: Provides the Holistic model for multi-task recognition (pose, face, hands).
- **matplotlib**: Used for basic plotting of images (optional for visualizing).

### Functions Defined:

- **mediapipeDetect(img, model)**:
  - Converts the image from BGR to RGB format.
  - Processes the image using the specified Mediapipe model (model).
  - Converts the image back to BGR format after processing.
  - Returns the modified image and detection results.

- **drawLandmarks(img, results)**:
  - Draws landmarks on the image based on the detection results for pose, face, and both hands.
  - Uses different colors and drawing specifications for each type of landmark.

- **drawLandmark(img, results)**:
  - Draws landmarks on the image based on the detection results for pose, face, and both hands.
  - Uses default drawing specifications for connections.

### Main Code Execution:

1. **Video Capture**: Utilizes OpenCV (`cv2.VideoCapture`) to capture frames from a webcam feed (`cap`).
   
2. **Mediapipe Holistic Model Initialization**: Initializes the Holistic model from Mediapipe with specified confidence thresholds (`min_detection_confidence`, `min_tracking_confidence`).
   
3. **Real-time Processing**: Within a loop, reads frames from the video capture, processes them using `mediapipeDetect`, draws landmarks using `drawLandmarks` or `drawLandmark`, and displays the modified frames using OpenCV (`cv2.imshow`).
   
4. **Loop Termination**: The loop continues until the user presses 'q', at which point the video capture is released and all windows are closed (`cap.release()`, `cv2.destroyAllWindows()`).

## Usage

To run the project:

1. Ensure your webcam is connected and accessible.
   
2. Execute the Python script containing the provided code.
   
3. A window titled "OpenCV Feed" will appear showing real-time video with overlaid landmarks.
   
4. Press 'q' to exit the program.

## Dependencies

- **TensorFlow 2.13.0**: Required for the Mediapipe library.
- **OpenCV**: Used for video capture, image processing, and display.
- **Mediapipe**: Provides the Holistic model for multi-task recognition.
- **Matplotlib**: Optional dependency used for image plotting.

## Credits

This project template is inspired by the Mediapipe examples and utilizes its robust library for real-time landmark detection.