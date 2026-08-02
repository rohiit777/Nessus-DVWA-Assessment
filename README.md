
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
> <img width="1712" height="965" alt="1-nessus-installed" src="https://github.com/user-attachments/assets/b37ae125-08d8-43df-85b2-c811328e2a28" />


### 2. Spinning Up the DVWA Target Environment
Started the Docker daemon service to host the target web application (DVWA) in an isolated local container environment.
> <img width="1718" height="961" alt="2-docker-dvwa" src="https://github.com/user-attachments/assets/89835e9c-fe6f-44fb-81b2-303cadd6c34c" />


### 3. Accessing the Target Web Application
Navigated to `http://127.0.0.1/index.php` using Firefox to verify that DVWA was fully functional and ready for security testing.
> <img width="1715" height="959" alt="3-dvwa-homepage" src="https://github.com/user-attachments/assets/7d488afc-82a6-4ff7-8fdc-5515ceb3cb91" />


### 4. Accessing the Nessus Management Interface
Opened the web dashboard on port `8834` (`https://192.168.117.129:8834`) to manage and monitor scanning activities.
<img width="1714" height="956" alt="Screenshot 2026-07-18 164125" src="https://github.com/user-attachments/assets/80b92e72-1f2d-41c2-8a84-642168c32ec0" />



### 5. Configuring the Scan Policy
Selected the **Basic Network Scan** policy from the Nessus template library to perform host discovery and vulnerability identification on the target machine.
<img width="1715" height="959" alt="5-scan-policy" src="https://github.com/user-attachments/assets/56c72c6d-a2f3-4a3a-8c48-fda16a3c45a3" />



### 6. Executing the Vulnerability Scan
Launched the scan targeting the local web host and monitored real-time progress as Nessus probed the application for active flaws.
<img width="1719" height="959" alt="6-scan-running" src="https://github.com/user-attachments/assets/b6081f1b-781c-4302-99ee-7b3b613d1dfd" />



### 7. Scan Completion & Vulnerability Discovery
Completed the 13-minute assessment cycle, which successfully uncovered **56 vulnerabilities** categorized across various severity levels for analysis.
<img width="1715" height="965" alt="7-scan-completed" src="https://github.com/user-attachments/assets/9906b839-02dd-4073-8c0a-7eb260b071e3" />



---

## 🎯 Conclusion
This lab demonstrates how to set up an end-to-end vulnerability scanning pipeline on Linux. By hosting DVWA in Docker and managing Nessus natively on Ubuntu, I successfully executed a full security assessment that identified critical application and service-level exposure points.
