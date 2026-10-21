# ☁️ AWS CloudWatch Infrastructure Monitoring & Alarms

## 🚀 Project Overview
This project demonstrates the implementation of **Amazon CloudWatch** to actively monitor system infrastructure performance. Specifically, it details the tracking of **EC2 CPU Utilization** metrics, the creation of custom visualization dashboards, and the configuration of automated remediation alarms.

---

## 🏗️ Architecture & Metric Flow
The monitoring loop captures real-time server health data and automates infrastructure scaling or team alerts based on predefined performance thresholds:


---

## 📊 Monitoring Configuration Details

### 1. Metric Tracking
* **Metric Monitored:** `AWS/EC2 -> CPUUtilization`
* **Monitoring Interval:** Configured for **Detailed Monitoring** at **1-minute intervals** to ensure high-precision telemetry and rapid incident response.

### 2. Custom Dashboard
A central CloudWatch Dashboard was built to unify infrastructure metrics, providing clean visual timelines across the following views:
* Real-time spike indicators.
* 3-day average utilization trends.
* Aggregated cluster-wide performance grids.

---

## 🚨 Automated Alarm Rules & Actions
To prevent server crashes and minimize downtime, the following multi-tier automated alarm system was deployed:

### 🔥 High CPU Alarm (Scale Out & Alert)
* **Trigger Condition:** `CPUUtilization` is **> 80%** for **2 consecutive periods** of 1 minute.
* **Automated Action 1:** Triggers an **Amazon SNS (Simple Notification Service)** topic that pages the engineering team via email/Slack.
* **Automated Action 2:** Triggers an **EC2 Auto Scaling Group policy** to provision and boot an additional EC2 instance to balance incoming traffic.

### ❄️ Low CPU Alarm (Cost Optimization)
* **Trigger Condition:** `CPUUtilization` drops **< 20%** for **5 consecutive periods** of 5 minutes.
* **Automated Action:** Triggers Auto Scaling to **terminate idle instances**, keeping monthly AWS infrastructure costs optimized.

---

## 🔧 Tools & Services Used
* **Amazon CloudWatch:** Metrics collection, dashboard generation, and alarm triggers.
* **Amazon EC2:** Virtual computing instances serving web application traffic.
* **Amazon SNS:** Managed notification service for DevOps alerting.
* **AWS Auto Scaling:** Automated horizontal infrastructure adjustments.
