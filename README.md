# Indian Sign Language Recognition

This repository contains a machine learning pipeline for recognizing Indian Sign Language (ISL) gestures using hand landmarks and translating the predictions into multiple Indian regional languages with audio playback.

## Features
- **Hand Gesture Recognition**: Recognizes alphanumeric hand gestures (A-Z, 0-9) using computer vision.
- **Translation**: Translates the predicted sequence of characters into Hindi, Bengali, Telugu, or Gujarati.
- **Text-to-Speech (TTS)**: Plays the translated text as an audio format in the selected language.
- **GUI Interface**: User-friendly GUI built with Tkinter to view predictions, select translation languages, and play audio.
- **Machine Learning**: Uses a trained classifier (saved as `model.p`) trained on hand landmarks to classify the gestures.

## Tech Stack & Libraries
- **OpenCV** (`cv2`): For real-time webcam image capture.
- **MediaPipe**: For robust hand tracking and extracting 2D hand landmarks.
- **NumPy**: For array manipulations and data padding.
- **Scikit-learn**: For machine learning models (Random Forest, SVM, KNN explored in the project steps).
- **Googletrans**: For translating text to regional Indian languages.
- **gTTS (Google Text-to-Speech)**: For generating speech from the translated text.
- **Tkinter**: For the desktop graphical user interface.

## Project Structure
- `Final.py`: The main execution script. It captures images via the webcam, processes them to extract hand landmarks, predicts the characters, and opens a GUI for translation and audio playback.
- `step1.py` - `step6.py`: Scripts outlining the pipeline from data collection, preprocessing, and training various models (like Random Forest).
- `KNN/` & `SVM/`: Directories containing models or experiments exploring K-Nearest Neighbors and Support Vector Machines for this classification task.
- `model.p`: The finalized serialized machine learning model (Random Forest Classifier).
- `data_padded.pickle`: Serialized padded landmark data used during the training phase.

## Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/PRATYUSH5690/Indian-Sign-Language-Recognition.git
   cd Indian-Sign-Language-Recognition
   ```

2. **Install the required dependencies:**
   Make sure you have Python installed. Then run:
   ```bash
   pip install opencv-python mediapipe numpy scikit-learn googletrans==4.0.0-rc1 gTTS
   ```
   *(Note: `googletrans` might require a specific version like `4.0.0-rc1` to work properly due to API changes).*

## Usage
1. Run the main script:
   ```bash
   python Final.py
   ```
2. The terminal will ask: `How many pictures do you want to capture?`. Enter a number (e.g., 5) to represent the length of the word/characters you want to sign.
3. The script will wait a few seconds and capture frames from your webcam. Form your hand gestures accordingly!
4. Once captured, a Tkinter GUI will pop up showing the predicted string.
5. Select a regional language from the dropdown (Hindi, Bengali, Telugu, Gujarati) to translate the prediction.
6. Click **Play Audio** to hear the translated text.

## Limitations
- The current implementation captures static images at intervals rather than performing continuous real-time sequential recognition.
- Ensure good lighting and a clear background for MediaPipe to accurately map hand landmarks.

## Acknowledgements
Developed utilizing Google's MediaPipe framework for hand tracking and various Python open-source libraries.
