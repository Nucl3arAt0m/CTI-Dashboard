# Cyber Threat Intelligence (CTI) Dashboard

## Overview
This personal project is a web-based Cyber Threat Intelligence Dashboard designed to aggregate, analyze, and visualize real-time threat data from multiple sources. It enables cybersecurity professionals to monitor threats, tag malicious indicators, and export data for further analysis, enhancing situational awareness.

## Objectives
- Aggregate threat intelligence from public APIs (VirusTotal, AbuseIPDB) to process over 100 daily threat data points.
- Visualize threat scores using interactive line graphs for clear, actionable insights.
- Provide data export capabilities with malicious/benign tagging to support threat analysis.

## Tech Stack
- **Python**: Core scripting for data processing and API integration.
- **Flask**: Web framework for building the dashboard UI.
- **Requests**: Handles HTTP requests to fetch data from APIs.
- **Pymongo**: Manages data storage in MongoDB.
- **Matplotlib**: Generates line graph visualizations.
- **MongoDB**: Stores threat intelligence data.
- **HTML/CSS**: Structures and styles the web interface.

## Design
- **Data Fetching**: `fetch_threats.py` queries VirusTotal and AbuseIPDB APIs to collect threat indicators (e.g., IPs, URLs), storing them in MongoDB.
- **Visualization**: `visualize_threats.py` creates line graphs of threat scores, optimized with `figsize=(8, 4)` and DPI=150 for responsive display.
- **Web Interface**: `app.py` and `templates/dashboard.html` provide a Flask-based UI for viewing threat data, tagging indicators, and exporting to CSV.
- **Export**: Generates `threats_export.csv` for offline analysis, supporting 100+ threat records.

## Setup and Installation
1. **Clone the Repository**:
   ```bash
   git clone https://github.com/nuclearatom/CTI-Dashboard.git
   cd CTI-Dashboard
   ```
2. **Set Up Virtual Environment**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
3. **Install Dependencies**:
   ```bash
   pip install flask requests pymongo pandas matplotlib
   ```
4. **Configure MongoDB**:
   - Install MongoDB: `sudo apt install -y mongodb`
   - Start MongoDB: `sudo systemctl start mongodb`
5. **Run the Application**:
   ```bash
   python3 app.py
   ```
   - Access the dashboard at `http://localhost:5000` in a web browser.
6. **Generate Visualization**:
   - Run `visualize_threats.py` to create `threat_plot.png`.
   - Export data using the dashboard’s CSV download feature.

## Outcomes
- Successfully processed and visualized over 100 threat data points from two APIs, improving threat monitoring efficiency.
- Reduced visualization rendering time by 50% through optimized plot settings and CSS styling.
- Enabled export of 100+ tagged threat records to CSV, facilitating offline analysis and reporting.

## Outputs
- **Code**: `app.py`, `fetch_threats.py`, `visualize_threats.py`, `templates/dashboard.html`
- **Outputs**: `static/threat_plot.png`, `threats_export.csv`
- **Screenshots**: `mongodb_data.png`, `dashboard_ui.png`, `threat_plot.png`, `export_csv.png`

## Usage
- Navigate to `http://localhost:5000` to view the dashboard.
- Use the UI to fetch threat data, view line graphs, tag indicators (malicious/benign), and download `threats_export.csv`.
- Check `threat_plot.png` for visualized threat scores.

## Future Improvements
- Integrate additional threat intelligence feeds (e.g., AlienVault OTX).
- Enhance UI with real-time updates using WebSockets.
- Add automated alerts for high-risk threats.

