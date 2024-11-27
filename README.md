# Waste Segregation System (WSS)

An innovative IoT project designed to automate the segregation of waste materials, promoting efficient recycling and reducing landfill contributions. The WSS uses smart sensors and motors to classify and sort waste into specific categories.

---

## Project Overview

The **Waste Segregation System** is a machine that detects and separates waste into three categories:
- **Metallic Waste** (e.g., aluminum cans)
- **Wet Waste** (e.g., food scraps)
- **Dry Waste** (e.g., paper, plastic)

Using sensors to analyze the characteristics of waste, the system automatically sorts items into their respective bins, improving recycling efficiency.

---

## List of Items Needed

### Hardware Components
- **Arduino UNO** x 1: Main microcontroller board for processing sensor data.
- **Servo Motors** x 2: To open and close the bin lids for waste deposition.
- **Stepper Motor** x 1: For precise movement of the waste sorting mechanism.
- **Inductive Sensor** x 1: To detect metallic waste.
- **Moisture Sensor** x 1: To identify wet waste based on moisture levels.
- **Infrared (IR) Sensor** x 1: Acts as a swipe trigger to detect the presence of waste.
- **Stepper Motor Stand** x 1: To secure the motor in place.
- **3D-Printed R2-D2 Latch** x 1: Used in the sorting mechanism for secure and reliable waste deposition.[Latch youtube](https://www.youtube.com/watch?v=e58yMo2MXdY) - Link for conponent download is in the video description.
- **Wiring and Breadboard**: For electrical connections between components.
- **Power Supply**: To provide necessary voltage to all components.
- **Bins**: For sorting waste into separate categories.
- **Miscellaneous**: Screws, hinges, and other tools for assembly.

### Software Tools
- **Arduino IDE**: For coding and uploading programs to the Arduino board.
- **Node-RED**: For processing sensor data and integrating with cloud services.
- **InfluxDB**: For storing time-series data related to waste processing.
- **Grafana**: For creating real-time dashboards.
- **Azure IoT Hub**: For cloud-based storage and monitoring of data.

---

## How the Project Works

1. **Detection**  
   - An **IR sensor** detects when an item is swiped near the system, triggering the sorting process.
   - The **Inductive Sensor** determines if the waste is metallic.
   - A **Moisture Sensor** measures moisture levels to identify wet waste.

2. **Classification**  
   - If the inductive sensor detects metallic waste, the system categorizes the item as **Metallic Waste**.
   - If the moisture sensor detects high moisture levels, the item is categorized as **Wet Waste**.
   - Otherwise, the waste is classified as **Dry Waste**.

3. **Sorting**  
   - A **Stepper Motor** positions the waste drop mechanism above the correct bin.
   - **Servo Motors** open and close the bin lids to deposit waste into the appropriate compartment.

4. **Data Processing and Storage**  
   - Data from the sensors is sent to **Node-RED**, which processes the readings and categorizes the waste type.
   - The processed data is stored in an **InfluxDB** database and forwarded to **Azure IoT Hub** for cloud storage.

5. **Visualization**  
   - **InfluxDB and Grafana Dashboards** provide real-time data visualization, including the types of waste processed and the frequency of sorting.
   - **Azure IoT Hub** dashboards display payload summaries for monitoring the system's performance.

---

## System Architecture and Workflow

The system integrates **Node-RED**, **InfluxDB**, and **Azure IoT Hub** for seamless data processing and visualization:

1. **Data Input via Node-RED**  
   Serial readings from Arduino sensors are captured using the Node-RED Arduino Serial Block.

2. **Processing in Node-RED**  
   A custom function block, **Process Waste Type**, processes sensor data to determine the waste type (Metallic, Wet, or Dry).  
   - **InfluxDB Function Block:** Stores processed data for time-series analysis.
   - **Azure Payload Function Block:** Sends processed data to Azure IoT Hub for secure cloud storage.

3. **Data Storage and Visualization**  
   - **InfluxDB Allocations and Grafana Dashboards:** Provide real-time insights into the system's operations, such as waste distribution trends and sorting efficiency.
     
   ![InfluxDB Allocations](https://github.com/user-attachments/assets/1e7468a6-9bfd-4ded-ba85-7083732144cc)

   - **Azure IoT Hub Dashboards:** Display payload summaries for high-level system monitoring.

## Basic flow of Data

 **Arduino Sensors** -> **Node-RED (Serial Block)** -> **Process Waste Type** -> **InfluxDB** -> **Azure IoT Hub** -> **Dashboards (InfluxDB/Grafana)**

---

## Screenshots

### Node-RED Flow

![Node-RED Flow](https://github.com/user-attachments/assets/b3368a23-e4ab-44cb-983f-903c2fed9ca7)

*Displays the data flow, from Arduino serial readings to Azure and InfluxDB.*

**Process waste type-Config**

![process waste type](https://github.com/user-attachments/assets/b1b8c872-003a-46f1-a479-ea13e3dd7ac0)

**Azure Payload-Config**

![Azure Payload](https://github.com/user-attachments/assets/6b07a6d8-7f8a-4ab7-843e-98e3968de1e2)

### Azure IoT Hub Dashboard

![Azure Dashboard](https://github.com/user-attachments/assets/a243d757-a512-4cc2-a4b9-3d54514fc56a)

*Payloads received from Node-RED for cloud-based monitoring.*

**Azure Database code snippet**

![Azure db snippet](https://github.com/user-attachments/assets/af2dd624-cae5-407d-ad1e-5c29a4e58685)

### Prototype
![inner view](https://github.com/user-attachments/assets/710a9d4b-94f1-473b-b403-f9489a67d481)
![outer view](https://github.com/user-attachments/assets/0129b172-61ae-42a5-950e-e1411231405c)
![bottom view](https://github.com/user-attachments/assets/6c6c7b20-2cbf-4a5d-83ee-c0337ff48ea5)

---

## Benefits

- **Automation:** Reduces manual labor in waste sorting.
- **Efficiency:** Enhances recycling processes and minimizes errors.
- **Scalability:** Supports large-scale deployments via Azure and InfluxDB.
