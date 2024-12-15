# 🌿 **Plant Monitoring System**

The **Plant Monitoring System** is an IoT-based project designed to monitor and display soil moisture levels in real-time. It uses a combination of embedded devices, cloud services, and a user-friendly dashboard to ensure continuous monitoring and efficient plant care.

---

## 📌 **Project Overview**

This system collects data using a **Raspberry Pi Pico W** with a connected soil moisture sensor. The data is sent to a backend server hosted on a cloud-based Virtual Private Server (VPS), where it is processed and stored in **InfluxDB**. The real-time data is displayed on a web-based dashboard, providing insights and alerts for optimal plant health.

---

## 🌟 **Key Objectives**

1. **Real-Time Data Collection**: Continuously monitor soil moisture using a sensor.
2. **Secure Data Storage**: Store readings securely in InfluxDB.
3. **Interactive Visualization**: Display data on a dashboard with real-time updates.
4. **Cloud Accessibility**: Ensure the system operates 24/7 with public access.
5. **Cost-Effectiveness**: Use affordable hardware and open-source tools.

---

## 🛠️ **System Components**

### 🔹 **Embedded Device**
- **Raspberry Pi Pico W**
  - Collects soil moisture data.
  - Sends data to the backend server using **HTTP POST requests**.
- **MicroPython Code**: Reads sensor values and transmits them periodically.

### 🔹 **Backend Server**
- **Node.js 23**: Handles HTTP requests, processes incoming data, and broadcasts updates.
- **InfluxDB v2.7.10**: Stores time-series data efficiently.
- **WebSocket**: Provides real-time updates to the dashboard.

### 🔹 **Cloud Hosting**
- **Ubuntu 24.04 VPS**: Reliable server for hosting backend and frontend services.
- **Nginx v1.24.0**: Manages HTTP/HTTPS traffic for the dashboard and backend APIs.

### 🔹 **User Interface**
- **React.js**: Builds a responsive and interactive dashboard.
- **Chart.js**: Visualizes real-time data trends.

---

## 📈 **System Workflow**

1. **Data Collection**: The soil moisture sensor reads values and transmits data to the backend API.
2. **Backend Processing**:
   - Data is sanitized and validated.
   - Valid readings are stored in InfluxDB.
   - Latest data is broadcasted to connected clients via WebSocket.
3. **Data Visualization**: The React-based dashboard displays real-time and historical moisture levels using interactive graphs.
4. **Cloud Configuration**:
   - Public ports **80** (HTTP) and **443** (HTTPS) are configured for accessibility.
   - Firewall settings ensure secure routing of traffic to backend and frontend services.

---

## 🚀 **Setup Instructions**

Follow these steps to set up the Plant Monitoring System:

### 1️⃣ **Embedded Device Setup**
1. Connect the soil moisture sensor to **Raspberry Pi Pico W**.
2. Upload the MicroPython script to the device.
3. Update the backend server endpoint in the script:
   ```python
   endpoint = "http://<YOUR_SERVER_IP>:3001/moisture"
   ```
4. Run the script to start collecting and sending data.

### 2️⃣ **Backend Installation**
1. Navigate to the backend directory:
   ```bash
   cd backend
   ```
2. Install dependencies:
   ```bash
   npm install
   ```
3. Start the server:
   ```bash
   npm run dev
   ```
4. Ensure the server is running on **port 3001**.

### 3️⃣ **Database Configuration**
1. Install InfluxDB on your VPS:
   ```bash
   sudo apt update
   sudo apt install influxdb
   sudo systemctl start influxdb
   ```
2. Access InfluxDB at:
   ```
   http://<YOUR_SERVER_IP>:8086
   ```
3. Create a bucket named `plant-monitoring-system`.

### 4️⃣ **Frontend Deployment**
1. Copy frontend files to Nginx's web root directory:
   ```bash
   sudo cp -r frontend/* /var/www/html/
   sudo systemctl restart nginx
   ```
2. Access the dashboard via your server's public IP or domain.

---

## 💰 **System Costs**

| **Component/Service**        | **Cost**   |
|------------------------------|------------|
| Raspberry Pi Pico W          | $52.00     |
| Soil Moisture Sensor         | $10.00     |
| **Total Cost**               | **$62.00** |

---

## 📊 **Dashboard Features**

1. **Real-Time Updates**: Moisture levels are updated instantly using WebSocket.
2. **Historical Data**: View moisture trends over time with line graphs.
3. **Alerts**: Visual notifications for abnormal moisture levels.

---

## 🔒 **System Reliability**

- **Continuous Operation**: Services operate 24/7 with cloud hosting.
- **Security**: Firewall configurations allow secure public access on ports **80** and **443**.
- **Data Handling**:
   - Incoming data is validated to ensure reliability.
   - Logs track all incoming requests for monitoring purposes.

---

## 🐳 **Optional: Docker Deployment**

Deploy the system using Docker for simplified setup:
1. Navigate to the project directory:
   ```bash
   cd plant_monitoring_system
   ```
2. Run Docker Compose:
   ```bash
   docker-compose up --build
   ```
3. Access the dashboard at:
   ```
   http://<YOUR_SERVER_IP>:3000
   ```

---

## 📂 **Additional Resources**
- **GitHub Repository**: [Project Link](https://github.com/Firoz-Thapa/Plant_Monitoring_System)
- **Demo Video**: [Watch on YouTube](https://youtu.be/1gQZejyTcGo)

---

## 🙌 **Acknowledgments**
This project was developed with a focus on simplicity, efficiency, and cost-effectiveness to help improve plant care through IoT technology.

---

Thank you for exploring the **Plant Monitoring System**! 🌱
