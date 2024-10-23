# Real-time-human-gesture-recognition-system
This project is a python based webcam integrated system to recognise some human gestures, created to work in real time.
It makes use of mediapipe to extract hand landmarkers and then classifies the gestures in real time using a neural network model. 
The model uses the keras framework and it has been trained from scratch.

## Installation:
1. Download python 3 (a version between 3.7 and 3.10 to be able to run mediapipe)
2. Download the required libraries (mediapipe, cv2, tensorflow, jupyter notebook to open the notebook and more if needed).
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
Works better with good illumination and hands not far from the webcam.

## Demo:
Watch the demo on Google Drive: https://drive.google.com/file/d/1LaLFVfy8v0FwXdNyh2hdvEY2E0NYWXqv/view?usp=sharing

## Technical details:
The neural network model has been trained on a refined database, created from raw videos. Additional information on the data pipeline will be found inside the progetto_video_to_data notebook.
In short, the video data is processed using various python libraries (such as cv2), and the mediapipe model is run on every frame extracting hand landmarker data, which is then further refined to create the database.
The raw videos each contain one single label, and they are stored on remote.
The database is then used to train the neural network (which has a 3 layers architecture with dropout after each layer to handle overfitting) using the keras framework.
The model obtains a fairly high accuracy on the test set (98%), so the training has been succesful.
The videos have been taken by different people and in different cam scenarios, with different webcams, to reduce the bias.
However most of the data comes from videos of me in my room, therefore when used in different scenarios some loss in performance is to be expected.
A lot of work is done by the mediapipe hand landmarker, and it will work differently with different setups and illumination conditions. 
Whenever the webcam window shows the raw image, it means that no hand is being recognized by the mediapipe model, so those kind of error are unfixable working on just my model.
