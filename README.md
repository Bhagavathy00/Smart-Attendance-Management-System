📌 Smart Attendance Management System (RFID + QR + Cloud)

An IoT-based hybrid attendance system that combines RFID-based identification with QR-based session validation to deliver a secure, real-time, and tamper-proof attendance workflow. The system leverages an edge–cloud architecture with buffering and retry mechanisms to ensure reliability even under unstable network conditions.

🚀 Key Features

📡 RFID-based student identification using ESP32 and MFRC522

🔐 QR-based session validation (Start & End QR) to prevent proxy attendance

☁️ Edge-to-cloud synchronization with buffering and retry handling

⏱️ Timestamp-based verification within authorized session windows

📊 Real-time dashboard for students, staff, and administrators

🌐 Cloud-based validation logic for accurate attendance computation

🏗️ System Architecture

Data Acquisition Layer

Students tap RFID-enabled ID cards on the MFRC522 scanner.

ESP32 captures UID and timestamp, marking partial attendance.

Session Verification

Staff generate Start QR and End QR via a mobile/web interface.

Students scan both QR codes to confirm classroom presence.

Edge Layer

ESP32 buffers RFID data locally.

Implements retry mechanism during Wi-Fi disconnections.

Cloud Layer

Validates attendance only if:

RFID scan exists, and

Both Start & End QR scans fall within the session window.

Dashboard Layer

Displays class-wise metrics, session logs, and student-wise status in real time.

🧠 Attendance Logic
Condition	Attendance Status
No RFID + No QR	Absent
RFID only	Partial
RFID + Valid Start & End QR	Full Attendance
⚙️ Tech Stack

Hardware

ESP32 NodeMCU

MFRC522 RFID Reader

Firmware

Arduino IDE

C/C++

Backend

Node.js

Express.js

Supabase (Database & Auth)

Frontend / Dashboard

Web-based dashboard

QR Code generation & scanning

Connectivity

Wi-Fi

🧪 Implementation Highlights

Edge firmware captures RFID UID with timestamps and queues events locally.

Buffered events are transmitted to the cloud once connectivity is restored.

Backend validates attendance using time-window checks and staff authorization.

Dashboard updates attendance status with sub-2 second latency.

📈 Results

✅ >95% attendance validation accuracy

⚡ Average update latency < 2 seconds

🔄 Reliable performance during Wi-Fi interruptions

🔐 Effective prevention of proxy attendance

📂 Project Structure
Smart-Attendance-Management-System/
│
├── firmware/
│   └── esp32_rfid.ino
│
├── backend/
│   ├── server.js
│   ├── routes/
│   └── database/
│
├── dashboard/
│   └── frontend files
│
└── README.md

🛠️ Future Enhancements

Face recognition as an additional verification layer

Mobile app for students and staff

Role-based analytics and reports

Offline QR validation support
