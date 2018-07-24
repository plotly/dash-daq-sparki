# Dash-Sparki

## Introduction
An application that allows the user to wirelessly control an arduino powered robot known as [Sparki](http://arcbotics.com/products/sparki/). [Play with Sparki here](http://dash-daq-sparki.herokuapp.com/) and learn more about this application from our [blog entry](https://www.dashdaq.io/sparki). //Add link to blog post.


### Sparki
Sparki is a pre-built robot, consisting of: an ultrasonic sensor, piezometer, stepper motor, servos, an RGB LED, and a bluetooth module. This robot is built upon a Arduino microcontroller, and is programmed with Sparkiduino, an Ardunio based IDE.


### dash-daq
[Dash DAQ](http://dash-daq.netlify.com/#about) is a data acquisition and control package built on top of Plotly's [Dash](https://plot.ly/products/dash/). It gives users more accesibility and, key features for data aquistion applications.


## Requirements
It is advisable	to create a separate conda environment running Python 3 for the app and install all of the required packages there. To do so, run (any version of Python 3 will work):

```
conda create -n	[your environment name] python=3.6.4
```
```
source activate [your environment name]
```

To install all of the required packages to this conda environment, simply run:

```
pip install -r requirements.txt

```

and all of the required `pip` packages, as well as the package, will be installed, and the app will be able to run.
 
## How to use the app
There are two versions of this application. A mock version for the user to play with, without any instruments connected, and a local version, that can be connected to a device.

### Local Application
If you would like to run the __**local version**__, first ensure that the following file is uploaded to Sparki using Sparkiduino.

Open the provided file with Sparkiduino,:

```
sparki_arduino.ino
```
and ensure the __**board ArcBotics Sparki**__ and correct port are selected:

![changefail](screenshots/port_board.png)

next upload the file to Sparki:

![changefail](screenshots/upload.png)

If you have issues uploading to Sparki perform a [manual upload](http://arcbotics.com/lessons/manual-upload/).


When the file is uploaded, plug the HC-05 [Bluetooth module](http://arcbotics.com/products/sparki/parts/bluetooth-module/) into Sparki like so:

<img src="screenshots/bluetooth.jpg" width="250">

Now, you can set up the Bluetooth connection bewtween your computer and Sparki, by following the instructions here for [Windows](http://arcbotics.com/products/bluetooth-2-1-module/connecting-your-bluetooth-2-1-module-with-windows-7/), and here for Mac(http://arcbotics.com/products/bluetooth-2-1-module/connecting-your-bluetooth-2-1-module-with-mac-os-x/).

Once you have finished setting up the connection bewteen Sparki and your PC, take the __**serial port path or COM PORT**__ 
and modify it in __**app.py**__:

![changefail](screenshots/port.JPG)


Run the file in the command line like so:

![changefail](screenshots/pythonapp.jpg)

and you should see this:

![changefail](screenshots/runapp.JPG)

Open the web address given to you in your browser and the application will be ready for use:

![changefail](screenshots/openport.JPG)

If the app is run, but the device is not connected you will see something like this:

![changefail](screenshots/no_connection.JPG)

Sometimes the connection drops with Sparki, if you have issues with connection try the following:
1. Turning the Bluetooth on and off on the PC
2. Pressing the reset button on Sparki
3. Running __**app.py**__

### Mock Application
If you would like to run the __**mock version**__, run in the command line:

```
python app_mock.py 
```

![changefail](screenshots/pythonapp_mock.jpg)

and you should see this:

![changefail](screenshots/runmock.JPG)

Open the web address given to you in your browser and the application will be ready for use:

![changefail](screenshots/openport.JPG)

### Controls
* Color Picker: Changes colors of the RGB LED, and the Sparki icon.
* Motion Joystick: Controls the stepper motors in Sparkis wheels, allowing him to move left, right, forwards, and backwards.
* Motion Knob: Controls Sparki's ultrasonic sensor location.
* Gripper Start: Open grippers.
* Gripper Close: Close grippers.
* Gripper Stop: Stop grippers.
* Sweep (Boolean Switch): Puts ultrasonic sensor in sweep mode.
* Sweep: Ultrasonic sensor scans a 180 degree area, and graphs distance of objects every 10 degrees.
* Capture (Boolean Switch): Puts ultrasonic sensor in capture mode.
* Capture: Ultrasonic sensors scans area directly in front of it, and returns distance.
* Detected LED: Green indicates object detected. Red indicated error, or object not detected.
* Beep: Plays a frequency from the piezometer according to the knob frequency.

## Resources
PySerial was used for serial communication, over bluetooth. The API for PySerial can be found [here](http://pyserial.readthedocs.io/en/latest/pyserial_api.html). For programming Sparki, use the Sparkiduino IDE, which also comes with the necessary drivers; you can find the link [here](http://arcbotics.com/lessons/sparkiduino-windows-install-guide/).

