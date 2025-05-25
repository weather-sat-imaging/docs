# 0. 🧪 Proof of concept

A first version of the acquisition chain was made using off-the-shelf components. This version validated the feasibility of the project and helped us identify critical points to consider for the final version. The results were satisfactory, but there is still room for improvement.

Image obtained with the proof of concept setup from NOAA-19 satellite:

![Proof of concept captured image](./images/main/Proof%20of%20concept%20captured%20image.png)

While this first image contain visible clouds and land - water demarcation, it is not very clear. There is also a lot of noise and the top and bottom part of the image are missing due to too much noise.

For this first version, the setup consists of a V-dipole antenna, tuned for the 137Mhz frequency band, and an RTL-SDR v4 receiver. Signal processing and recording were done with SDR++, and image decoding with Sat-dump.

Current setup:

![Proof of concept setup](./images/main/Proof%20of%20concept%20setup.png)
**TODO :** translate the image text to english

The result quality is acceptable but not optimal. Therefore, it is necessary to design a more efficient system. This first attempt also highlighted some critical points to consider:

- the north-south orientation of the V-dipole antenna
- the height of the antenna to allow signals to bounce off the ground
- the dimensions of the antenna arms, which must be adapted to the signal wavelength
- the quality of the transmission chain between the antenna and the receiver

## Antenna

**TODO :** describe the antenna used in the proof of concept

## Software setup

**TODO :** describe the software setup used in the proof of concepts

## Locations

**TODO :** describe the locations used in the proof of concept

## Results

**TODO :** describe the results obtained with the proof of concept