<div align="center">

![n8n Weather Automation Banner](https://raw.githubusercontent.com/asmtoha/n8n_learning/master/assets/weather-automation-banner.png)

# 🌦️ Weather Email Automation with n8n

Fetch real-time weather data from an API and send it as a formatted email using **n8n**.

</div>

---

## 📌 Overview

This project demonstrates a simple yet practical **n8n workflow** that:
- Fetches current weather data from a Weather API
- Extracts key information like temperature, condition, and humidity
- Sends a clean, readable email using Gmail

The workflow currently uses a **Manual Trigger** for learning and testing, but it can easily be converted into a fully automated alert system.

---

## ⚙️ Workflow Breakdown

### 1️⃣ Manual Trigger
The workflow starts with **n8n’s Manual Trigger**, allowing execution only when manually run inside the editor. This is ideal for development, testing, and learning.

### 2️⃣ HTTP Request – Weather API
An **HTTP Request node** sends a GET request to a Weather API endpoint to retrieve real-time weather data for a selected location.

Typical data includes:
- 🌡️ Temperature
- ☁️ Weather condition
- 💧 Humidity

### 3️⃣ Gmail – Send Weather Report
The API response is passed to a **Gmail node**, where the important fields are formatted into a user-friendly email and sent to a selected email address.

---

## 🔄 From Manual to Automation

This workflow can be upgraded by replacing the Manual Trigger with:
- ⏰ **Schedule Trigger** (daily/hourly weather updates)
- 🌐 **Webhook Trigger** (trigger from external apps)
- ⚡ Any other event-based trigger supported by n8n

No changes are required to the core logic—only the trigger needs to be swapped.

---

## 🎯 Learning Goals

- Understanding data flow between n8n nodes
- Practicing API integration using HTTP Request
- Formatting and sending dynamic emails
- Designing reusable automation workflows

---

## 🚀 Use Cases

- Daily weather alerts
- Location-based weather monitoring
- Email notifications for travel or events
- Foundation for more advanced automation systems

---

## 🛠️ Tools & Technologies

- **n8n** – Workflow automation
- **Weather API** – Real-time weather data
- **Gmail Node** – Email delivery

---

## 📖 Notes

This project is part of my ongoing learning journey with automation and workflow design using n8n. More workflows and experiments will be added to this repository.

---

⭐ If you find this useful, feel free to star the repo and follow my automation journey!

