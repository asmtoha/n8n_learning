# 🚀 Automated Data Pipeline: Apify → n8n → Google Sheets  
### `get_data_using_apify_putin_google_sheet`

This project demonstrates a fully automated data workflow built using **Apify**, **n8n**, and **Google Sheets**.  
The automation fetches scraped data from Apify, processes it through an AI model, and then appends/updates the results directly into Google Sheets — completely hands-free.

---

## ✅ Features

- 🌐 Fetch structured web data via **Apify API**
- 🔁 Trigger workflow manually or automate it using schedules
- 🤖 Process data using **LLM Chain (OpenRouter Model)**
- 🧹 Split, clean, and aggregate incoming data
- 🔎 Logic-based branching (update existing rows or append new ones)
- 📊 Store processed results inside **Google Sheets**
- ⚡ No-code/low-code, easily customizable

---

## 🧩 Workflow Overview

Below is a high-level breakdown of the workflow steps:

1. **Manual Trigger**  
   Start the process using the *Execute Workflow* button.

2. **Get Existing Rows (Google Sheet)**  
   Used to compare current sheet data with new Apify data.

3. **HTTP Request (Apify API)**  
   Fetches dataset/items from your Apify Actor.

4. **Wait Node**  
   Ensures the Apify Actor has fully completed before fetching results.

5. **Split Out → Aggregate**  
   - Splits Apify JSON array into individual items  
   - Aggregates them back into a structured batch

6. **Basic LLM Chain**  
   - Sends data to an AI model  
   - Uses a structured output parser  
   - Extracts or transforms the data

7. **IF Condition**  
   Determines whether a row should be updated or newly added.

8. **Append/Update in Google Sheets**  
   Automatically inserts or updates the correct row.

---

## 🖼 Workflow Screenshot

![Workflow Screenshot](./your_image_filename.png)

*(Replace the filename if needed)*

---

## 📦 Requirements

| Tool | Purpose |
|------|---------|
| **n8n** | Automation engine |
| **Apify** | Data scraping / crawling |
| **Google Sheets API** | Store results |
| **OpenRouter (LLM)** | AI processing |

---

## 🔧 Setup Instructions

1. **Clone the repo**
   ```bash
   git clone https://github.com/asmtoha/n8n_learning.git
