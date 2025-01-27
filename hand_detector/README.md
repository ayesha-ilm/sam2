# Hand Detection and Segmentation in Videos

## Introduction

This is an example project to show object detection using sam2. This requires a set up of SAM2 as shown in the base repository's README file. A requirements file has also been included for compatible library use.

## Methodology

1. **Data Collection**: We first fragment the video as frames and use the first one as our frame to mark down the hand position.

2. **Identification**: mediapipes hand recognition model is used 

3. **Propagation of Masks**: To ensure consistency across frames, the segmentation masks are propagated from one frame to the next.

4. **Video Compilation**: The processed frames are combined into a final output video, preserving the hand region segmentation for each frame.

## Limitations

1. **Model Accuracy**: While the SAM2 model performs well for hand detection and segmentation, it is not immune to errors. In certain video frames, the model may incorrectly identify the boundaries of the hand, leading to inaccurate segmentation, especially when the hand is in complex poses or overlapping with other objects. While it can be useful to process the video and create a bounding box, it hurts the generalizability of the example tool.

2. **Noise in Segmentation**: The model sometimes propagates unnecessary regions of the body, such as the neck, which can be considered noise. This could lead to inaccurate segmentation results in videos where the hand is close to other body parts, or when there is insufficient contrast between the hand and the background.
