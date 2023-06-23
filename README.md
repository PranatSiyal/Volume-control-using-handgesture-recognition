# Volume-control-using-handgesture-recognition
A model to recognize hand gestures using Media-Pipe for building user friendly touchless interface to give commands to the operating system.
## Handtracking module 
Hand detector is a class which takes parameters such as mode, maxHands, complexity, detectionCon, and trackCon to configure the hand detection process.
### The findHands method
Takes an image as input, converts it to RGB format, and processes it using the MediaPipe Hands model to detect hands. It then draws the hand landmarks and connections on the image if the hands are detected.
### The findPosition method
Returns the coordinates of the landmarks for a specific hand. It takes an image and a hand number as input and returns a list of landmark positions.
### In the main function (def main())
A video capture object is created to read frames from the webcam. <br/>
Inside the main loop, the findHands and findPosition methods are called to detect and track hands in the captured frames. The landmark positions for the index finger (landmark ID 4) are printed.<br/>
The code also calculates and displays the frames per second (FPS) on the image.<br/>
The processed image is displayed in a window using cv2.imshow, and the loop continues until the user presses any key.<br/>

## Main.py
**1**. The code sets up the webcam and initializes variables for volume control.<br/>
**2**. A loop is started to continuously capture frames from the webcam.<br/>
**3**. Inside the loop, the hand detector is used to detect and track hands in the captured frames.<br/>
**4**. The positions of specific landmarks on the hand (index finger and thumb) are extracted from the hand detector.<br/>
**5**. The code calculates the distance between the two landmarks using the math.hypot function.<br/>
**6**. The distance is mapped to the volume range and adjusted using the np.interp function.<br/>
**7**. The volume level is set using the volume.SetMasterVolumeLevel method from the PyCaw library.<br/>
**8**. The code visualizes the volume adjustment on the screen by drawing circles and rectangles.<br/>
**9**. The code also calculates and displays the frames per second (FPS) on the screen.<br/>
**10**. The processed image is displayed in a window using cv2.imshow, and the loop continues until the user presses any key.
