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
Here, you should put the command needed to run your app, and then the steps that the user should take to use it. You should include screenshots of the app running in your own browser to make it easier to follow along. 

Then, show a step-by-step guide of how your app works, and what each control does.

If possible, include screenshots of something in the app failing, and, if any, the steps that the user can take to correct the error.

There are two versions of this application. A mock version for the user to play with without any instruments connected, and a local version, that can be connected to a device.

If you would like to run the local version, please connect the device to the USB port on your computer, and run in the command line:
``` 
python app.py
```

If the app is run, but the device is not connected you will see something like this:



If you would like to run the mock version, run in the command line:

```
python app_mock.py demo
```
A step by step guide with photos is provided below:

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

