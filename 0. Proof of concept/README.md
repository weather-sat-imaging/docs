# 0. 🧪 Proof of concept

A first version of the acquisition chain was made using off-the-shelf components. This version validated the feasibility of the project and helped us identify critical points to consider for the final version. The results were satisfactory, but there is still room for improvement.

Image obtained with the proof of concept setup from NOAA-19 satellite:

![Proof of concept captured image](./images/Proof%20of%20concept%20captured%20image.png)

While this first image contain visible clouds and land-water demarcation, it is not very clear. There is also a lot of noise and the top and bottom part of the image are missing due to too much noise.

For this first version, the setup consists of a V-dipole antenna, tuned for the 137Mhz frequency band, and an RTL-SDR v4 receiver. Signal processing and recording were done with SDR++, and image decoding with Sat-dump. Current setup:

![Proof of concept setup](./images/Proof%20of%20concept%20setup.png)
**TODO :** translate the image text to english

The result quality is acceptable but not optimal. Therefore, it is necessary to design a more efficient system. This first attempt also highlighted some critical points to consider:

- the north-south orientation of the V-dipole antenna
- the height of the antenna to allow signals to bounce off the ground
- the dimensions of the antenna arms, which must be adapted to the signal wavelength
- the quality of the transmission chain between the antenna and the receiver

## Antenna

The antenna used is a V-dipole antenna tuned for the 137Mhz frequency band. According to ressources found on the internet, the antenna specifications are described below.

### Arm length

We used a half-wave dipole antenna. This allow for shorter arms (1/4 the wavelength) but still provide good gain (2.15 dBi).

The wavelength of 137 Mhz RF is : λ = c / f = 299 792 458 / 137 000 000 = 2.188 m. Where c is the speed of light in m/s and f is the frequency in Hz.
As we used a half-wave antenna, we use half the wave length as the source of the calculations = λh / 2 = 1.094 m.

A dipole antenna has two arms, each arm being 1/4 of the wavelength. Therefore, the length of each arm is : λh / 2 = 1.094 / 2 = 0.547 m.

**Note :** having arms at the correct length is important to ensure the antenna is tuned to the correct frequency. If the arms are too short or too long, the antenna will have a lower gain on the desired frequency and will be less efficient at receiving signals.

#### Wave length in material compared to air

The wave length in the air is different from the wave length in the material used to build the antenna. Usually a conversion factor of 0.95 is applied to the wave length.

**Note :** Some websites provide a simplified formula to calculate the arm length in centimeters: 149 / frequency in MHz. Here, the number 149 represents the speed of light (c) in meters per second, already divided by 2 (for a half-wave dipole) and converted to centimeters by dividing by 1,000,000.

### Arm angle

Dipole antennas are straightline antennas, bending the arms help modify the impedance of the antenna without affecting the gain, frequency or radiation pattern. To achieve an impedance of 50 ohms, the two arms should be separated by an angle of 120°.

**TODO :** add a diagram showing the antenna arms and angle

Achieving the right angle is not crucial for the antenna to work, but even a small missmathch can lead to high / lower impoedance and therefore a lower gain. The antenna will still work, but it will not be as efficient as it could be.

### Antenna height and positionning

The antenne should be placed facing north or south from the miidle of the two arms. Antenna height is also important, any RF signal will bounce on the nearest conductive surface and thus reflet on the antenna. The perfect height is around 1/4 of the wavelength, which is around 0.5 m for the 137 Mhz frequency band.

**Note :** this factor is critical, if the antenna is placed at 1/2 of the wavelength, the reflected signal will canceled the direct signal and the antenna will not receive anything.

Placing the antenna as high as possible may be beneficial to avoid reflections, bt using a reflector right below at 0.5 m will greatly improve the signal quality.

Finnally, the antenna should be placed in an open area, away from any metallic objects that could interfere with the signal. The antenna should also be placed away from any sources of electromagnetic interference, such as power lines or electronic devices.

As the satellites rise and set over the horizon, having a clear line of sight to the satellite is important. This means that the antenna should be placed in an area with a clear view of the sky, without any obstructions such as trees or buildings for maximum signal reception.

## Software setup

**TODO :** describe the software setup used in the proof of concepts

## Locations

**TODO :** describe the locations used in the proof of concept

## Results

**TODO :** describe the results obtained with the proof of concept

## Bibliography

**TODO :** list the resources used to build the proof of concept