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
3. Open a web browser on your PC and go to `https://<YOUR_HOLOLENS_IP_ADDRESS>`.
4. Ignore any security certificate warnings.
5. Create or enter a username and password.
6. Navigate to `View -> Mixed Reality Capture -> Live preview`.
7. Right-click to copy the live stream link and replace the stream link in the `server.py` code.

## Running the Server Code

After configuring the HoloLens device portal and updating the stream link in `server.py`, run the following command to start the server:

```bash
python server.py
