Player Detection and Jersey Number Tracking Tool

This tool uses TensorFlow’s PoseNet model to detect football (soccer) players and their movements in real time via a live video feed. It also integrates Tesseract.js for Optical Character Recognition (OCR) to detect and display jersey numbers above the players’ heads. The live feed is sourced from the back camera (non-mirrored), providing accurate tracking of players on the field.

Features

	•	Real-Time Player Detection: Detects player positions based on key body points (such as head and shoulders) using PoseNet.
	•	Jersey Number Recognition: Uses Tesseract.js to detect jersey numbers dynamically from a designated area (between the shoulders) and overlays the detected number above the player.
	•	Non-Mirrored Back Camera Feed: Ensures that the video feed from the back camera is displayed correctly (not mirrored).
	•	UI/UX Enhancements: Provides a loading screen while models are initializing, and displays live feedback when detection starts.

Requirements

To run this program, you need the following:

	•	A modern browser that supports WebRTC for camera access (e.g., Chrome, Firefox, Safari).
	•	A computer or mobile device with a back camera (environment-facing camera).
	•	Internet connection (to load the PoseNet and Tesseract.js models).

Libraries Used:

	•	TensorFlow.js: For real-time pose detection using the PoseNet model.
	•	Tesseract.js: For Optical Character Recognition (OCR) to detect jersey numbers.

How to Run

Step 1: Set up the HTML file

	1.	Download or copy the HTML file containing the code.
	2.	Ensure you have an internet connection to load the external libraries (@tensorflow/tfjs, @tensorflow-models/posenet, and tesseract.js).

Step 2: Open the HTML file in a Browser

	1.	Open the HTML file in any modern web browser (preferably Chrome or Firefox) on a desktop or mobile device.
	2.	Allow access to the camera when prompted by the browser. Make sure to use the back camera (environment-facing camera).

Step 3: Detection Process

	1.	Once the page loads, you’ll see a loading message while the model is being initialized.
	2.	After loading, the live camera feed will appear on the screen, and player detection will begin automatically.
	3.	The system will detect players based on their body keypoints and attempt to recognize the jersey numbers from the area between the shoulders.
	4.	Detected jersey numbers will be displayed above the players’ heads as they move.

Code Overview

	1.	Video Feed: The camera feed is captured using navigator.mediaDevices.getUserMedia, with the back camera activated by specifying facingMode: { exact: "environment" }.
	2.	Player Detection: PoseNet is used to detect players based on body keypoints, such as shoulders, hips, and head.
	3.	Jersey Number Detection: The tool simulates OCR by drawing bounding boxes in the area between players’ shoulders, which can be processed by Tesseract.js to detect jersey numbers dynamically.
	4.	Canvas Rendering: A canvas is used to draw keypoints and detected jersey numbers on top of the video feed.

File Structure

	•	index.html: The main HTML file containing the program code.

Customization

	•	Pose Thresholds: You can adjust the detection accuracy by modifying the keypoint.score threshold in the JavaScript. For instance, only draw keypoints if the confidence score is above 0.5 (default).
	•	OCR Region: The current setup approximates the jersey area based on the player’s shoulders. You can fine-tune this by adjusting the width, height, and positioning of the bounding box for more accurate OCR detection.

Known Issues & Future Improvements

	•	OCR Accuracy: The Tesseract.js library may struggle to recognize numbers if the video quality or lighting conditions are poor. This can be improved by preprocessing the video frames for better clarity.
	•	Player Tracking: Player movements are tracked in real-time using PoseNet, but further improvements can be made using additional tracking algorithms to reduce flickering or misdetection.
	•	Performance: On lower-end devices, the tool may experience performance drops. Reducing the video resolution or limiting the detection frequency can help.

License

This project is open source and available under the MIT License. Feel free to modify and distribute the code as per the terms of the license.
