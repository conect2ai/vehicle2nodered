## Introduction

Modern vehicles have a variety of sensors that constantly generate a vast amount of information. During a car trip, for example, these sensors can collect data about the travel time, the speeds reached during the trip, the emission of gases into the atmosphere, and many other important information.

Using a device called On-Board Diagnostics II (OBD-II), it is possible to read the values from these sensors and perform a comprehensive analysis of the collected data. In this way, this project aims to create a server that establishes a data flow, allowing the capture, sending, processing, and storage of this data in a time-series database. This information can later be used by data scientists to solve problems and perform advanced analysis.

## The big picture

To create an efficient data flow that allows the analysis of the information coming from a vehicle, several tools were used, each one responsible for a specific step of the process.

First, to perform the **sensor reading**, the **OBD-II** device was used, which is connected to a specific location on the vehicle and is responsible for collecting the sensor values. Then, the **Torque App Pro** application, available on Android smartphones, is connected via bluetooth to the OBD-II to **capture the data** provided by it. This app allows the selection of which sensors will be measured during a trip, allowing the creation of a customized vehicle profile.

After this step, the captured data is sent to a server created with the **Node-Red** tool, which performs the **pre-processing** of the data to leave it in a standard format for. This step is followed by the **data storage** in the **Timescale** database, a Postgres-based database with specific features for time series storage.

Finally, for the **data analysis** step, the **Google Colaboratory** is used, a tool that allows the application of data science algorithms to analyze the information captured by the OBD-II, such as average travel time, speed and route taken by the driver. With these tools together, it is possible to create a complete data stream and perform advanced analysis.

![image info](./img/final-bigpicture-nodered.png)
