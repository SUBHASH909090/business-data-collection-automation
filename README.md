# Business Data Collection Automation

An automated data pipeline built with **n8n** that queries the **OpenStreetMap Overpass API**, cleans and normalizes complex geographic and business data, and writes the structured records directly into Google Sheets[cite: 1].

---

## 📌 Features

- **Automated API Querying:** Executes structured Overpass QL queries to extract target business listings (names, coordinates, contact tags, categories)[cite: 1].
- **Data Normalization:** Parses raw JSON arrays and nested properties into flat, clean tabular records[cite: 1].
- **Spreadsheet Storage:** Streams formatted data directly into Google Sheets without manual intervention[cite: 1].
- **Error Handling & Batching:** Includes retry logic and paging to handle API rate limits reliably.

---

## 🛠️ Tech Stack

- **Workflow Orchestration:** n8n[cite: 1]
- **APIs & Data Protocols:** OpenStreetMap Overpass API, REST APIs, HTTP Requests, JSON[cite: 1]
- **Target Storage:** Google Sheets[cite: 1]

---

## ⚙️ Workflow Architecture

1. **Trigger:** Scheduled cron trigger or manual webhook execution.
2. **HTTP Request Node:** Sends Overpass QL queries to the OpenStreetMap endpoint[cite: 1].
3. **Data Transformation:** Parses response JSON, extracts relevant tags (amenity, name, phone, address), and standardizes column headers[cite: 1].
4. **Google Sheets Node:** Appends records as rows in real time[cite: 1].

---

## 🚀 Setup & Installation

1. Import `workflow.json` into your **n8n** instance.
2. Configure credentials:
   - **Google Sheets OAuth2 / Service Account**[cite: 1]
3. Update the Overpass QL query string inside the HTTP Request node for your target region or amenity type.
4. Set the destination Google Sheet ID.
5. Execute or activate the workflow.
