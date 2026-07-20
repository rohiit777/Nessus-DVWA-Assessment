
# Vulnerability Assessment on DVWA using Tenable Nessus

## 📝 Objective
This project demonstrates a complete web application vulnerability assessment using Tenable Nessus Essentials. The objective was to deploy the Nessus scanner service on an Ubuntu system, target a locally hosted instance of Damn Vulnerable Web Application (DVWA), and execute a comprehensive scan to discover security flaws.

## 💻 Lab Environment
* **Vulnerability Scanner:** Tenable Nessus Essentials (v19.18.1)
* **Scanning OS:** Ubuntu Linux running on VMware
* **Target Application:** Damn Vulnerable Web Application (DVWA) running in Docker (`127.0.0.1`)
* **Management Dashboard:** Mozilla Firefox (`192.168.117.129:8834`)

## 🧠 Key Achievements & Skills
* Deployed and managed the Nessus scanner daemon (`nessusd`) via the Linux command line.
* Orchestrated local containerized environments using Docker to serve vulnerable applications.
* Configured network scan policies and monitored active scan jobs.
* Identified 56 total security vulnerabilities across web and transport layers within a 13-minute scan cycle.

---

## 🚀 Step-by-Step Walkthrough

### 1. Initializing the Nessus Scanner Daemon
Verified the service status of `nessusd` on the Ubuntu virtual machine using `systemctl` to ensure the scanning engine was fully active and listening for local management connections.
> ![Nessus Service Active](images/01-nessus-status.png)

### 2. Spinning Up the DVWA Target Environment
Started the Docker daemon service to host the target web application (DVWA) in an isolated local container environment.
> ![Docker Service Active](images/02-docker-dvwa.png)

### 3. Accessing the Target Web Application
Navigated to `http://127.0.0.1/index.php` using Firefox to verify that DVWA was fully functional and ready for security testing.
> ![DVWA Target Interface](images/03-dvwa-interface.png)

### 4. Accessing the Nessus Management Interface
Opened the web dashboard on port `8834` (`https://192.168.117.129:8834`) to manage and monitor scanning activities.
> ![Nessus Dashboard](images/04-nessus-dashboard.png)

### 5. Configuring the Scan Policy
Selected the **Basic Network Scan** policy from the Nessus template library to perform host discovery and vulnerability identification on the target machine.
> ![Nessus Scan Templates](images/05-scan-policy.png)

### 6. Executing the Vulnerability Scan
Launched the scan targeting the local web host and monitored real-time progress as Nessus probed the application for active flaws.
> ![Scan in Progress](images/06-scan-progress.png)

### 7. Scan Completion & Vulnerability Discovery
Completed the 13-minute assessment cycle, which successfully uncovered **56 vulnerabilities** categorized across various severity levels for analysis.
> ![Scan Completion Summary](images/07-scan-results.png)

---

## 🎯 Conclusion
This lab demonstrates how to set up an end-to-end vulnerability scanning pipeline on Linux. By hosting DVWA in Docker and managing Nessus natively on Ubuntu, I successfully executed a full security assessment that identified critical application and service-level exposure points.
