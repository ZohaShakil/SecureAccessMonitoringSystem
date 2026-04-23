# SecureAccessMonitoringSystem
# 🛡️ Secure Access Monitoring System (SAMS)

A **Java-based Defence Operations Security Platform** with Role-Based Access Control (RBAC), real-time session monitoring, anomaly detection, and a complete audit logging system — built with a modern dark-themed GUI.

---

## 📌 Project Overview

SAMS is a secure access management system designed for defence operations environments. It enforces strict role-based permissions, monitors user sessions in real time, detects unauthorized access attempts, and logs all system activity for forensic review.

### Key Highlights:
| Feature | Description |
|---|---|
| 🔐 RBAC | 4-tier role hierarchy (Admin, Commander, Officer, Soldier) |
| 📋 Audit Logging | Every action logged with timestamp and user info |
| 🚨 Anomaly Detection | Flags abnormal login times and unauthorized attempts |
| 🖥️ Modern GUI | Dark-themed Java Swing interface |
| 🔒 BCrypt Hashing | Secure password storage |
| ⏱️ Session Monitoring | Auto-timeout and session tracking |

---

## 🗂️ Project Structure

```
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
```

---

## 👤 Role-Based Access Control

| Username | Password | Role | Permissions |
|---|---|---|---|
| `admin` | `admin123` | Admin | Full access — all commands, audit logs, user management |
| `commander1` | `pass123` | Commander | View data, issue commands, access classified |
| `officer1` | `pass123` | Officer | View data, limited classified access |
| `soldier1` | `pass123` | Soldier | View data only |

> ⚠️ Change passwords after first login in production!

---

## 🚀 How to Run

### Prerequisites
- Java JDK 17+
- Apache Maven 3.6+

Verify installations:
```bash
java -version
mvn -version
```

### Method 1: Run Scripts (Easiest)

**Windows:**
```bash
run_windows.bat
```

**Linux/Mac:**
```bash
chmod +x run_unix.sh
./run_unix.sh
```

### Method 2: Maven Command Line
```bash
mvn clean compile
mvn exec:java -Dexec.mainClass="Main"
```

### Method 3: IntelliJ IDEA
1. `File` → `Open` → Select project folder
2. Set SDK to Java 17+
3. Run `Main.java`

---

## 🔐 Security Features

- ✅ **BCrypt password hashing** — passwords never stored in plaintext
- ✅ **Session monitoring** — auto-timeout on inactivity
- ✅ **Failed login tracking** — max 5 attempts before lockout
- ✅ **RBAC enforcement** — unauthorized commands blocked and alerted
- ✅ **Anomaly detection** — flags abnormal access timing (e.g. 3 AM logins)
- ✅ **Full audit logging** — every login, command, and alert recorded

---

## 📊 Sample Audit Log

```
[2026-02-11 16:42:09] [INFO]  admin     - MISSION_EXECUTED: Operation Nightfall
[2026-02-11 16:43:32] [HIGH]  ALERT: soldier1 - Unauthorized command attempt
[2026-02-12 00:40:03] [HIGH]  ALERT: admin    - Abnormal access timing detected
[2026-02-13 09:57:22] [INFO]  commander1 - COMMAND_EXECUTED: Deploy Unit Alpha
```

---

## 📦 Dependencies

Managed automatically via Maven:

| Library | Version | Purpose |
|---|---|---|
| SQLite JDBC | 3.42.0.0 | Local database |
| BCrypt | 0.10.2 | Password hashing |

---

## 🛠️ Troubleshooting

| Issue | Solution |
|---|---|
| Java not found | Install JDK 17+ from oracle.com |
| Maven not found | Install Maven from maven.apache.org |
| Database error | Delete `sams.db` and restart — it auto-recreates |
| Login fails | Use credentials from table above |
| Dependencies not downloading | Run `mvn clean install -U` |

---

## 🛠️ Technologies Used

- **Java 17** — Core language
- **Java Swing** — GUI framework
- **SQLite** — Lightweight local database
- **Maven** — Build and dependency management
- **BCrypt** — Password encryption

---

## 👩‍💻 Author

**Zoha Shakeel**  
BS Information Technology — NUTECH, Islamabad  
Cybersecurity & Software Development

---

## 📝 License

© 2025 Defence Operations — All Rights Reserved
