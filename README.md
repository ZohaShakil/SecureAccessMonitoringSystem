# SecureAccessMonitoringSystem
🛡️ Secure Access Monitoring System (SAMS)
A Java-based Defence Operations Security Platform with Role-Based Access Control (RBAC), real-time session monitoring, anomaly detection, and a complete audit logging system — built with a modern dark-themed GUI.

📌 Project Overview
SAMS is a secure access management system designed for defence operations environments. It enforces strict role-based permissions, monitors user sessions in real time, detects unauthorized access attempts, and logs all system activity for forensic review.
Key Highlights:
FeatureDescription🔐 RBAC4-tier role hierarchy (Admin, Commander, Officer, Soldier)📋 Audit LoggingEvery action logged with timestamp and user info🚨 Anomaly DetectionFlags abnormal login times and unauthorized attempts🖥️ Modern GUIDark-themed Java Swing interface🔒 BCrypt HashingSecure password storage⏱️ Session MonitoringAuto-timeout and session tracking

🗂️ Project Structure
SecureAccessMonitoringSystem/
├── src/main/java/

│   ├── Main.java                    # Entry point

│   ├── database/                    # Database layer

│   │   ├── DatabaseConnection.java
│   │   ├── UserDAO.java
│   │   ├── SessionDAO.java
│   │   ├── ActivityLogDAO.java
│   │   └── AlertDAO.java
│   ├── models/                      # Data models

│   │   ├── User.java
│   │   ├── Session.java
│   │   ├── ActivityLog.java
│   │   └── Alert.java
│   ├── ui/                          # User Interface

│   │   ├── LoginFrame.java
│   │   ├── DashboardFrame.java
│   │   ├── AdminFrame.java
│   │   ├── UserManagementFrame.java
│   │   ├── SessionViewerFrame.java
│   │   └── AlertViewerFrame.java
│   ├── security/                    # Security features

│   │   ├── SessionMonitor.java
│   │   ├── AnomalyDetector.java
│   │   ├── RBACManager.java
│   │   └── CommandValidator.java
│   ├── logger/
│   │   └── AuditLogger.java
│   └── utils/
│       └── UIHelper.java
├── pom.xml                          # Maven configuration

└── audit_log.txt                    # Audit logs


👤 Role-Based Access Control
UsernamePasswordRolePermissionsadminadmin123AdminFull access — all commands, audit logs, user managementcommander1pass123CommanderView data, issue commands, access classifiedofficer1pass123OfficerView data, limited classified accesssoldier1pass123SoldierView data only

⚠️ Change passwords after first login in production!


🚀 How to Run
Prerequisites

Java JDK 17+
Apache Maven 3.6+

Verify installations:
bashjava -version
mvn -version
Method 1: Run Scripts (Easiest)
Windows:
bashrun_windows.bat
Linux/Mac:
bashchmod +x run_unix.sh
./run_unix.sh
Method 2: Maven Command Line
bashmvn clean compile
mvn exec:java -Dexec.mainClass="Main"
Method 3: IntelliJ IDEA

File → Open → Select project folder
Set SDK to Java 17+
Run Main.java


🔐 Security Features

✅ BCrypt password hashing — passwords never stored in plaintext

✅ Session monitoring — auto-timeout on inactivity

✅ Failed login tracking — max 5 attempts before lockout

✅ RBAC enforcement — unauthorized commands blocked and alerted

✅ Anomaly detection — flags abnormal access timing (e.g. 3 AM logins)


✅ Full audit logging — every login, command, and alert recorded


📊 Sample Audit Log
[2026-02-11 16:42:09] [INFO]  admin     - MISSION_EXECUTED: Operation Nightfall
[2026-02-11 16:43:32] [HIGH]  ALERT: soldier1 - Unauthorized command attempt
[2026-02-12 00:40:03] [HIGH]  ALERT: admin    - Abnormal access timing detected
[2026-02-13 09:57:22] [INFO]  commander1 - COMMAND_EXECUTED: Deploy Unit Alpha

📦 Dependencies
Managed automatically via Maven:
LibraryVersionPurposeSQLite JDBC3.42.0.0Local databaseBCrypt0.10.2Password hashing

🛠️ Troubleshooting
IssueSolutionJava not foundInstall JDK 17+ from oracle.comMaven not foundInstall Maven from maven.apache.orgDatabase errorDelete sams.db and restart — it auto-recreatesLogin failsUse credentials from table aboveDependencies not downloadingRun mvn clean install -U

🛠️ Technologies Used

Java 17 — Core language
Java Swing — GUI framework
SQLite — Lightweight local database
Maven — Build and dependency management
BCrypt — Password encryption


👩‍💻 Author
Zoha Shakeel
BS Information Technology — NUTECH, Islamabad
Cybersecurity & Software Development

📝 License
© 2025 Defence Operations — All Rights Reserved
