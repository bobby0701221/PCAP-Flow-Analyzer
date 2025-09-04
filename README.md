# 🌐 Flow Visualization & Network Traffic Analysis Tool

An interactive **flow-based network analysis dashboard** built with **Tranalyzer2** and **Streamlit**.  
This tool helps analysts move beyond packet-level inspection by converting PCAP files into **visual summaries** of flows, protocol usage, IP communication patterns, and geolocation maps.

---

## 📑 Table of Contents
1. [Introduction](#-introduction)  
2. [Project Overview](#-project-overview)  
3. [Architecture](#-architecture)  
4. [Implementation](#-implementation)  
5. [Features](#-features)  
6. [Results](#-results)  
7. [Technologies Used](#-technologies-used)  
8. [Future Scope](#-future-scope)  
9. [How to Run](#-how-to-run)  

---

## 📝 Introduction
With the exponential growth of network traffic, **monitoring and analyzing communication flows** has become crucial for **cybersecurity and performance analysis**.  
While tools like Wireshark offer detailed insights, they often overwhelm users with packet-level data.  

This project addresses that gap by building a **simplified, web-based flow visualization tool** that extracts meaningful insights from PCAP files using **Tranalyzer2** and presents them through an **interactive Streamlit dashboard**.

---

## 📊 Project Overview
The system takes **.pcap files** as input and processes them through Tranalyzer2 to generate **flow-level data**.  
It then visualizes the following:
- **Protocol distribution** (Pie Chart)  
- **Top Active Source & Destination IPs** (Bar Graphs)  
- **Communication Table** (with source, destination, protocol, and port)  
- **Geolocation Map** (IP-to-IP communication on world map)  

👉 Unlike advanced versions, this implementation focuses on **core flow visualization** (domain & WHOIS lookups excluded).

---

## 🏗 Architecture
1. User uploads a `.pcap` file via the web interface.  
2. File is saved to the server directory.  
3. **Tranalyzer2** is executed via Python’s `subprocess`.  
4. The generated flow output file is parsed.  
5. Data is visualized in **charts, tables, and maps** using Streamlit & Plotly.  

---

## ⚙️ Implementation

### 🔹 Technologies Used
| Category        | Tool/Library        |
|-----------------|---------------------|
| Flow Analyzer   | Tranalyzer2         |
| Backend Logic   | Python (subprocess, pandas) |
| Frontend        | Streamlit           |
| Visualization   | Plotly, Streamlit   |
| File Handling   | Local Storage       |

---

## 🚀 Features
- **File Upload Module**  
  - Accepts `.pcap` and `.pcapng` files (up to 200MB).  
  - Displays file details (name, size, upload status).  

- **Tranalyzer2 Integration**  
  - Automatically runs after upload.  
  - Extracts flow-level metadata.  
  - Provides downloadable processed file.  

- **Visualization Module**  
  - Protocol Distribution (Pie Chart).  
  - Top 10 Active Source & Destination IPs (Bar Graphs).  
  - IP Geomap (source-destination relationships).  
  - Communication Table (IP, protocol, port).  

---

## 📈 Results
- Successfully uploaded and processed PCAP files (~40MB).  
- Tranalyzer2 ran efficiently and generated clean flow records.  
- GeoMap visualized **414 flows with valid geolocation**.  
- Protocol pie chart highlighted **TCP as the dominant protocol**.  
- Extracted **Top 10 Source & Destination IPs** with bar graph visualization.  

---

## 🛠 How to Run
1. Clone the repository:  
   ```bash
   git clone https://github.com/yourusername/flow-visualization-tool.git
   cd flow-visualization-tool



   Install dependencies:

pip install -r requirements.txt


Make sure Tranalyzer2 is installed and available in your PATH.

Run the Streamlit app:

streamlit run app.py


Open your browser at:

http://localhost:8501


Upload a .pcap file and start analyzing 🚀
