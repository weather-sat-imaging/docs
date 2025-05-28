# Weather satellites imaging

This project aims to develop and implement an autonomous system for capturing images from weather satellites. The ultimate goal is to complete the entire acquisition chain: from the antenna to the signal processing systems, up to displaying the received images on a website. As part of the project we also want to developp some related softwares, such as satellites trajectory prediction and image processing, to enhance the overall system capabilities.

The project is divided into several sub-parts, some of which are optional, to cover the entire chain. Some of the more complex steps can be replaced by existing open-source alternatives but the main interest in redoing them ourselves is to learn how to design them and understand how they work.

As recieving all satellites radio signals is not a simple task, we plan to focus on the most interresting ones, such as NOAA and METEOR wheather satellites. These satellites transmit images in the 137-138 MHz band, which is accessible with a rather simple setup but complex enough for an interresting learning experience.

In the future this project may be extended to other satellites located on other radio bands, but that would requires another setup.

## Project overview

Before the start of the project, a proof of concept was made to validate the feasibility of the project. This proof of concept allowed us to test the reception of signals and the processing of images. The results were satisfactory, but there is still room for improvement cf. [0. Proof of concept](./0.%20Proof%20of%20concept/README.md).

To make the work easier to understand and test, the project is divided into several parts. Each part can be developed and tested independently before being integrated into the final system. This allows for a more modular approach and makes it easier to identify and fix issues.

The newly developped components will first be added to the proof of concept setup, that will help us test them on a working system. Once the components are validated, they will be integrated into the final system.

Overview of the project sub-parts:

- **Antenna**: Design and manufacture of an antenna for receiving fix band RF signals.
- **Reception**: Design and manufacture of a fixed-band RF receiver for signal reception, including filters, IQ separation and analog-to-digital conversion.
- **Signal processing**: Embedded software for signal acquisition to obtain a raw audio recording.
- **Image processing**: Software for processing the audio signal to obtain an image.
- **Trajectory prediction**: Software for predicting satellite trajectories to know when they will be visible and activate the acquisition chain.
- **Display**: Displaying images and trajectories on a website.

![System overview](./images/main/System%20overview.png)
**TODO :** translate the image text to english

### Areas for improvement

The current antenna does not provide optimal quality and remains very sensitive to disturbances and its orientation. It is necessary to replace it with a more efficient antenna to reduce noise and improve image quality. An omnidirectional antenna would be ideal to avoid having to orient the antenna towards the satellite and thus simplify the setup and improve reliability.

The connection between the coaxial cable and the antenna does not take into account the antenna's impedance, which can cause reflections and signal loss. It is therefore important to use a connector adapted to the antenna's impedance.
Similarly, the connection between the coaxial cable and the receiver is not optimal; a connector matching the receiver's impedance should be used.

Signal reception via software, as well as processing to obtain an image, are not automated. It is therefore essential to automate these steps to obtain an image automatically.

## Detailed objectives

This block schematic shows the different parts of the project and their interactions.

![Goal - version 1](./images/main/Goal%20-%20version%201.png)

## Breakdown of the different sub-parts
- [0. 🧪​ Proof of concept](./0.%20Proof%20of%20concept/README.md)
- [1. 📡​ Antenna](./1.%20Antenna/README.md)
- [2. 🔋​ Embedded](./2.Embedded.md)
- [3. 🖥️​ Server](./3.Server.md)
- [4. 🖼️​ Frontend](./4.Frontend.md)

## Workflow management

**TODO :** describe the workflow management system used in the project