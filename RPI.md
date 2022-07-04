# ___Raspberry Pi___

  In this part of our project, we used a rpi as a smart guide for blind people to communicate easily with a deaf person.
  
 ## Overview

  * Setting up Raspberry Pi.
  * Install dependencies needed to operate our model on RPI.

Each step will be explained in more detail below


   

## How to Set Up a Raspberry Pi for the First Time

First, you will need the following 

### Hardware
* A Raspberry Pi computer with an SD card or micro SD card

* A monitor with a cable (and, if needed, an HDMI adaptor)

* A USB keyboard and mouse

* A power supply

* Headphones or speakers (optional)

* An ethernet cable (optional)

### Software
* Raspberry Pi OS, installed using the Raspberry Pi Imager

### Install Raspberry Pi OS using Raspberry Pi Imager
  Many vendors sell SD cards with a simple Rasperry Pi OS installer called NOOBS preinstalled but you can really easily install Rasperry Pi OS yourself using a computer that has an SD card port or using an SD card reader.
  
  * Download and launch the Raspberry Pi Imager using [link](https://www.raspberrypi.com/software/)

  * Insert your SD card into the computer or laptop’s SD card slot.

* In the Raspberry Pi Imager, select the OS that you want to install, We installed Buster OS (32-bit) 

* Select the SD card you would like to install it on then click write. 
* Wait for the Raspberry Pi Imager to finsh writing.
* Insert SD card into your rpi then it will boot up into a graphical desktop.



## Installing dependencies needed for our model
 
  Apps and libraries needed to operate our model 

1. Python version 3.7.2

2. TensorFlow version 2.5
3. OpenCV version 4.5.2
4. NumPy version 1.21
5. Pillow latest version
6. Mediapipe latest version
7. pyttsx3 latest version
8. Webbrowser latest version

## 1. Python download and installation 

* Before we install Python, install the required build-tools (some might already be installed on your system).

            sudo apt-get update -y
            
            sudo apt-get install build-essential tk-dev libncurses5-dev libncursesw5-dev libreadline6-dev libdb5.3-dev libgdbm-dev libsqlite3-dev libssl-dev libbz2-dev libexpat1-dev liblzma-dev zlib1g-dev libffi-dev -y

If one of the packages cannot be found, try a newer version number (e.g. libdb5.4-dev instead of libdb5.3-dev).

* Download and install Python 3.7.2

       wget https://www.python.org/ftp/python/3.7.2/Python-3.7.4.tar.xz
       tar xf Python-3.7.2.tar.xz
       cd Python-3.7.2
       ./configure
       make -j 4
       sudo make altinstall



## 2. OpenCV download and installation

There is two package needed to use OpenCV, download and install them directly using following commands which may take a longer time to process.

         pip install opencv-python==4.5.5.62
         pip install opencv-contrib-python==4.5.5.62


## 3. TensorFlow and NumPy download and installation 

Select suitable version based on ur architecture using this [link](https://github.com/PINTO0309/Tensorflow-bin/tree/main/previous_versions) use link included in Raw format to download suitable version, in our case we choose this build version armv7l which also include NumPy package. Type in terminal commands as follow

         wget https://drive.google.com/uc?export=download&id=1iqylkLsgwHxB_nyZ1H4UmCY3Gy47qlOS

Make sure it downloaded correctly if not download it manually.
Then start change directory to the one you download the package in it, copy the filename then install it by following commands.

         sudo chmod +x [FILENAME YOU COPIED]
         ./[FILENAME YOU COPIED]

Now you have to find the name of your Tensorflow .whl file. Type ls to list the files in your directory and look for a file with a name like tensorflow-(VERSION).whl. VERSION will be a Tensorflow version like 2.5.0. Copy that filename. Replace tensorflow-(VERSION).whl in the code below with the filename you copied.
         
         pip install tensorflow-(VERSION).whl
        
Hint: we modify the array_ops.py file in the package site due to its version conflict with OpenCV. So by opening this file add the following lines 

       from tensorflow.python.ops.math_ops import reduce_prod

Also at the function which define constants named _constant_if_small replace np.prod to reduce_prod.

Now you should have Tensorflow and NumPy installed successfully.


## 4. Pyttsx3 download and installation 
  
Directly installed using 

         pip install pyttsx3

## 5. Webbrowser download and installation 

Directly installed using 

         pip install browser

## 6. Pillow download and installation 

Directly installed using 
        
         pip install Pillow

## 7. MediaPipe download and installation

Directly installed using 

         pip install mediapipe-rpi4

