# Juniper NOC Dashboard & Monitoring System

A comprehensive, asynchronous monitoring and visualization platform designed specifically for Juniper EX2300 switches in a Network Operations Center (NOC) environment[cite: 3]. This system provides real-time telemetry, L2 loop detection, and historical performance tracking[cite: 3].

## 🖥️ System Interface & Dashboard

<p align="center">
  <img width="100%" alt="Juniper NOC Dashboard Screenshot" src="https://github.com/user-attachments/assets/c519a55a-eaca-4a27-8853-56fa5cf45bb8" />
</p>

## 🏗️ System Architecture

The project is divided into two main components: a Python-based asynchronous backend for data collection and a modern Flutter dashboard for real-time visualization[cite: 3].

### Backend Engine (Telemetry & Analysis)
The backend is built with Python and FastAPI, designed for high-performance network monitoring[cite: 3].
*   **Real-time SNMP Poller:** Asynchronously collects CPU utilization, STP topology changes, and interface-specific broadcast/multicast counters[cite: 3].
*   **Loop Detection Engine:** Analyzes SNMP OID deltas (e.g., broadcast packet rates) to identify network instability and pinpoint the source of L2 storms[cite: 3].
*   **Time-Series Storage:** Persists telemetry to InfluxDB for trend analysis and historical queries[cite: 3].
*   **Resilient Connectivity:** Implements circuit-breaker patterns to gracefully handle database or network connection failures[cite: 3].

### Frontend Dashboard (NOC UI)
The frontend is a responsive, modern Flutter web/desktop application tailored for NOC displays[cite: 3].
*   **NOC Dark-Mode Theme:** Optimized for low-light NOC environments and continuous viewing[cite: 3].
*   **Real-Time Status Grid:** Visualizes all monitored switches in a responsive grid layout[cite: 3].
*   **Intelligent Alerting UI:** Color-coded alerts for network storms (Red for source interfaces generating high broadcast traffic, Orange/Yellow for victim interfaces)[cite: 3].
*   **Historical Analysis:** Dedicated screens utilizing `fl_chart` to visualize broadcast and interface health trends over time[cite: 3].
*   **Dynamic Layouts:** Handles variable numbers of interfaces gracefully without UI overflow issues[cite: 3].

## 🚀 Key Benefits

1.  **Proactive Loop Detection:** Rapidly identifies L2 loops and broadcast storms before they cause catastrophic network outages[cite: 3].
2.  **Precise Fault Isolation:** Differentiates between the source of a network storm and the victim interfaces, enabling quicker resolution[cite: 3].
3.  **Real-Time Visibility:** Provides NOC engineers with immediate visual feedback on switch health and performance metrics[cite: 3].
4.  **Historical Context:** InfluxDB integration allows for post-incident analysis and capacity planning based on historical trends[cite: 3].
5.  **Scalable & Non-Blocking:** Asynchronous SNMP polling ensures the system remains responsive even when monitoring multiple devices concurrently[cite: 3].

## 🛠️ Technology Stack

*   **Backend & API:** Python, FastAPI
*   **Network Automation:** PySNMP (Asynchronous), APScheduler
*   **Database & Storage:** InfluxDB (Time-Series), SQLAlchemy, SQLite
*   **Frontend UI:** Flutter, Dart (Cross-platform)
*   **State Management & Networking:** Riverpod, Dio, fl_chart
