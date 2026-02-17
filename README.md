# \# AI-Based Ransomware IDPS

# 

# \*\*AI-Based Intrusion Detection \& Prevention System (IDPS) for Ransomware\*\*  

# This project is a capstone for Spring 2026, designed to detect and respond to ransomware attacks in real-time using machine learning, feature engineering, and a modular monitoring agent, with a web dashboard for management and analytics.

# 

# ---

# 

# \## Table of Contents

# 

# \- \[Project Overview](#project-overview)  

# \- \[Architecture](#architecture)  

# \- \[System Components](#system-components)  

# \- \[Tech Stack](#tech-stack)  

# \- \[Installation \& Setup](#installation--setup)  

# \- \[Usage](#usage)  

# \- \[Milestones \& Development Plan](#milestones--development-plan)  

# \- \[Team \& Roles](#team--roles)  

# \- \[License](#license)  

# 

# ---

# 

# \## Project Overview

# 

# This AI-based IDPS continuously monitors a system for suspicious activity across files, processes, network connections, and system events. Using a combination of feature engineering and ML models (Random Forest + XGBoost), the system predicts potential ransomware behavior and executes policy-based responses such as quarantining files, terminating processes, or blocking network connections.  

# 

# A \*\*web dashboard\*\* allows users to visualize system metrics, manage alerts, and control responses manually.

# 

# ---

# 

# \## Architecture

# 

# !\[Architecture Diagram](docs/architecture.png)

# 

# The system is divided into five main components:  

# 

# ---

# 

# \## System Components

# 

# \### 1. Web Dashboard

# \- \*\*Purpose:\*\* User interface for monitoring, management, and configuration  

# \- \*\*Responsibilities:\*\*  

# &nbsp; - Display real-time system status and metrics  

# &nbsp; - Show active alerts and threat history  

# &nbsp; - Provide manual response controls  

# &nbsp; - Visualize detection analytics  

# &nbsp; - Configure system settings  

# \- \*\*Technology:\*\* Flask, Bootstrap, Chart.js, WebSocket  

# 

# \### 2. Detection \& Response Engine

# \- \*\*Purpose:\*\* Core orchestrator coordinating detection and response  

# \- \*\*Responsibilities:\*\*  

# &nbsp; - Run main control loop continuously  

# &nbsp; - Coordinate between all components  

# &nbsp; - Apply decision policies (thresholds, rules)  

# &nbsp; - Execute response actions  

# &nbsp; - Manage alerts and notifications  

# \- \*\*Technology:\*\* Python (threading, queue)  

# 

# \### 3. Feature Engineering

# \- \*\*Purpose:\*\* Transform raw events into ML-ready feature vectors  

# \- \*\*Responsibilities:\*\*  

# &nbsp; - Extract features from raw event data  

# &nbsp; - Time-window aggregation (60-second windows)  

# &nbsp; - Calculate statistical metrics (entropy, rates, counts)  

# &nbsp; - Maintain baseline behavior profiles  

# &nbsp; - Output standardized feature vectors  

# \- \*\*Technology:\*\* Pandas, NumPy  

# 

# \### 4. ML Engine

# \- \*\*Purpose:\*\* Machine learning prediction and model management  

# \- \*\*Responsibilities:\*\*  

# &nbsp; - Load trained Random Forest and XGBoost models  

# &nbsp; - Perform inference on feature vectors  

# &nbsp; - Ensemble voting for final prediction  

# &nbsp; - Return confidence scores  

# &nbsp; - Support model updates/retraining  

# \- \*\*Training Approach:\*\*  

# &nbsp; - Public ransomware datasets (Kaggle/academic)  

# &nbsp; - Synthetic benign behavior collection  

# &nbsp; - Ensemble voting improves accuracy  

# \- \*\*Technology:\*\* scikit-learn, XGBoost, joblib  

# 

# \### 5. Monitoring Agent

# \- \*\*Purpose:\*\* Collect raw system events from the OS  

# \- \*\*Responsibilities:\*\*  

# &nbsp; - Monitor file system (create, modify, delete, rename)  

# &nbsp; - Track processes and parent-child relationships  

# &nbsp; - Monitor network connections  

# &nbsp; - Detect high-entropy files  

# &nbsp; - Push events to queue for processing  

# \- \*\*Technology:\*\* Watchdog, psutil, threading  

# 

# ---

# 

# \## Tech Stack

# 

# \*\*Backend:\*\* Python  

# \- Flask, scikit-learn, XGBoost, Pandas, NumPy, SQLite, Watchdog, psutil  

# 

# \*\*Frontend:\*\*  

# \- Bootstrap 5, Chart.js, Vanilla JavaScript, AJAX/Fetch API  

# 

# \*\*Development Tools:\*\*  

# \- Jupyter Notebook, pytest, Git  

# 

# ---

# 

# \## Installation \& Setup

# 

# 1\. Clone the repository:

# ```bash

# git clone https://github.com/cyber-capstone-spring26/ai-ransomware-idps.git

# cd ai-ransomware-idps

