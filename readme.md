# 🌱 Plant Monitoring System

The **Plant Monitoring System** is an IoT-based solution designed to monitor soil moisture and ensure plant health through real-time data collection, cloud storage, and web-based visualization. It leverages cutting-edge technologies for continuous and efficient plant care.

---

## 🛠️ Key Features

- **Data Collection:** Captures soil moisture data using embedded sensors.
- **IoT Communication:** Transmits collected data via HTTP POST requests.
- **Backend Processing:** Manages and stores incoming data securely in InfluxDB.
- **Data Visualization:** Displays real-time data on an interactive web interface.
- **24/7 Cloud Operation:** Services run continuously with public connectivity.
- **Cost-Effective:** Uses affordable hardware like Raspberry Pi Pico W.

---

## 🔧 Technologies Used

### Embedded Device:
- **MicroPython on Raspberry Pi Pico W:** Collects and sends data via HTTP POST.

### Backend:
- **Node.js 23+**: Manages backend logic and APIs.
- **Express.js:** Simplifies server-side routing and API integration.
- **InfluxDB v2.7.10:** Stores and manages time-series data.

### Frontend:
- **React.js:** Creates a responsive and interactive dashboard.
- **Chart.js:** Visualizes real-time sensor data.
- **Tailwind CSS:** Provides a sleek and customizable UI.

### Cloud Platform:
- **Ubuntu 24.04 LTS VPS:** Hosts the backend and frontend.
- **Nginx v1.24.0:** Manages web traffic and acts as a reverse proxy.

---

## 🚀 Getting Started

### Prerequisites

1. **Hardware:** Raspberry Pi Pico W with a soil moisture sensor.
2. **Software:**
   - Node.js 23+
   - InfluxDB v2.7.10
   - Nginx v1.24.0

### Setup Instructions

#### 1. Embedded Device
- Connect sensors to the Raspberry Pi Pico W.
- Upload the MicroPython script from the `Python/` folder to the device.
- Update the endpoint URL in the script:
  ```python
  endpoint = "http://<YOUR_SERVER_IP>:3001/moisture"
  ```
- Run the script to start sending data.

#### 2. Backend Setup
- Navigate to the backend folder:
  ```bash
  cd backend
  npm install
  npm run dev
  ```
- Ensure the backend runs on port 3001.

#### 3. Frontend Deployment
- Deploy frontend files using Nginx:
  ```bash
  sudo cp -r frontend/* /var/www/html/
  sudo systemctl restart nginx
  ```

#### 4. Database Configuration
- Install and configure InfluxDB:
  ```bash
  sudo apt update
  sudo apt install influxdb
  sudo systemctl start influxdb
  sudo systemctl enable influxdb
  ```
- Access InfluxDB through:
  ```bash
  http://<YOUR_SERVER_IP>:8086
  ```

#### 5. System Testing
- Send test data from the Raspberry Pi Pico W.
- Open the web interface to monitor data updates.

---

## 📊 Total Cost of the System

| **Component/Service**      | **Cost**   |
|----------------------------|------------|
| Raspberry Pi Pico W        | $52.00     |
| Soil Moisture Sensor       | $10.00     |
| **Total Cost**             | **$62.00** |

---

## 📊 Dashboard Preview

- **Real-Time Data Display:** Live soil moisture updates.
- **Historical Data Visualization:** Past records with time-series graphs.
- **Alerts and Notifications:** Warnings for abnormal moisture levels.

---

## ⚙️ System Configuration

### **1. Embedded Device Setup:**
- Raspberry Pi Pico W reads soil moisture data and sends HTTP POST requests to the backend.

### **2. Backend Configuration:**
- **Data Handling:**
  - **Receiving Data:** Collects and validates incoming data.
  - **Data Sanitization:** Cleans invalid or corrupted entries.
  - **Data Storage:** Writes records to InfluxDB securely.

### **3. Cloud Service Configuration:**
- **24/7 Availability:** Public services run continuously.
- **Connectivity:** Listens on public ports 80 and 443.
- **Firewall Management:** Routes external traffic securely.

### **4. Data Visualization:**
- Real-time updates through WebSocket.
- Interactive graphs powered by Chart.js.

---

## 🐳 Docker Deployment (Optional)

#### Build and Run with Docker Compose

1. Navigate to the project root:
   ```bash
   cd plant_monitoring_system
   ```
2. Start services:
   ```bash
   docker-compose up --build
   ```
3. Access the dashboard at:
   ```bash
   http://<YOUR_SERVER_IP>:3000
   ```

---

## 📜 License

This project is licensed under the **[MIT License](https://opensource.org/licenses/MIT)**.
See the [LICENSE](LICENSE) file for details.

---

## 📂 Project Resources
- **GitHub Repository:** [GitHub Link](https://github.com/Firoz-Thapa/Plant_Monitoring_System)
---

Thank you for exploring the **Plant Monitoring System**!