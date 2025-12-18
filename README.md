 IoT Sensor Data Pipeline

## Description
This project implements a **real-time IoT sensor data pipeline** using **Kafka**, **PostgreSQL**, **Flask**, and **Plotly**.  

It collects simulated sensor data, stores it in a database, and visualizes it in a live dashboard that updates automatically.  

This is my **own implementation** based on understanding the original concepts, with enhancements like:

- Real-time auto-refresh dashboard
- Local timezone adjustment for timestamps
- Full Docker Compose orchestration

---

## Architecture
[Producer] --> [Kafka Topic] --> [Consumer] --> [PostgreSQL] --> [Flask API] --> [Plotly Dashboard]
**Components:**

1. **Producer:** Simulated IoT sensor sending temperature & humidity to Kafka  
2. **Kafka:** Message broker handling real-time data streams  
3. **Consumer:** Reads Kafka messages and stores them in PostgreSQL  
4. **PostgreSQL:** Stores sensor data with timestamp, temperature, and humidity  
5. **Flask + Plotly UI:** Dashboard fetching JSON data and plotting live graphs  

---

## Features

- **Real-time Dashboard:** Graphs update automatically every 2 seconds  
- **Persistent Storage:** PostgreSQL stores all incoming sensor data  
- **Timezone Handling:** Timestamps are converted to local time (UTC+3)  
- **Dockerized Services:** Kafka, Zookeeper, PostgreSQL, Producer, Consumer, and Flask UI run via Docker Compose  

---

## Setup & Run

1. **Clone the repository**

```bash
git clone https://github.com/AlHaniAbdullah/kafka-iot-dashboard
cd kafka-iot-dashboard
```

2. Run all services using Docker Compose

```bash
docker compose up --build
```

3. Open the dashboard in your browser

```bash
http://localhost:5000
```

## Notes

-Adjust database credentials in app.py if needed (DB_USER, DB_PASS, DB_HOST)

-Make sure Docker Desktop is running before starting

-The dashboard auto-refreshes every 2 seconds

## License

This project is for academic purposes and is open-source.
