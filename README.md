## Overview

This Python script implements a hand-tracking module using the Mediapipe library and OpenCV. The module is encapsulated in a class named `handDetectors`. It provides functionalities for detecting hands in a video feed, drawing landmarks on the detected hands, and extracting the 2D coordinates of specific landmarks.

## Requirements

- Python 3.x
- OpenCV
- Mediapipe

Install the required libraries using:

```bash
pip install opencv-python
pip install mediapipe
```

## Usage

1. Clone the repository or download the script.

```bash
git clone https://github.com/devDurgeshK/handTrackingModule.git
cd handTrackingModule
```

2. Run the script:

```bash
python main.py
```

3. Press 'q' to exit the program.

## Configuration

The `handDetectors` class can be configured by adjusting the initialization parameters in the script:

- `mode`: Hand tracking mode (default: False)
- `maxHands`: Maximum number of hands to detect (default: 2)
- `modelComplexity`: Model complexity (default: 1)
- `detectionCon`: Detection confidence threshold (default: 0.5)
- `trackCon`: Tracking confidence threshold (default: 0.5)

## Functionality

1. **Hand Detection:**
   - The `findHands` method processes the input image to detect hands and, if specified, draws landmarks and connections on the hands.

2. **Landmark Position Extraction:**
   - The `findPosition` method extracts the 2D coordinates of specific landmarks on the detected hand.

3. **Display and Interaction:**
   - The script displays the processed image with detected hands and landmark information.
   - It also calculates and displays the frames per second.

## Contributing

Feel free to contribute to the project by submitting issues or pull requests. Your feedback and enhancements are welcomed!

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Certainly! Below are the documentation sections for the `findHands` and `findPosition` methods in the `handDetectors` class.

### `findHands` Method

The `findHands` method processes an input image to detect hands using the configured parameters. If specified, it also draws landmarks and connections on the detected hands.

#### Method Signature:

```python
def findHands(self, img, draw=True):
```

#### Parameters:

- `img`: Input image (numpy array) in BGR format.
- `draw`: Boolean flag to indicate whether to draw landmarks and connections on the detected hands (default: True).

#### Returns:

The method returns the input image with detected hands and landmarks if drawing is enabled.

#### Example Usage:

```python
# Create an instance of handDetectors
detector = handDetectors()

# Process an image to detect hands and draw landmarks
img_with_hands = detector.findHands(input_image)
```

### `findPosition` Method

The `findPosition` method extracts the 2D coordinates of specific landmarks on a detected hand.

#### Method Signature:

```python
def findPosition(self, img, handNum=0, draw=False):
```

#### Parameters:

- `img`: Input image (numpy array) in BGR format.
- `handNum`: Index of the hand to extract landmarks from (default: 0).
- `draw`: Boolean flag to indicate whether to draw circles around the landmarks (default: False).

#### Returns:

The method returns a list of landmark information, where each element is a list `[id, cx, cy]` representing the landmark ID and its 2D coordinates.

#### Example Usage:

```python
# Create an instance of handDetectors
detector = handDetectors()

# Process an image to detect hands
img_with_hands = detector.findHands(input_image)

# Extract landmark information for the first hand
landmark_info = detector.findPosition(img_with_hands, handNum=0)
```
