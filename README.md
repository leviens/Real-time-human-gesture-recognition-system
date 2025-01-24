# Real-time-human-gesture-recognition-system
This project is a python based webcam integrated system to recognise some human gestures, created to work in real time.
It makes use of a mediapipe model to extract hand landmarkers and then classifies the gestures in real time using a neural network architecture. 
The model uses the keras framework and has been trained from scratch.

## Installation:
1. Download python 3 (a version between 3.7 and 3.12 to be able to run mediapipe, confirmed to work on 3.12.4).
2. Install the required libraries (mediapipe, cv2, tensorflow (confirmed to work on 2.18.0), jupyter notebook to open the notebook and more if needed).
3. Download the Webcam_livemode.ipynb from this repository.

## Usage:
To use, you'll need a webcam. Then, just run the Webcam_livemode notebook until the last part.
Then run the last part whenever you want to open the webcam window, and the system will be online, ready to recognise your hand signs. It will work on both hands (left and right), with different orientations (e.g. palm or the back of the hand), even simultaneusly (and on multiple people).

Ajdust the webcam resolution in the notebook for higher resolution (Full HD), default setting is 1080x720.

Close the window by clicking 'q' on the keyboard.

These are the hand signs it recognises:
1. Thumb up
2. V sign
3. Three
4. Four
5. Stop/Five
6. Okay
7. Rock sign
8. (No sign)

Additional info on the signs (images/video) will be in the 'Gestures' folder and in the demo.

Illumination and setup differences may yield slightly less accurate results.

## Demo:
Watch the demo on Google Drive: https://drive.google.com/file/d/1dfzahXi3ihxk6iCwaSifBRglMyFUQP15/view?usp=sharing

Additional demos:

Same implementation with hand landmarks: https://drive.google.com/file/d/1eQdI_6gFdtqtDqg9Pl2MSwwu6BH6tDuA/view?usp=sharing

Old implementation: https://drive.google.com/file/d/1LaLFVfy8v0FwXdNyh2hdvEY2E0NYWXqv/view?usp=sharing

## Technical details:
The neural network model has been trained from scratch on a refined database, created from raw videos. Additional information on the data pipeline will be found inside the video_to_data notebook.

In short, the videos are processed using various python libraries (such as cv2), and the mediapipe model is run frame by frame extracting hand landmarker data, which is then further refined to create the database.

Each of the raw videos contain one single label, to remove the need for annotations, and they are stored remotely.

The database is then used to train the neural network (which has a 3 layers architecture with dropout after each layer to handle overfitting) using the keras framework.

The model obtains very high accuracy on the test set (99%), with close to perfect performance on every gesture, by various metrics (precision, recall, f1 score).

The videos have been taken by different people and in different cam scenarios, with different webcams, to reduce the bias;
however, most of the data comes from videos of me in my room, therefore when used in different scenarios some loss in performance is to be expected.

A lot of work is done by the mediapipe hand landmarker, and it will work differently with different setups and illumination conditions. 

## Licensing:
This project uses Mediapipe, which is licensed under the Apache License 2.0. You can find the full license at [https://github.com/google/mediapipe/blob/master/LICENSE].
