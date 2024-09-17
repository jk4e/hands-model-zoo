# Hands Model Zoo 🖐️

A collection of pretrained models for hand gesture recognition (HGR) tasks. Models are ready to use with the APIs and pipelines from [MediaPipe](https://github.com/google-ai-edge/mediapipe) and [Ultralytics YOLO](https://github.com/ultralytics/ultralytics). Visit those project to see how to integrate these model files.

**Note:** If you'd like to test the model directly, visit the [my-hgr GitHub repository](https://github.com/jk4e/my-hgr) or try it out on [my-hgr Streamlit app](https://my-hgr.streamlit.app/).

## Table of Contents

- [MediaPipe Gesture Recognition Models](#for-mediapipe-gesture-recognition)
- [Ultralytics YOLOv8 Models](#for-ultralytics-yolov8)
  - [Detection Models](#detection)
  - [Classification Models](#classification)
- [Usage](#usage)
- [Related Repository](#related-repository)

## For MediaPipe Gesture Recognition

File type: .task file (TensorFlow Lite)

| Model                                       | Available | Test Accuracy | Model Input Shape    | Size (MB) | Num. of Images | Num. of Classes | Trained with none/background class | Class names                                                                                                                    |
| ------------------------------------------- | --------- | ------------- | -------------------- | --------- | -------------- | --------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| [RPS]()                                     | ✔️        | 0.90          | 224 x 224            | 8.3       | 8,100          | 4               | ✔️                                 | `rock`, `paper`, `scissors`, `none`                                                                                            |
| [ASL Count](models/asl_count.task)          | ✔️        | 0.98          | 224 x 224            | 8.3       | 7,100          | 10              | ❌                                 | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `none`                                                                       |
| [ASL Alphabet](models/asl_alphabet.task)    | ✔️        | 0.96          | 224 x 224            | 8.3       | 8,400          | 24              | ❌                                 | `A`, `B`, `C`, `D`, `E`, `F`, `G`, `H`, `I`, `K`, `L`, `M`, `N`, `O`, `P`, `Q`, `R`, `S`, `T`, `U`, `V`, `W`, `X`, `Y`, `none` |
| [Default](models/gesture_recognizer.task)\* | ✔️        | -             | 192 x 192, 224 x 224 | 8.3       | 30,000         | 8               | -                                  | `Unknown`, `Closed_Fist`, `Open_Palm`, `Pointing_Up`, `Thumb_Down`, `Thumb_Up`, `Victory`, `ILoveYou`                          |

\* Default model is provided by MediaPipe (Model name: `HandGestureClassifier` or `Default` (in MP Studio)). For more information, see [Model card for Hand Gesture Classification](https://storage.googleapis.com/mediapipe-assets/gesture_recognizer/model_card_hand_gesture_classification_with_faireness_2022.pdf).

## For Ultralytics YOLOv8

File type: .pt file (PyTorch)

### Detection

| Model                                         | Model Input Shape | Size (MB) | Num. of Classes | Class names                                                                                                                      |
| --------------------------------------------- | ----------------- | --------- | --------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| [RPS](models/rps_detect.pt)                   | 640               | 12.1      | 3               | `Rock`, `Paper`, `Scissors`                                                                                                      |
| [ASL Alphabet](models/asl_alphabet_detect.pt) | 640               | 6.1       | 26              | `A`, `B`, `C`, `D`, `E`, `F`, `G`, `H`, `I`, `J`, `K`, `L`, `M`, `N`, `O`, `P`, `Q`, `R`, `S`, `T`, `U`, `V`, `W`, `X`, `Y`, `Z` |
| [AI Open Palm](models/ai_open_palm_detect.pt) | 640               | 6.1       | 1               | `open_palm`                                                                                                                      |
| [AI Hands](models/ai_hands_detect.pt)         | 640               | 6.1       | 1               | `hand`                                                                                                                           |

### Classification

| Model                                           | Model Input Shape | Size (MB) | Num. of Classes | Class names                                                                                                                          |
| ----------------------------------------------- | ----------------- | --------- | --------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| [RPS](models/rps_classify.pt)                   | 640               | 5.8       | 4               | `rock`, `paper`, `scissors`, `background`                                                                                            |
| [Hand](models/hand_classify.pt)                 | 640               | 8.6       | 2               | `hand`, `background`                                                                                                                 |
| [ASL Count](models/asl_count_classify.pt)       | 224               | 10.0      | 11              | `0`, `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `background`                                                                       |
| [ASL Alphabet](models/asl_alphabet_classify.pt) | 224               | 10.1      | 25              | `A`, `B`, `C`, `D`, `E`, `F`, `G`, `H`, `I`, `K`, `L`, `M`, `N`, `O`, `P`, `Q`, `R`, `S`, `T`, `U`, `V`, `W`, `X`, `Y`, `background` |

## Usage

Download the models and integrate them into your application for testing or demonstration purposes. These models are not production-ready and should only be used for quick testing or to explore potential capabilities. Model accuracy may vary depending on the input images.

## Related Repository:

- [Custom Hand Gesture Recognition Models (HGR)🖐️ with YOLOv8🚀 and MediaPipe👋 - Streamlit App](https://github.com/jk4e/my-hgr): Streamlit app with MediaPipe and Ultralytics YOLOv8 hand gesture recognition (HGR) demos using custom trained models.
- [AI Hands Dataset](https://github.com/jk4e/ai-hands-dataset): An AI image-generated hand dataset for object detection.

## Disclaimer

This project is for educational purposes only.
