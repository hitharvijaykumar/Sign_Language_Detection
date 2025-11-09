<img width="1385" height="128" alt="image" src="https://github.com/user-attachments/assets/f03e5c6b-db33-464d-b654-2fddcc596786" />Sign Language Detection – Real Time (CNN + OpenCV + CVZone)

This project performs real-time Sign Language Recognition using a Convolutional Neural Network (CNN) and a webcam.
The model is trained on the Sign Language MNIST dataset and predicts A-Z hand signs.

Link to the code :
https://colab.research.google.com/drive/1XHdLqJZjWVGJprdxR0FtKJYzCsMVpYhc?usp=sharing

Features

Live webcam hand sign detection

Hand region cropping using CVZone HandDetector

CNN model trained on Sign Language MNIST

Detects 25 hand signs (A-Z, no J or Z because dataset is static)

Requirements

Install these before running:

pip install opencv-python
pip install cvzone
pip install mediapipe
pip install tensorflow
pip install numpy

Project Structure
SignLanguage_RealTime/
│
├── sign_language_cnn_model.h5        # Trained model file
└── realtime_sign.py                  # Real-time prediction script

Model Training (Done in Google Colab)

The model was trained using the Sign Language MNIST dataset:

Dataset Source:
https://www.kaggle.com/datasets/datamunge/sign-language-mnist

The model achieved ~98–99% accuracy and was exported as:

sign_language_cnn_model.h5

Run Real-Time Detection (VS Code / Local Machine)

Make sure your webcam is connected.
Then run:

python realtime_sign.py

🖥️ Code Overview (Real-time Script)

The script:

Captures webcam frames

Detects hand using CVZone

Crops & preprocesses the hand region

Predicts sign using the trained CNN model

Displays the detected label on the video feed

Press q to exit the application.

🔠 Label Mapping (Model Output → Alphabet)

We convert model predictions to letters:

0 → A
1 → B
2 → C
...
24 → Z

Notes

Ensure good lighting for accurate detection.

Keep hand in front of camera, steady for best results.

This model supports static signs only (A-Z except signs requiring movement).

Future Enhancements (Optional)

You can extend this project with:

Feature	Description
Sentence Formation	Combine multiple signs into words
Speech Output	Convert detected signs to spoken audio
GUI Mode	Build a graphical interface using Tkinter / PyQt

Acknowledgements
Dataset: Sign Language MNIST (Kaggle)

Libraries: TensorFlow, OpenCV, CVZone, MediaPipe
