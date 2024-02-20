MEDIAPIPE :   https://google.github.io/mediapipe/solutions/hands

MY_ARM  :  https://www.instructables.com/Pocket-Sized-Robot-Arm-meArm-V04

HOW TO USE:  view-source:https://github.com/Crazycurly/gesture_MeArm/blob/main/README.md

CIRCUIT CONNECTION: view-source:https://github.com/Crazycurly/gesture_MeArm/blob/main/README.md

!! Important don't use the software serial, it will cause the servo jitter.:   view-source:https://github.com/Crazycurly/gesture_MeArm/blob/main/README.md

1.UPLOAD THE CODE

int default_angle[4] = {75, 90, 90, 60};
make sure remove the bluetooth module from serial pin then upload the code.

2.Install the required libraries
cd python
pip install -r requirements.txt

3.Set up webcam
you can use the normal webcam or an android phone as a webcam through DROIDCAM app.
change the cam_source in the code.

cam_source = "http://192.168.1.100:4747/video"
# 0,1 for usbcam, "http://192.168.1.165:4747/video" for webcam

4.Change the configuration
First, you need to know the servo movement range of your MeArm.

Then, change the configuration in the python code.

x_min = 0
x_mid = 75
x_max = 150

y_min = 0
y_mid = 90
y_max = 180

z_min = 10
z_mid = 90
z_max = 180

claw_open_angle = 60
claw_close_angle = 0
5.Sencond, make sure the debug mode is on.

debug = True
6.Due to different camera viewing angles and resolutions, it may need test and then change the values of the following parameters.

# use angle between wrist and index finger to control x axis
palm_angle_min = -50
palm_angle_mid = 20

# use wrist y to control y axis
wrist_y_min = 0.3
wrist_y_max = 0.9

# use palm size to control z axis
plam_size_min = 0.1
plam_size_max = 0.3


fist_threshold = 7
7.Finally, run the code and enjoy it.
->make sure the com port is correct.

ser = serial.Serial('COM4', 115200)
->change debug mode to False.

debug = False

->run the code.

python main.py

