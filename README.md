# motion-detector
 
## Overview
 
This is a python script that uses OpenCV to detect motion and trigger an alarm through a webcam. The system sends an email alert and plays a beep sound when motion is detected.

## Requirements

- Python 3.x
- OpenCV (`cv2`)
- imutils (`imutils`)
- `winsound` (Windows only)
- `smtplib` and `ssl` for email notifications
- A Gmail account

## Installation

1. **Install Python 3.x** if it's not already installed. You can download it from [python.org](https://www.python.org/downloads/).

2. **Install the required Python packages**:
   ```bash
   pip install opencv-python imutils

3. **Set Up Email Configuration**
   - Edit the `email_sender`, `email_password`, and `email_receiver` with email credentials.
   - `email_sender` is the Gmail account that will send alerts.
   - `email_password` is the password to the Gmail account.
   - `email_receiver` is an email account that will receive the alerts when motion has been detected.
   - This script uses Gmail's SMTP server to send alerts upon motion detection.
   - Ensure that less secure app access is enabled for the sender's Gmail account or use an app-specific password.
  
## How It Works

1. **Video Capture:**
   - The application captures video frames from the webcam using OpenCV and processes them to detect motion
   - The initial frames are used to create a baseline for comparison.

2. **Motion Detection:**
   - Frames are converted to grayscale and blurred to reduce noise.
   - The difference between the current frame and the baseline frame is calculated.
   - The difference calculated is then compared to the threshold to identify significant motion.
  
3. **Alarm Triggering:**
   - If motion is detected consistently, an alarm is triggered.
   - The beep sound and email alert are activated to notify the user.
