🚒 RFID Fire Truck Dispatch System

📌 Project Overview

The RFID Fire Truck Dispatch System is a real-time tracking and dispatch solution using ESP32, Firebase, and Streamlit. It enables fire stations to monitor truck availability and automatically dispatch the nearest available fire trucks during emergencies.

✨ Features

🔹 1. RFID-Based Fire Truck Tracking

Each fire truck is assigned an RFID tag.

ESP32 with an RFID reader scans the tag when a truck enters or leaves the station.

A scan count system determines availability:

Even count = Truck is in the station (Available).

Odd count = Truck is dispatched (Not Available).

Truck status updates in Firebase Realtime Database in real time.

🔹 2. Real-Time Data Sync with Firebase

Stores truck status, scan history, and availability.

RFID scans automatically update Firebase.

Data is accessible via Streamlit web app for monitoring and decision-making.

🔹 3. Smart Dispatch System (Nearest Trucks)

Firefighters enter the fire location in the web app.

The system:

Fetches all available trucks from Firebase.

Calculates distance between each truck's station and the fire location.

Sorts trucks by distance.

Selects the nearest trucks for dispatch.

🔹 4. Request Additional Trucks from Other Stations

If more trucks are needed, the system:

Identifies other nearest fire stations.

Checks truck availability at these stations.

Dispatches additional trucks from the nearest station with available resources.

🔹 5. Interactive Map for Fire Truck & Fire Location

Uses Folium to display an interactive map in the web app.

Shows:

🚒 Fire truck locations (Green = Available, Orange = Dispatched).

🔥 Fire location (Red marker).

🔹 6. Truck Entry & Exit Logging

Logs each truck's entry and exit with timestamps.

Displays detailed history in the web app.

Helps analyze response time and improve efficiency.

🛠️ Tech Stack

Component

Technology Used

Hardware

ESP32, RFID Module

Backend

Firebase Realtime Database

Web App

Streamlit, Folium

Distance Calculation

Geopy

📌 How It Works

🚀 Step 1: Scanning Trucks at the Fire Station

1️⃣ Each truck has an RFID tag.
2️⃣ An ESP32-based RFID reader scans the tag when a truck enters or leaves.
3️⃣ Truck availability is determined based on scan count.
4️⃣ The Firebase Realtime Database updates truck status automatically.

🚀 Step 2: Fire Emergency Reported

1️⃣ Firefighters enter the fire location (latitude/longitude) in the Streamlit web app.
2️⃣ The system fetches all available trucks from Firebase.
3️⃣ It calculates the distance between each truck and the fire location.
4️⃣ The nearest trucks are selected for dispatch.

🚀 Step 3: Dispatch & Request Additional Trucks

1️⃣ Selected trucks are marked as dispatched in Firebase.
2️⃣ If more trucks are needed:

The system finds nearby fire stations.

Requests additional trucks based on distance.
3️⃣ The dispatch event is logged in Firebase.
4️⃣ The interactive map updates in real-time.
5️⃣ The web app displays a timestamped history of truck movement.

🚀 Getting Started

📥 Prerequisites

ESP32 microcontroller

RFID module (MFRC522 or similar)

Firebase Realtime Database account

Python environment with Streamlit installed

Internet connection

🔧 Installation Steps

1️⃣ Clone the Repository

git clone https://github.com/your-username/rfid-fire-truck-dispatch.git
cd rfid-fire-truck-dispatch

2️⃣ Set Up Firebase

Create a Firebase Realtime Database.

Update the Firebase credentials in the code.

3️⃣ Install Required Dependencies

pip install streamlit firebase-admin folium geopy

4️⃣ Run the Web App

streamlit run app.py

5️⃣ Deploy ESP32 Firmware

Flash the ESP32 with the provided RFID scanner code.

Ensure WiFi and Firebase configurations are correct.
