# Edge Computing in AR Integrated Autonomous Vehicles

## Summary

In our internship project, we investigate the significant benefits that edge computing introduces in the AR integrated autonomous vehicle computation offloading. We have developed an object detection model and an eye tracking model to form the basis of our computations that need to be performed locally and with the assistance of an edge server. We measure and record various computation resource utilization such as CPU, bandwidth, energy consumption, and latency from executing these various computations locally and with the help of edge computing.

## Project Components

1. **Server Side**: Consists of our object detection model.
2. **Client Side**: Consists of our HoloLens 2 device.

## Server-Side Object Detection

We run the YOLOv8 model on the server side, which receives camera frames from the HoloLens to perform object detection. The detected object information is then transmitted to the HoloLens for rendering.

## Server Code (server.py)

- [server.py](server/server.py): This code is responsible for running the object detection model on the server side.

## Preliminaries

Before running the server code, make sure to install the necessary Python packages, especially YOLOv8, Detect, Segment, and Pose models. These models are pretrained on the COCO dataset and can be obtained from [ultralytics/ultralytics](https://github.com/ultralytics/ultralytics).

## Configuring the HoloLens Device Portal

To configure the HoloLens device portal for streaming:

1. Connect your HoloLens to Wi-Fi.
2. Obtain your device's IP address through the device's network settings.

![HoloLens Device Portal 1](docs/deviceportal_usbncm_ipaddress.jpg)

3. Open a web browser on your PC and go to `https://<YOUR_HOLOLENS_IP_ADDRESS>`.

![HoloLens Device Portal 2](docs/using-windows-portal-img-04.png)

4. Ignore any security certificate warnings.
5. Create or enter a username and password.
6. Navigate to `View -> Mixed Reality Capture -> Live preview`.

![HoloLens Device Portal 1](docs/using-windows-portal-img-07.png)

7. Right-click to copy the live stream link and replace the stream link in the `server.py` code.

## Running the Server Code

After configuring the HoloLens device portal and updating the stream link in `server.py`, run the following command to start the server:

```bash
python server.py
``````

# AR Integrated Autonomous Vehicle Computation Offloading - Client Side

In this section, we'll guide you through setting up and using the client side of our AR Integrated Autonomous Vehicle Computation Offloading project. The client side is developed in Unity and is designed to receive object detection data from the server.

## Table of Contents
- [Introduction](#introduction)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Future Plans](#future-plans)

## Introduction

In our internship project, we investigate the significant benefits that edge computing introduces in AR integrated autonomous vehicles' computation offloading. This section focuses on the client side of the project, which is responsible for receiving object detection data from the server.

We provide a UUID that uniquely identifies detected objects from the server and their corresponding paths for data retrieval purposes, facilitating easy searching and retrieval of data associated with these objects.

## Getting Started

To set up the client side of the project, follow these steps:

1. **Download the Project:**
   - We have provided the necessary Unity project files, including scripts and assets, on OneDrive for your convenience.
   - Download the complete project from the OneDrive link provided by the team.

2. **Copy Files and Folders:**
   - Copy the `BoxCreatorWebSocket.cs` file into the `Assets/Scripts` folder of your Unity project.
   - Replace the `BoundingBoxes` scene in the `Assets/Scenes` folder with the provided scene.
   - Replace the `Prefabs` folder in the `Assets/Prefabs` directory with the provided Prefabs folder.
   - Similarly, copy the `Plugins` folder into the `Assets/Prefabs` folder or follow the provided instructions for downloading the entire project.

3. **Build the Solution:**
   - In Unity, select `File -> Build Settings -> Build` to build a solution for the project to deploy on the HoloLens.

4. **Visual Studio Configuration:**
   - Navigate to the `Build` folder and open the solution file in Visual Studio.
   - Configure Visual Studio for either `DEBUG` or `RELEASE` and set the architecture to `ARM`.
   - Build and run the application on your HoloLens device.

## Usage

Once you have successfully deployed the application on your HoloLens device, follow these steps:

1. **Start the Server:**
   - Run the server to initiate object detection. Ensure that the server is up and running.

2. **Run the HoloLens Application:**
   - Hit the play button in Visual Studio to deploy the application on your HoloLens.
   - Once deployed, you can exit the application on the HoloLens.

3. **Client Operation:**
   - Enjoy the demo as the HoloLens receives and displays object detection data from the server.

## Future Plans

As we continue to develop this project, we have several future plans in mind:

1. **Enhanced Object Rendering:**
   - Add functionalities to render sample Unity assets that represent the class names in a dialog box, along with the object ID and path for retrieval.

2. **Improved User Interface (UI):**
   - Improve the user interface by including a landing page and implementing robust error handling and extensive simulation features.

3. **Integration with Eye Tracking:**
   - Implement functionalities that utilize eye tracking information, such as sending information to the edge server to start or stop object detection based on user gaze.

4. **Voice Commands:**
   - Implement voice commands in addition to eye tracking, enhancing the user experience and control options.

These future plans aim to make the project more versatile, user-friendly, and suitable for a wide range of use cases.

Please feel free to contact us with any questions or feedback regarding this project.

---

**Contributors:**
- [Your Name]
- [Contributor 2 Name]
- [Contributor 3 Name]
- ...

**License:**
This project is licensed under the [License Name]. See the LICENSE file for details.

**Acknowledgments:**
- [Acknowledgment 1]
- [Acknowledgment 2]
- ...
