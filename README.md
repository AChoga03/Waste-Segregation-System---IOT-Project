# Waste Segregation System (WSS)

An innovative IoT project designed to automate the segregation of waste materials, promoting efficient recycling and reducing landfill contributions. The WSS uses smart sensors and motors to classify and sort waste into specific categories.

## Project Overview

The **Waste Segregation System** is a machine that detects and separates waste into three categories:
- **Metallic Waste** (e.g., aluminum cans)
- **Wet Waste** (e.g., food scraps)
- **Dry Waste** (e.g., paper, plastic)

Using sensors to analyze the characteristics of waste, the system automatically sorts items into their respective bins, improving recycling efficiency.

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
   - **InfluxDB and Grafana Dashboards:** Provide real-time insights into the system's operations, such as waste distribution trends and sorting efficiency.
   - **Azure IoT Hub Dashboards:** Display payload summaries for high-level system monitoring.

---

## Screenshots

### Node-RED Flow  
![Node-RED Flow](path/to/Node-RED-screenshot.jpg)  
*Displays the data flow, from Arduino serial readings to Azure and InfluxDB.*

### Azure IoT Hub Dashboard  
![Azure Dashboard](path/to/Azure-screenshot.jpg)  
*Payloads received from Node-RED for cloud-based monitoring.*

---

## Benefits

- **Automation:** Reduces manual labor in waste sorting.
- **Efficiency:** Enhances recycling processes and minimizes errors.
- **Scalability:** Supports large-scale deployments via Azure and InfluxDB.

---

