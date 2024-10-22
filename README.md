# Live-human-gesture-recognition-system
This project is a python based webcam integrated system to recognise some human gestures, created to work in real time.
It makes use of mediapipe to extract hand landmarkers and then classifies the gestures in real time with a trained model.

## Installation:
1. Download python 3 (a recent version that supports mediapipe)
2. Download the required libraries (mediapipe, cv2, tensorflow and more if needed).
3. Download the progetto_webcam.ipynb from this repository.

## Usage:
To use, you'll need a webcam. Then, just run the progetto_webcam notebook until the last part.
Then run the last part whenever you want to open the webcam window, and the system will be online, ready to recognise your hand signs. It will work on both hands (left and right), one at a time.
Close the window by clicking 'q' on the keyboard.
Hand sign it recognises:
1. Thumb up
2. V sign
3. Three
4. Four
5. Stop/Five
6. Okay
7. (No sign)
Additional info on the signs (images/brief videos) will be in the 'gestures' folder.
